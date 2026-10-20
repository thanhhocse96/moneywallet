# AGENTS_MODULES.md — MoneyWallet
# Module-Specific Rules
# Đọc section liên quan đến module đang làm việc. Không cần đọc toàn bộ file.

---

## Module-Specific Rules

### Data layer (MODULE_DATA_LAYER.md)

- `SQLDatabase`, `ContentProvider`, `Contract` — không thay đổi schema cũ mà không migration test.
- Dùng `selectionArgs`, KHÔNG concat chuỗi vào SQL.
- Migration Room (nếu có) phải có test trên `.db` thật.
- Auto-backup JSON trước lần đầu Room mở DB cũ (theo roadmap P1).

### UI layer (MODULE_UI.md)

- Activity/Fragment, Loader (hiện tại), ViewModel+Flow (roadmap P4).
- Không xóa `DataContentProvider`, `SyncContentProvider`, `SQLDatabase`, `SQLCache`, `Contract`, `MultiUriCursorWrapper` khi chưa có test oracle pass.
- Migrate từng màn hình theo pattern đã chuẩn hóa.

### Backup layer (MODULE_BACKUP.md)

- SAF (Storage Access Framework), Google Drive, Dropbox — không abort app khi lỗi.
- Không hardcode API key; lưu trong `gradle.properties` / `local.properties`, KHÔNG commit.
- `USE_FINGERPRINT` → Biometric API (`USE_BIOMETRIC`).

### Flavors (MODULE_FLAVORS.md)

- `floss`/`proprietary` × `gmap`/`osm`; giữ build khả thi trên mọi combo.
- `proprietary`: chứa Google Drive + Dropbox, yêu cầu API-key hợp lệ trong `gradle.properties`.
- `floss`: chỉ open source, không có Drive/Dropbox.
- `gmap`: dùng Google Map, yêu cầu API-key.
- `osm`: dùng OpenStreetMap.
- Bản release hiện tại dùng `proprietary` + `osm` + Crashlytics + In-App billing.

### Calculator / Formatter (MODULE_CALC.md)

- Không dùng `double` rồi truncate về `long` (bug mất 1 cent). Chuyển sang `BigDecimal` + `HALF_UP`.
- `MoneyFormatter.normalize()`, `CurrencyConverterPicker.convert()`, `EquationSolver` — kiểm tra kỹ trước khi sửa.
