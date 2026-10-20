# Roadmap hiện đại hóa MoneyWallet

> Từ codebase Java (commit 11/2021, 441 files, ~70k LOC) → app Android hiện đại (Kotlin, Room, coroutines/Flow, targetSdk 35/36), kèm tính năng vàng (phân/chỉ/lượng).
> Đọc kèm: `moneywallet-data-layer-deep-analysis.md` (phân tích tầng data).

---

## Nguyên tắc dẫn đường (kinh nghiệm migration dự án legacy)

1. **Không big-bang rewrite.** Mọi phase kết thúc app vẫn build, cài, chạy được — luôn có bản shippable.
2. **Strangler pattern:** backend mới (Kotlin/Room) sống cạnh backend cũ (Java/Provider), nuốt dần từng domain rồi xóa code cũ.
3. **Risk-first:** việc đáng sợ nhất (Room mở được file `.db` của user cũ không?) làm sớm nhất, không để cuối.
4. **Vertical slice trước, horizontal sau:** chứng minh stack mới bằng 1 tính năng thật chạy end-to-end (currency + vàng), rồi mới port hàng loạt.
5. **Old code là oracle:** project 0 test → viết characterization test so sánh output implementation mới vs cũ trên cùng input, trước khi xóa code cũ.
6. **Backup trước migrate:** lần đầu mở DB bằng Room, tự động export JSON backup trước — user mất dữ liệu là thảm họa không thể rollback bằng lời xin lỗi.

---

## Tổng quan 7 phase

| Phase | Nội dung | Thời gian (part-time) | App chạy được? |
|---|---|---|---|
| 0 | Toolchain & compliance | 1–2 tuần | ✅ như cũ |
| 1 | Room core + validate trên `.db` thật | 2 tuần | ✅ như cũ |
| 2 | **Vertical slice: currency + vàng trên stack mới** | 2–3 tuần | ✅ + tính năng vàng |
| 3 | Port toàn bộ write orchestration sang Repository | 3–4 tuần | ✅ |
| 4 | Migrate UI: Loader → Flow, xóa Provider | 3–4 tuần | ✅ hiện đại |
| 5 | UI modernization (M3, thay lib chết) | ongoing | ✅ đẹp hơn |
| 6 | Vàng phase 2: giá tự động (SJC/…) | 2–3 tuần | ✅ |

**Tổng tới phase 4:** ~4–5 tháng part-time (~10–15h/tuần), hoặc ~2–2.5 tháng full-time.

---

## Phase 0 — Toolchain & compliance (1–2 tuần)

**Mục tiêu:** build system hiện đại, app đạt chuẩn Play Store 2026. Code vẫn Java, behavior không đổi.

- [ ] AGP 4.0.1 → 8.x, Gradle 6.1.1 → 8.x, `jcenter()` → `mavenCentral()`
- [ ] `compileSdk`/`targetSdk` 29 → 35 (hoặc 36), `minSdk` 21 → 26
- [ ] Gắn Kotlin plugin 2.x (chưa viết Kotlin, chỉ chuẩn bị)
- [ ] Xóa `free_reflection` + code trong `App.java` (crash Android 11+)
- [ ] Gọn flavor: giữ `floss`+`osm`, bỏ `proprietary`/`gmap` (cần API key không có)
- [ ] Scoped storage: backup/export chuyển sang SAF (không còn `WRITE_EXTERNAL_STORAGE`)
- [ ] `USE_FINGERPRINT` → Biometric API (`USE_BIOMETRIC`)
- [ ] Foreground service types + `SCHEDULE_EXACT_ALARM` nếu dùng (Android 14+)
- [ ] Fix build break do bump lib, chạy smoke test thủ công toàn bộ luồng chính

**Exit criteria:** `./gradlew assembleRelease` pass; cài trên máy Android 14/15/16 chạy được; backup/restore OK.
**Rủi ro:** lib chết không có bản mới tương thích → pin version cũ tạm, ghi vào tech-debt list cho phase 5.

---

## Phase 1 — Room core + validation (2 tuần)

**Mục tiêu:** Room mở được database của user cũ, không mất 1 dòng dữ liệu. Đây là phase de-risk quan trọng nhất.

