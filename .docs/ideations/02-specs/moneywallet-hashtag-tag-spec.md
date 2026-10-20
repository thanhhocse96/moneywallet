# Spec + Phản biện: Hashtag trong description → Tag entity

> Ngày: 2026-10-14. Yêu cầu: user gõ `#tag` trong description → gom nhóm chi tiêu theo tag (tag chỉ người, chỉ hãng...); bulk rename `#tag`→`#tag1` đổi toàn bộ giao dịch.

---

## 1. Spec đề xuất

### 1.1. Grammar (phải chốt trước khi code)

- Tag = `#` + 1+ ký tự word. Word char: Unicode letter/number + `_` (KHÔNG dấu cách).
- Regex: `(?<![\p{L}\p{N}_])#([\p{L}\p{N}_][\p{L}\p{N}_-]*)`
- Lookbehind: `abc#tag` không thành tag (copy quy tắc của Twitter/X).
- `#cà_phê` → tag `cà_phê`. `#ăn sáng` → tag `ăn` ("sáng" rơi ra ngoài — phải document rõ cho user Việt).
- **Chuẩn hóa Unicode:** mọi tag name đưa về NFC ngay lúc ghi (`Normalizer.normalize(name, NFC)`) — 1 dòng, triệt tiêu phân mảnh composed/decomposed. Không cấm tiếng Việt (lý do Facebook cấm không áp dụng cho app single-user — xem phân tích 2026-10-14).
- **Case-insensitive identity:** `#tag` = `#tAg` = `#TAG` → cùng 1 tag. Định danh bằng cột fold:
  `fold = NFC(name).lowercase(Locale.ROOT)` (ROOT để tránh bug Turkish-I theo locale máy).
  KHÔNG dùng SQLite `NOCASE` (chỉ fold ASCII, `Đ/đ` lọt).
- **Phân biệt:** identity (case-insensitive, giữ dấu: `ăn_sáng` ≠ `an_sang`) vs search/fuzzy (bỏ dấu lúc gợi ý).

### 1.2. Data model (theo Firefly III)

```sql
CREATE TABLE tags (
    tag_id INTEGER PRIMARY KEY AUTOINCREMENT,
    tag_name TEXT NOT NULL,              -- cách viết đầu tiên (hiển thị)
    tag_fold TEXT NOT NULL UNIQUE,       -- NFC + lowercase(ROOT): định danh, lookup
    tag_color TEXT,
    uuid TEXT NOT NULL UNIQUE,
    last_edit INTEGER NOT NULL,
    deleted INTEGER NOT NULL DEFAULT 0
);
CREATE TABLE transaction_tags (
    _transaction INTEGER NOT NULL,
    _tag INTEGER NOT NULL,
    uuid TEXT NOT NULL UNIQUE,
    last_edit INTEGER NOT NULL,
    deleted INTEGER NOT NULL DEFAULT 0,
    PRIMARY KEY (_transaction, _tag),
    FOREIGN KEY (_transaction) REFERENCES transactions(transaction_id) ON DELETE CASCADE,
    FOREIGN KEY (_tag) REFERENCES tags(tag_id) ON DELETE CASCADE
);
-- Alias cho merge: gõ nhầm trong tương lai tự resolve về tag chính.
-- KHÔNG dùng JSON field (vi phạm 1NF: không index, không UNIQUE được).
CREATE TABLE tag_aliases (
    alias_fold TEXT PRIMARY KEY,         -- fold key của tên biến thể
    tag_id INTEGER NOT NULL REFERENCES tags(tag_id) ON DELETE CASCADE,
    uuid TEXT NOT NULL UNIQUE,
    last_edit INTEGER NOT NULL,
    deleted INTEGER NOT NULL DEFAULT 0
);
```

- Parse description **lúc ghi** (insert/update) → sync join rows. Dedupe theo fold key trong cùng 1 description (`#Coffee` + `#coffee` → 1 join row).
- Thứ tự lookup khi parse `#x`: `tags` theo fold → không có → `tag_aliases` theo fold → không có → tạo tag mới.
- Description vẫn hiển thị `#tag` cho user thấy (export CSV/JSON giữ nguyên text).
- KHÔNG tái dùng cột `transaction_tag` hiện có — cột đó đang pass-through cho transfer legs linkage nội bộ, semantic khác. Giữ nguyên để khỏi vỡ import/export cũ.
- Theo pattern UUID + LAST_EDIT + DELETED của tallybook (chuẩn bị sync).
- KHÔNG auto-collect alias từ description — alias chỉ sinh ra từ merge do user xác nhận (kể cả lúc migrate/import: hỏi user).

### 1.3. Operations

| Thao tác | Thực hiện |
|---|---|
| Query gom chi theo tag | JOIN 3 bảng + GROUP BY (có index → ms) |
| Bulk rename `#tag`→`#tag1` | **1 transaction**: `UPDATE tags SET tag_name/tag_fold` + rewrite description chứa tag (regex boundary, case-insensitive) + bump `last_edit` transaction |
| Xóa tag | Xóa entity + gỡ `#tag` khỏi descriptions (rewrite) |
| **Merge** `#a`,`#b` → `#a` | 1 transaction, 5 bước (xem 1.4) |
| **Unmerge** (tách alias) | `DELETE FROM tag_aliases` → lần sau gõ lại sinh tag mới độc lập |

### 1.4. Merge — spec chi tiết + UI flow

**UI (minimal, theo quyết định):** màn hình quản lý tag → chọn nhiều (2+) tag → nút **Merge** → dialog hỏi tag nào làm key chính:
- Radio list, mỗi dòng hiện số giao dịch đang dùng: `#coffee (42)`, `#coffe (3)`, `#cafe (5)`
- Default tick sẵn tag có count cao nhất (user thường muốn giữ tag đúng chính tả = tag dùng nhiều nhất)
- Dòng preview: "→ `#coffee`. `#coffe`, `#cafe` thành alias — gõ nhầm sau này tự nhận."
- [Hủy] [Gộp]

