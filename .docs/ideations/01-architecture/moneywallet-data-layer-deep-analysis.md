# Phân tích sâu tầng Data — MoneyWallet (AndreAle94/moneywallet)

> Phân tích từ source tại commit `071be04` (11/2021), version 4.0.5.10.
> Phạm vi: `storage/database/` + `storage/cache/` + `utils/DateUtils.java` — toàn bộ tầng dữ liệu local.

---

## 1. Bản đồ kiến trúc tầng data hiện tại

```
UI (56 files) ──getContentResolver()──▶ DataContentProvider (45 URIs, 832 dòng)
                                                    │
                        ┌───────────────────────────┼───────────────────────────┐
                        ▼                           ▼                           ▼
              SQLDatabase (4.779 dòng)     Schema.java (774 dòng)        Contract.java
         SQLiteOpenHelper + toàn bộ       DDL khai báo 24 bảng          "Virtual tables":
         business logic ghi/xóa +         (CREATE TABLE...)             tên cột JOIN đã
         các query JOIN thủ công                                    denormalize cho UI
                        │
                        ▼
              moneywallet.db (SQLite, v3)
              money/cache (SQLCache.java — cache riêng)

Luồng phụ:
  SyncContentProvider (245 dòng) — expose raw tables cho SyncAdapter "tương lai" (chưa bao giờ được build)
  Backup: JSONDatabaseExporter/Importer (stream per-table Cursor → JSON) + CSV/XLS/PDF exporters
  LegacyDatabaseImporter (847 dòng) — import từ bản MoneyWallet đời đầu
```

**Nhận xét kiến trúc:** Đây là mẫu **ContentProvider-as-Repository** điển hình giai đoạn 2015–2018. Provider là cửa ngõ duy nhất (chỉ 2 file chạm trực tiếp `SQLDatabase`), toàn bộ UI đọc qua `CursorLoader`. Logic nghiệp vụ (không phải SQL thuần) nằm lẫn trong `SQLDatabase`.

---

## 2. Schema: 24 bảng, 6 nhóm domain

### 2.1. Nhóm core tiền tệ

| Bảng | PK | Ghi chú |
|---|---|---|
| `currencies` | `currency_iso` TEXT | PK là TEXT, không autoincrement |
| `wallets` | `wallet_id` INTEGER AUTOINCREMENT | `wallet_start_money` INTEGER, `wallet_index` (sort tay, thêm ở v3) |
| `transactions` | `transaction_id` INTEGER AUTOINCREMENT | Bảng trung tâm; 7 FK ra ngoài |
| `transfers` | `transfer_id` INTEGER AUTOINCREMENT | Trỏ tới 2–3 dòng `transactions` (from/to/tax) |

### 2.2. Nhóm template & định kỳ

| Bảng | Ghi chú |
|---|---|
| `transaction_models`, `transfer_models` | Template tạo nhanh (bản sao rút gọn của transaction/transfer) |
| `recurrent_transactions`, `recurrent_transfers` | `RULE` TEXT (chuỗi RFC 5545, lib `org.dmfs:lib-recur`), `last/next_occurrence` |

### 2.3. Nhóm kế hoạch

| Bảng | Ghi chú |
|---|---|
| `budgets` + `budget_wallets` (junction) | `budget_type`: 0=expenses, 1=incomes, 2=category |
| `savings` | Mục tiêu tiết kiệm, `end_money`, `complete` |
| `debts` + `debt_people` (junction) | Nợ/phải thu, `expiration_date` |

### 2.4. Nhóm ngữ cảnh

| Bảng | Ghi chú |
|---|---|
| `categories` | **Self-FK** `category_parent` ON DELETE CASCADE (cây danh mục); `category_tag` chứa tag hệ thống |
| `events` + `event_people` (junction) | Sự kiện |
| `places` | `latitude/longitude` REAL |
| `people` | Người liên quan |

### 2.5. Nhóm đính kèm

`attachments` + `transaction_attachment` + `transfer_attachment` (junction, composite PK).

### 2.6. Quy ước chung (quan trọng cho Room)

Mọi bảng (kể cả junction) đều có 3 cột sync:

```sql
uuid      TEXT NOT NULL UNIQUE,   -- định danh cross-device
last_edit INTEGER NOT NULL,       -- millis, cho sync tương lai
deleted   INTEGER NOT NULL DEFAULT 0  -- soft delete, mọi query đều lọc deleted = 0
```

Các quy ước kiểu dữ liệu:

| Khái niệm | Lưu trữ | Ghi chú Room |
|---|---|---|
| Tiền | `INTEGER` (đơn vị nhỏ nhất, tránh float) | Map thẳng `Long` |
| Ngày giờ | `TEXT` format `"yyyy-MM-dd HH:mm:ss"` trong cột kiểu `DATETIME` | **Không phải millis!** Giữ `String` hoặc converter String↔LocalDateTime |
| Boolean | `INTEGER` 0/1 | Room map native `boolean` |
| Tọa độ | `REAL` | `Double` |
| Junction | Composite PK `(_a, _b)` + 3 cột sync | `@Entity(primaryKeys = [...])` |
| FK | `ON DELETE CASCADE` cho quan hệ bắt buộc, `SET NULL` cho optional | `@ForeignKey(onDelete = CASCADE / SET_NULL)` |

**System categories** (nghiệp vụ ẩn trong data): các danh mục `type=2` (SYSTEM) định danh bằng `TAG`: `system::transfer`, `system::transfer_tax`, `system::debt`, `system::credit`, `system::paid_debt`, `system::paid_credit`, `system::tax`, `system::deposit`, `system::withdraw`. Mọi transfer/debt/saving đều sinh transaction trỏ vào các category này — xóa nhầm là gãy toàn bộ số liệu.

**Migration history:** v1→v3 chỉ gồm 2 `ALTER TABLE ADD COLUMN` (wallet_index, category_index). Lịch sử migration cực đơn giản.

---

## 3. Luồng đọc (Read path)

```
DataContentProvider.query(uri)
  → switch 45 URI → SQLDatabase.getX(projection, selection, selectionArgs, sortOrder)
      → build thủ công chuỗi SQL: subquery JOIN denormalize
      → queryFrom(subquery, ...) bọc outer SELECT áp projection/selection/sort của caller
  → MultiUriCursorWrapper + setNotificationUri (fan-out nhiều URI)
```

Ví dụ `getTransactions()`: 1 subquery JOIN `transactions` với `categories`, `wallets`, `places`, `events`, `transaction_people`→`people`, dùng `GROUP_CONCAT('<' || person_id || '>')` để nén danh sách người thành 1 cột `transaction_person_ids`, `GROUP BY transaction_id`, lọc `deleted = 0` ở mọi bảng.

`Contract.*` định nghĩa "virtual tables": tên cột sau JOIN (prefix `transaction_`, ví dụ `transaction_category_name`). UI chỉ biết Contract, không biết Schema — đây là điểm tốt, Room DAO có thể tái tạo đúng các projection này bằng `@Query` JOIN trả về POJO.

**Notification fan-out thủ công:** mỗi query đăng ký nhiều URI (ví dụ `TRANSACTION_LIST` observe 9 URI: wallets, transactions, transfers, categories, debts, events, people, places, attachments). Khi migrate sang Room, `InvalidationTracker` tự biết query chạm bảng nào → toàn bộ `notifyChange`/`setNotificationUri` thủ công **biến mất**, cùng với 36 file dùng `LocalBroadcastManager`.

---

## 4. Luồng ghi (Write path) — phần việc nặng nhất

`SQLDatabase` chứa ~30 method `insert/update/delete` per-entity (package-local, provider gọi). Mỗi method là một **orchestration nhiều bước**, ví dụ `insertTransfer()`:

1. Tạo transaction nguồn (EXPENSE, category `system::transfer`, ví `from`)
2. Tạo transaction đích (INCOME, ví `to`)
3. Nếu có thuế: tạo transaction thuế (category `system::transfer_tax`)
4. Tạo dòng `transfers` trỏ tới 2–3 transaction trên
5. Insert junction `transfer_people`, `transfer_attachment`

Tương tự: `insertDebt` sinh debt + các transaction hệ thống (debt/credit/paid...), `insertSaving` sinh deposit/withdraw, `updateTransaction` đồng bộ lại junction people/attachments (check conflict từng tuple).

Logic đặc biệt:
- **UUID định danh recurrence:** `getRecurrentItemUUID(recurrenceUUID, date)` — deterministic UUID từ (recurrence, ngày) để item định kỳ có identity ổn định cross-device.
- Mỗi dòng ghi đều set `uuid` random + `last_edit = now()` + `deleted = 0`.

### ⚠️ Phát hiện: không có transaction SQLite nào

`beginTransaction` xuất hiện **0 lần** trong toàn bộ `SQLDatabase`. Một `insertTransfer` = 4–6 câu INSERT rời rạc — crash giữa chừng để lại dữ liệu dở dang (transfer không có transaction đích, junction mồ côi...). Đây là bug tiềm ẩn có thật, và migrate sang Room `@Transaction` sẽ **sửa luôn**, không chỉ "chuyển ngang".