- [ ] 24 `@Entity` map 1:1 tên bảng/cột (giữ `String` cho cột DATETIME — xem phân tích data)
- [ ] `currencies`: `@PrimaryKey` trên `currency_iso` (TEXT)
- [ ] Junction tables: `@Entity(primaryKeys = [...])`; FK đúng `CASCADE`/`SET_NULL` như Schema
- [ ] `RoomDatabase` version 4 + migration 3→4: `CREATE INDEX` cho các cột FK theo naming của Room (DB cũ không có index nào — không làm bước này validation sẽ fail)
- [ ] Export schema JSON, bật `exportSchema = true`
- [ ] **Test quyết định:** lấy file `.db` thật từ bản 4.0.5.10 (cài bản cũ, nhập vài dữ liệu, pull db), mở bằng Room, assert đọc đủ 24 bảng + số dòng khớp
- [ ] DAO CRUD cơ bản cho 24 bảng (chưa cần JOIN phức tạp)

**Exit criteria:** test mở `.db` thật pass trên 3 sample khác nhau (db trống, db có dữ liệu, db sau restore từ backup JSON).
**Rủi ro:** sai 1 chi tiết schema (default, NOT NULL) → crash lúc mở app với user cũ. Mitigation: test trên db thật + auto-backup JSON trước khi Room chạm vào db (làm luôn từ phase này).

---

## Phase 2 — Vertical slice: currency + vàng trên stack mới (2–3 tuần)

**Mục tiêu:** chứng minh stack mới end-to-end bằng 1 domain độc lập (currency), đồng thời ship luôn tính năng vàng user cần.

- [ ] Entity `currencies` thêm cột `unit_type` (0 = decimal thường, 1 = vàng VN) + migration 4→5
- [ ] `GoldFormatter`: `257` (phân) → `"2 lượng 5 chỉ 7 phân"`; parse ngược
- [ ] UI nhập tiền cho vàng: 3 ô lượng/chỉ/phân (thay MoneyPicker thập phân khi `unit_type = 1`)
- [ ] Seed currency `VAU` ("Vàng", symbol `lượng`, decimals 2) — **không dùng `XAU`** (bị service tỉ giá ghi đè, xem phân tích)
- [ ] Nhập tỉ giá thủ công: dialog "1 lượng = X VND", lưu qua `ExchangeRateCache` (quy về đơn vị per-USD như model hiện tại)
- [ ] Migrate 2 màn hình currency (`CurrencyListActivity`, `NewEditCurrencyActivity`) sang ViewModel + StateFlow — **màn hình đầu tiên bỏ Loader**, làm mẫu cho phase 4
- [ ] Characterization test cho GoldFormatter (table-driven, ~30 case)

**Exit criteria:** tạo ví vàng, nhập 2 lượng 5 chỉ, xem đúng "2 lượng 5 chỉ", quy đổi ra VND đúng tỉ giá nhập tay; các màn hình khác vẫn chạy bình thường trên stack cũ.
**Rủi ro:** thấp — domain currency ít phụ thuộc chéo, là lựa chọn slice lý tưởng.

---

## Phase 3 — Port write orchestration sang Repository (3–4 tuần)

**Mục tiêu:** toàn bộ logic ghi chạy trên Room, bọc `@Transaction` thật sự (sửa luôn bug không-transaction của code cũ).

- [ ] Repository per aggregate: `TransactionRepository` (gồm transfer orchestration), `DebtRepository`, `BudgetRepository`, `SavingRepository`, `RecurrenceRepository`…
- [ ] Port ~30 method insert/update/delete từ `SQLDatabase`: giữ nguyên business rule (system category tags, junction sync, recurrence UUID deterministic)
- [ ] Mỗi repository method bọc `@Transaction`
- [ ] **Characterization test:** cùng input → so sánh DB state giữa implementation cũ và mới (dùng code cũ làm oracle), đặc biệt: insertTransfer (2–3 transaction + junction), updateTransaction (sync people/attachments), insertDebt
- [ ] `DataContentProvider` chuyển thành lớp delegate mỏng gọi Repository (strangler) — UI chưa đổi gì

