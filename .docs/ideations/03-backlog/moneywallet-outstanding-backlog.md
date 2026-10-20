# Backlog: các issue CHƯA FIX của MoneyWallet

> Lọc từ 100 open issues → chỉ giữ bug/feature còn tồn đọng, đã verify root cause trong code.
> Chi tiết root cause đầy đủ: `moneywallet-issues-research-report.md`
> Đã loại (ghi rõ lý do cuối file).

---

## 🔴 Critical

### #177 + #221 — App crash boot loop vĩnh viễn (SAF auto-backup)
- **Hiện trạng:** chưa fix. User bật auto-backup → setting hỏng → crash ngay khi mở app, chỉ còn cách xóa data.
- **Root cause:** `model/SAFFile.java:38-47` ném RuntimeException khi decode chuỗi setting hỏng; không được catch ở `BackendServiceFactory.getFile()`.
- **Fix:** try/catch khi decode → disable auto-backup backend đó + log, thay vì crash cả app. Về lâu dài viết lại SAF backend (roadmap P0/P5).
- **Effort:** 0.5 ngày (hotfix).

---

## 🟠 High

### #303 — Backup/Restore làm mất wallet notes
- **Hiện trạng:** chưa fix. Note của ví (người ta dùng lưu IBAN) mất lặng lẽ sau restore.
- **Root cause:** `SQLDatabaseExporter.getWallet()` thiếu đúng 1 dòng đọc cột `NOTE`.
- **Fix:** thêm dòng đọc `Schema.Wallet.NOTE` + test round-trip export→import cho mọi entity.
- **Effort:** 3 giờ.

### #298 — Xóa transaction không xóa attachment
- **Hiện trạng:** chưa fix. File đính kèm mồ côi tích tụ, DB/backup phình, không có UI dọn.
- **Root cause:** `SQLDatabase.deleteTransactionItem()` (`SQLDatabase.java:1026-1058`) xóa junction nhưng không xóa dòng `attachments` lẫn file vật lý; FK CASCADE vô dụng vì dòng bị xóa là junction.
- **Fix:** xóa attachment không còn reference + xóa file; thêm màn hình quản lý attachments; đưa vào `@Transaction` khi migrate Room (P3).
- **Effort:** 1–2 ngày.

### Họ bug "mất 1 cent" — #205, #189, #290, #128 (+ #45, #32)
- **Hiện trạng:** chưa fix. Nhập 20.6 → 20.59; 92.96 → 92.95; 160/25 = 6. Thêm **#128**: nhập 100 trong savings deposit hiện thành 1.00.
- **Root cause:** 3 chỗ dùng `double` rồi truncate về `long`: `MoneyFormatter.normalize()` (`utils/MoneyFormatter.java:88-93`), `CurrencyConverterPicker.convert()` (`picker/CurrencyConverterPicker.java:174-180`), `EquationSolver` phép chia (`utils/EquationSolver.java:155`); cộng **#128**: `NewEditTransactionActivity.java:809` tạo `MoneyPicker` với `currency=null` → `EquationSolver.getResult()` (`:177-186`) bỏ qua `movePointRight(decimals)` → lưu 100 thay vì 10000.
- **Fix:** chuyển sang BigDecimal + `HALF_UP` ở cả 3 chỗ + truyền đúng currency (fallback default) cho MoneyPicker + unit test table-driven (~40 case).
- **Effort:** 1 ngày. **Bắt buộc fix trước tính năng vàng** (sai số vàng nghiêm trọng hơn sai tiền).

### #197 — Restore chỉ ra subset dữ liệu
- **Hiện trạng:** chưa fix. Backup đủ nhưng restore được ~20–30 dòng, không báo lỗi rõ.
- **Root cause:** 1 bảng lỗi → abort toàn bộ restore giữa chừng, không báo cáo.
- **Fix:** per-table try/catch + báo cáo cuối ("22/24 bảng OK, lỗi ở..."); auto-backup JSON trước khi restore đè (P1).
- **Effort:** 1–2 ngày.

---

## 🟡 Medium

### #195 — Calculator hiện `1.0E7` với số lớn
- **Hiện trạng:** chưa fix. Sửa transaction số tiền ≥ 10^7 thì ô nhập hiện dạng exponent.
- **Root cause:** `EquationSolver.setValue()` (`utils/EquationSolver.java:67`): `String.valueOf(money / Math.pow(10, decimals))` → `Double.toString` ra exponent.
- **Fix:** 1 dòng — `BigDecimal.valueOf(money).movePointLeft(decimals).toPlainString()`.
- **Effort:** 15 phút.

### #211 — CSV import crash vì định dạng ngày
- **Hiện trạng:** chưa fix. `ParseException: Unparseable date` → abort toàn bộ file.
- **Root cause:** `CSVDataImporter.java:69` → `getDateFromSQLDateTimeString` ném RuntimeException khi chuỗi không khớp `yyyy-MM-dd HH:mm:ss` (Excel tự reformat cột ngày khi user mở/save lại).
- **Fix:** parser thử nhiều format + skip dòng lỗi có báo cáo, không abort cả file.
- **Effort:** 0.5 ngày.