**5 bước trong 1 transaction** (canonical = tag được chọn, absorbed = các tag còn lại):
```kotlin
db.withTransaction {
    // 1. Re-point join rows của absorbed về canonical
    UPDATE transaction_tags SET _tag = canonical WHERE _tag IN (absorbed...)
    // 2. Ghi alias cho từng absorbed (FLATTEN: dồn cả alias cũ của absorbed vào,
    //    cấm chain a→b→c — lookup luôn single-hop)
    INSERT INTO tag_aliases(alias_fold, tag_id)
        VALUES (fold("coffe"), canonical), (fold("cafe"), canonical), ...
    // 3. Rewrite description: #coffe/#cafe → #coffee (regex boundary, case-insensitive)
    // 4. Xóa tag entity bị hấp thụ (giữ canonical + màu của canonical)
    // 5. Bump last_edit mọi row chạm tới
}
```

**Quyết định kèm:**
- Namespace chung: một chuỗi không thể vừa là tag đang sống vừa là alias — check cả 2 bảng trong transaction.
- Không có undo đầy đủ (join đã re-point không tự tách lại được) — nhưng operation không mất dữ liệu; unmerge khôi phục hành vi tương lai.
- Alias chỉ có ích khi rewrite đã xong: text hiển thị đồng nhất + lần gõ nhầm sau tự lành.

---

## 2. Phản biện — các lỗ hổng trong spec gốc

### P1. Source-of-truth ambiguity (lỗ hổng lớn nhất)
Có 2 "sự thật" tiềm năng: text trong description vs bảng tags. Nếu không chọn 1, rename sẽ làm chúng lệch nhau (text còn `#tag` cũ, query ra `#tag1` → user hoang mang).
**Quyết:** description là source of truth; bảng tags là index materialized. Bulk rename = atomic transaction gồm cả UPDATE tag lẫn rewrite description.

### P2. Boundary regex trong bulk rename (bug chờ xảy ra)
Rename `#an`→`#anmoi` bằng text replace thường sẽ chạm `#an_vat`. BẮT BUỘC dùng regex boundary `(?<![\p{L}\p{N}_])#an(?![\p{L}\p{N}_-])`. Viết unit test riêng cho case này (kiểu characterization test đã chốt trong roadmap).

### P3. Retroactive parsing sinh tag rác
Description cũ có thể chứa `#` không phải tag ("giảm #1", "mua #2 cái"). Migration tự parse toàn bộ history → tag rác.
**Quyết:** forward-only — chỉ parse từ lúc feature bật; thêm nút "quét tag từ lịch sử" opt-in.

### P4. Thực tế gõ tiếng Việt
- User sẽ viết `#ăn sáng` (có dấu cách) → chỉ parse được `ăn`. Cần UX: gạch chân/highlight tag **ngay khi đang gõ** để user thấy boundary thật.
- `#an_sang` vs `#ăn_sáng` là 2 tag khác nhau (Telex vs bỏ dấu). Không normalize lúc lưu (giữ nguyên ý user); autocomplete lúc gõ sẽ giảm trùng.

### P5. Rewrite description phải bump LAST_EDIT
Tallybook dùng soft-delete + last_edit cho sync tương lai. Bulk rename rewrite description mà không bump `last_edit` → sync sau này mất update. Đưa vào cùng transaction ở 1.3.

### P6. Phạm vi tag
"Chỉ người / chỉ hãng" chỉ là cách dùng — giữ tag flat, không làm namespace (`#person:`). Nếu sau này cần, thêm cột `kind` nullable, không phá schema.

### P7. Split parts
Description của split part (`split_note`) có parse tag không? Đề xuất: có — nhưng join row trỏ về transaction cha (đơn giản, đủ dùng). Cần chốt trước khi code.

---

## 3. Research liên quan

- **Firefly III** (open-source, tham chiếu tốt nhất): bảng `tags` + join table `tag_transaction_journal` (many-to-many, đã verify qua issue #11620 về index cho reporting). Tag có metadata (mô tả, vị trí/map — dùng cho tag "chuyến đi"). Có rules engine auto-tag transaction. Nên đọc `TagController` và migrations của họ trước khi thiết kế UI quản lý tag.
- **Toshl**: có tags trên expense, dùng filter/report — UX đơn giản để tham khảo.
- **YNAB**: không có tag native; user workaround bằng cách gõ `#` trong memo rồi search text = parse-on-read thủ công. Chứng minh nhu cầu có thật, và chứng minh parse-on-read đủ dùng ở quy mô nhỏ.
- **Actual Budget / Money Lover**: không có tag — đúng khoảng trống user chỉ ra.
- **Twitter/X hashtag spec**: quy tắc lookbehind/lookahead cho boundary — copy, đừng tự phát minh.

---

## 4. Thứ tự triển khai đề xuất (~1.5–2 tuần)

1. Chốt grammar + source-of-truth (mục 1.1, P1) — 0.5 ngày
2. Migration v11: 2 bảng mới — 1 ngày
3. Parse-on-write trong insert/update (+ quyết P7) — 1 ngày
4. Bulk rename + unit test boundary regex (P2, P5) — 1.5 ngày
5. UI: autocomplete `#` khi gõ, màn hình quản lý tag, filter theo tag — 3–4 ngày
6. `AnalyticsEngine.spendingByTag()` — 0.5 ngày (nối vào plugin analytics đã thiết kế)

**Câu hỏi còn mở cho bạn:** P7 (tag trong split note?) và forward-only vs quét lịch sử (P3).