**Exit criteria:** toàn bộ test oracle pass; provider mới cho kết quả query/write giống hệt provider cũ trên bộ scenario chuẩn; app chạy full luồng bằng provider-mới.
**Rủi ro:** port sai rule ẩn (thứ tự insert, xử lý conflict tuple). Mitigation duy nhất: test oracle + review diff từng method với code cũ.

---

## Phase 4 — Migrate UI: Loader → Flow, xóa Provider (3–4 tuần)

**Mục tiêu:** xóa sổ kiến trúc 2015.

- [ ] Từng màn hình: `CursorLoader` → `ViewModel` + `StateFlow`/`collectAsState`, dùng chung pattern đã chuẩn hóa ở phase 2
- [ ] Xóa `LocalBroadcastManager` (36 files) — Room invalidation tự refresh
- [ ] Xóa `startActivityForResult` (14 files) → Activity Result API
- [ ] Khi màn hình cuối cùng migrate xong: xóa `DataContentProvider`, `SyncContentProvider`, `SQLDatabase`, `SQLCache`, `Contract`, `MultiUriCursorWrapper`
- [ ] Smoke test toàn app + test upgrade từ bản cũ (install 4.0.5.10 → nhập data → upgrade → verify)

**Exit criteria:** 0 file reference tới provider/loader/broadcast; APK nhỏ hơn; upgrade từ bản cũ không mất data.
**Rủi ro:** sót màn hình dùng URI lạ. Mitigation: grep toàn bộ `CONTENT_` trước khi xóa, mỗi màn hình migrate có checklist test tay.

---

## Phase 5 — UI modernization (ongoing, làm dần)

- Material 3 theme; thay lib chết: `material-dialogs` → MDC, `bottomsheetpickers` → MDC pickers, `MPAndroidChart` → Vico/Compose chart, `fingerprint-auth` → BiometricPrompt, `jxl` → Apache POI, `iText 5 (AGPL)` → cân nhắc thay nếu muốn gỡ ràng buộc license
- Compose cho màn hình mới (giữ View/XML cho màn hình cũ ổn định — không rewrite UI hàng loạt)
- Xóa `osmdroid` nếu không dùng map, hoặc giữ (vẫn maintained)

---

## Phase 6 — Vàng phase 2: giá tự động (2–3 tuần, optional)

- Nguồn giá vàng VN (SJC/BTMC): API nếu có, không thì scrape có cache + fallback giá tay
- Worker định kỳ cập nhật tỉ giá vàng (WorkManager), lưu lịch sử giá
- Cảnh báo biến động giá (optional)

---

## Chiến lược test xuyên suốt

| Tầng | Cách test (hiện tại 0 test) |
|---|---|
| Formatter/tính toán (`GoldFormatter`, `MoneyFormatter`, `DateUtils`) | Unit test thuần JVM, table-driven |
| Repository write | Characterization test vs implementation cũ (oracle), chạy trên in-memory Room + SQLite thật |
| Migration | Test mở `.db` thật nhiều version, assert row count + checksum |
| UI | Smoke test tay theo checklist/màn hình (chưa đầu tư UI test automation vội) |

## Decision log (ghi lại để khỏi tranh cãi lại)

- **ADR-1:** Thay thế thay vì convert Java→Kotlin hàng loạt (code sắp xóa không convert).
- **ADR-2:** Giữ ngày giờ dạng TEXT `"yyyy-MM-dd HH:mm:ss"`, không đổi sang millis.
- **ADR-3:** Đơn vị lưu trữ vàng = phân (INTEGER), decimals = 2, đơn vị hiển thị = lượng.
- **ADR-4:** Không dùng ISO `XAU` cho vàng VN (tránh bị service tỉ giá ghi đè) → dùng `VAU`.
- **ADR-5:** minSdk 26, targetSdk 35/36; bỏ flavor `proprietary`/`gmap`.
- **ADR-6 (license):** GPL v3 + iText AGPL → mọi bản fork phải open-source. Nếu muốn thương mại: thay iText trước khi public.

---

## Checklist "không bao giờ được quên"

- [ ] Auto-backup JSON trước lần đầu Room mở DB cũ
- [ ] Mọi migration có test trên `.db` thật
- [ ] Không xóa code cũ khi chưa có test oracle pass
- [ ] Mỗi phase xong: build release, cài máy thật, smoke test