### #161 — CSV import làm mất transfer
- **Hiện trạng:** chưa fix (thiết kế). Transfer export thành 2–3 dòng transaction thường; import tạo category "transfer" mới thay vì tái tạo transfer.
- **Fix ngắn hạn:** cảnh báo rõ trong UI import (CSV không khôi phục transfer/debt/recurrence — dùng JSON backup). Fix triệt để (matching heuristic) để backlog.
- **Effort:** 0.5 ngày (cảnh báo) / 3–5 ngày (rebuild).

### #253 — Không thấy file CSV để import (Android 10+)
- **Hiện trạng:** chưa fix. File explorer tự viết không liệt kê được thư mục ngoài vùng app (scoped storage).
- **Fix:** chuyển sang SAF (`ACTION_OPEN_DOCUMENT`/`ACTION_CREATE_DOCUMENT`) — trùng việc P0 roadmap.
- **Effort:** 1 ngày.

### #305 — Mất nhiều năm transactions
- **Hiện trạng:** chưa fix, cần thêm thông tin từ reporter (checklist: số dư ví, tìm kiếm transaction cũ, kích thước DB, thử backup JSON).
- **Effort:** 0.5 ngày xác minh.

### #258 — Cloud backup (Dropbox) cứ đòi disconnect/reconnect liên tục
- **Hiện trạng:** chưa fix. Token hết hạn sau vài giờ → backup fail → dialog đòi disconnect.
- **Root cause:** `DropboxBackendService.getAccessToken()` (`api/dropbox/DropboxBackendService.java:105`) chỉ lưu access token, không xử lý refresh token (Dropbox khai tử long-lived token từ 2021; SDK 3.0.8 quá cũ).
- **Fix:** upgrade Dropbox SDK + implement refresh-token flow. Làm cùng đợt với #192.
- **Effort:** 1–2 ngày.

### #192 — Google Drive backup không hoạt động
- **Hiện trạng:** chưa fix. Báo `Drive.API_CONNECTIONLESS is not available`.
- **Root cause:** dùng Google Drive Android API đã bị Google shutdown (`GoogleDriveBackendServiceAPI.java:66`).
- **Fix:** migrate sang Drive REST API v3 (fork MWPlus đã làm được) hoặc bỏ Drive. Gắn roadmap P5.
- **Effort:** lớn (vài ngày đến 1–2 tuần).

---

## 🟢 Low

### #200 — Mũi tên back không lật ở ngôn ngữ RTL
- **Fix:** thêm `android:autoMirrored="true"` vào `ic_arrow_back_black_24dp.xml`. 5 phút.

### #201 — Phím số calculator không theo locale
- Hiển thị + parse digit theo locale (hiện chỉ ASCII). Backlog.

### #219 — Chữ tối trên nền tối (dark theme)
- Không pinpoint được view cụ thể; audit màu hardcode trong đợt UI modernization (P5), không fix mù.

---

## Đề xuất kỹ thuật (chưa làm, đúng hướng)

- **#155 — Chuyển raw sqlite → Room:** agent đánh giá độc lập: NÊN LÀM. Chính là Phase 1–3 roadmap.
- **#243 — Upgrade gradle & dependencies:** chính là Phase 0 roadmap.

---

## Đã loại khỏi backlog (lý do)

| Issue | Lý do loại |
|---|---|
| #144 data export EPERM | Đã fix bởi PR #150 (verify trong code: filename không còn dấu `:`) |
| #302 Can't edit/delete categories | Không phải bug — menu đã có sẵn, chỉ là UX khó phát hiện |
| #250 Restore backup | Câu hỏi user, cộng đồng đã trả lời |
| #140 Auto Backup Error | Không tái hiện được (2020, Android 7); backend đã thay từ đó |
| #131 Extra column in export | Feature request (thêm cột balance), không phải bug — để backlog P5 |
| #120 Wrong calculator screen | By design (maintainer xác nhận calculator là extended keyboard có chủ ý) |
| #186 The minus sign | Cần quyết định sản phẩm (hiển thị số âm), chưa consensus — quyết sau |
| #291 Delete transaction from search | Feature request UX hợp lệ — backlog P5 |
| #132 "Bug" | Một nửa duplicate #128, nửa còn lại by-design (filter event theo ngày) |
| #136 Daily Auto backups | Duplicate #67, đã có câu trả lời |
| #218 Categories for debt and credit | Feature request; reporter đã chuyển sang app khác |

---

## Thứ tự fix đề xuất (gắn roadmap)

1. **Hotfix #177/#221** (0.5 ngày) — trước mọi thứ
2. **1-cent bugs** (1 ngày) — bắt buộc trước tính năng vàng (P2)
3. **#303** (3 giờ) — kèm test round-trip khóa họ bug thiếu field
4. **#197** (1–2 ngày) — trong P1 (Room/backup)
5. **#298** (1–2 ngày) — trong P3 (Repository `@Transaction`)
6. **#211** (0.5 ngày), **#253** (1 ngày, trong P0), **#161** (cảnh báo UI)
7. **#305** — xác minh với reporter