---

## 5. Model POJOs (24 file) → Entities

`storage/database/model/*` là POJO field-public mirror bảng raw (`Transaction.mDate` là `String` — khớp format TEXT). Khi migrate:

- Gắn `@Entity(tableName = "...")` + `@ColumnInfo(name = "...")` giữ nguyên tên bảng/cột → Room mở trực tiếp file `.db` cũ.
- `currencies`: `@PrimaryKey` trên `currency_iso` (String, `autoGenerate = false`).
- Junction tables: `@Entity(primaryKeys = {"_event", "_person"})`.
- FK: khai báo `@ForeignKey` đúng `onDelete` như Schema.
- Các class "view" denormalize cho UI (tương đương Contract virtual tables): viết POJO mới, DAO `@Query` JOIN fill vào.

### ⚠️ Checklist validation Room (dễ sập nhất)

1. **Indices:** Room tự expect index cho các cột FK (`index_<table>_<col>`), nhưng DB cũ **không có index nào**. Mở DB cũ bằng Room sẽ fail validation → cần migration 3→4 `CREATE INDEX` đúng naming của Room, hoặc test kỹ với `exportSchema`.
2. **AUTOINCREMENT:** Room `@PrimaryKey(autoGenerate = true)` sinh `INTEGER PRIMARY KEY AUTOINCREMENT` — khớp Schema. Kiểm tra `sqlite_sequence` còn nguyên.
3. **Date TEXT:** giữ field `String` (zero behavior change) hoặc converter; **không** đổi sang millis nếu không muốn rewrite toàn bộ query sort.
4. Test bắt buộc: mở file `.db` thật từ bản 4.0.5.10 trên máy, chạy full backup/restore round-trip.

---

## 6. Backup / Export / Import

- **JSON backup** (`JSONDatabaseExporter/Importer`): stream từng bảng qua Cursor → JSON có version header (`JSONDatabase.VERSION`). Format độc lập storage engine → sau Room, chỉ cần đổi nguồn Cursor thành DAO, **file backup cũ vẫn đọc được**.
- **CSV/XLS/PDF exporters**: đọc qua provider/query — rewire tương tự.
- **LegacyDatabaseImporter** (847 dòng): import từ bản MoneyWallet đời đầu — giữ nguyên, chạy một lần.
- ⚠️ **Scoped storage:** backup/export hiện ghi external storage (`WRITE_EXTERNAL_STORAGE`) — trên Android 10+ phải chuyển sang SAF/MediaStore. Đây là việc bắt buộc trong Phase 0, độc lập với Room.

---

## 7. Thành phần có thể bỏ

| Thành phần | Lý do |
|---|---|
| `SyncContentProvider` (245 dòng) | Scaffold cho SyncAdapter chưa bao giờ được build; 20 URI expose raw table không ai dùng |
| `SQLCache.java` | Cache thủ công — Room + Flow làm tốt hơn |
| `free_reflection` (gọi trong `App.java`) | Hack hidden-API, **crash trên Android 11+** — xóa ngay Phase 0 |
| `LocalBroadcastManager` (36 files) | Room invalidation thay thế |
| `MultiUriCursorWrapper` | Không cần khi bỏ provider |

---

## 8. Ước lượng effort (solo dev)

| Hạng mục | Ước lượng |
|---|---|
| Phase 0: toolchain (AGP 8, targetSdk 35/36, minSdk 26, Kotlin, bỏ flavor thừa, xóa free_reflection, SAF cho backup) | 1–2 tuần |
| Entities (24) + converters + DB class + migration 3→4 (indices) | 3–5 ngày |
| DAO read queries (~15 JOIN denormalize + CRUD cơ bản) | 1–2 tuần |
| Repository write orchestrations (port ~30 method insert/update/delete + bọc @Transaction + test) | 2–4 tuần |
| Rewire backup/export/import | 3–5 ngày |
| Verify trên .db thật + backup round-trip + regression | 1 tuần |
| **Tổng** | **~6–10 tuần part-time / ~4–6 tuần full-time** |

Rủi ro lớn nhất không phải code mới, mà là **port sai business rule ẩn** trong `SQLDatabase` (ví dụ: thứ tự insert transfer, cách sync junction khi update, system category tags) trong khi **không có test nào**. Khuyến nghị viết test cho các orchestration ghi trước khi xóa code cũ (dùng chính DB cũ làm oracle: so sánh output của 2 implementation trên cùng input).
