# .context/MILESTONES.md — MoneyWallet
# Milestone source of truth. Đọc cả mục "Nợ kỹ thuật đang mang" trước khi nhận task mới.

Current milestone: **P0 — Toolchain & compliance**

## Checklist P0 — Toolchain & compliance (1–2 tuần)

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

## Checklist P1 — Room core + validation (2 tuần)

- [ ] 24 `@Entity` map 1:1 tên bảng/cột (giữ `String` cho cột DATETIME)
- [ ] `currencies`: `@PrimaryKey` trên `currency_iso` (TEXT)
- [ ] Junction tables: `@Entity(primaryKeys = [...])`; FK đúng `CASCADE`/`SET_NULL`
- [ ] `RoomDatabase` version 4 + migration 3→4: `CREATE INDEX` cho các cột FK
- [ ] Export schema JSON, bật `exportSchema = true`
- [ ] Test quyết định: lấy file `.db` thật từ bản 4.0.5.10, mở bằng Room, assert đọc đủ 24 bảng + số dòng khớp
- [ ] DAO CRUD cơ bản cho 24 bảng

**Exit criteria:** test mở `.db` thật pass trên 3 sample khác nhau.

## Checklist P2 — Vertical slice: currency + vàng trên stack mới (2–3 tuần)

- [ ] Entity `currencies` thêm cột `unit_type` (0 = decimal, 1 = vàng VN) + migration 4→5
- [ ] `GoldFormatter`: `257` (phân) → `"2 lượng 5 chỉ 7 phân"`; parse ngược
- [ ] UI nhập tiền cho vàng: 3 ô lượng/chỉ/phân
- [ ] Seed currency `VAU` ("Vàng", symbol `lượng`, decimals 2) — không dùng `XAU`
- [ ] Nhập tỉ giá thủ công: dialog "1 lượng = X VND"
- [ ] Migrate 2 màn hình currency sang ViewModel + StateFlow
- [ ] Characterization test cho GoldFormatter (~30 case)

## Checklist P3 — Port write orchestration sang Repository (3–4 tuần)

- [ ] Repository per aggregate: `TransactionRepository`, `DebtRepository`, `BudgetRepository`, `SavingRepository`, `RecurrenceRepository`
- [ ] Port ~30 method insert/update/delete từ `SQLDatabase`
- [ ] Mỗi repository method bọc `@Transaction`
- [ ] Characterization test so sánh DB state giữa implementation cũ và mới
- [ ] `DataContentProvider` chuyển thành lớp delegate mỏng gọi Repository

## Checklist P4 — Migrate UI: Loader → Flow, xóa Provider (3–4 tuần)

- [ ] Từng màn hình: `CursorLoader` → `ViewModel` + `StateFlow`
- [ ] Xóa `LocalBroadcastManager` (36 files)
- [ ] Xóa `startActivityForResult` (14 files) → Activity Result API
- [ ] Khi migrate xong: xóa `DataContentProvider`, `SyncContentProvider`, `SQLDatabase`, `SQLCache`, `Contract`, `MultiUriCursorWrapper`

## Checklist P5 — UI modernization (ongoing)

- [ ] Material 3 theme
- [ ] Thay lib chết: `material-dialogs` → MDC, `bottomsheetpickers` → MDC pickers, `MPAndroidChart` → Vico/Compose chart
- [ ] Compose cho màn hình mới

## Checklist P6 — Vàng phase 2: giá tự động (2–3 tuần, optional)

- [ ] Nguồn giá vàng VN (SJC/BTMC): API hoặc scrape có cache
- [ ] Worker định kỳ cập nhật tỉ giá vàng (WorkManager)

## Nợ kỹ thuật đang mang

- Backlog outstanding: xem `.docs/moneywallet-outstanding-backlog.md`
- Hotfix #177/#221 (crash boot loop SAF) — ưu tiên cao nhất
- 1-cent bugs (#205, #189, #290, #128, #45, #32) — bắt buộc trước tính năng vàng
- #303 (backup/restore mất wallet notes)
- #197 (restore chỉ ra subset dữ liệu)

## Decision log (ADR)

- ADR-1: Thay thế thay vì convert Java→Kotlin hàng loạt.
- ADR-2: Giữ ngày giờ dạng TEXT `"yyyy-MM-dd HH:mm:ss"`.
- ADR-3: Đơn vị lưu trữ vàng = phân (INTEGER), decimals = 2.
- ADR-4: Không dùng ISO `XAU` cho vàng VN → dùng `VAU`.
- ADR-5: minSdk 26, targetSdk 35/36; bỏ flavor `proprietary`/`gmap`.
- ADR-6: GPL v3 + iText AGPL → mọi bản fork phải open-source.
