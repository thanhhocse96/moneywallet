# .context/GLOBAL.md — MoneyWallet
# Stack, module index, invariants, phase scope

## Stack

- Ngôn ngữ: Java (hiện tại), Kotlin (roadmap P1+)
- Build: Gradle (AGP 4.0.1 → cần nâng cấp)
- Min SDK: 21, Target SDK: 29 (cần nâng lên 35/36 theo roadmap P0)
- Flavors: floss/proprietary × gmap/osm
- Database: SQLite qua `SQLDatabase` + `ContentProvider` (hiện tại), Room (roadmap P1)
- UI: Activity/Fragment + Loader (hiện tại), ViewModel+Flow (roadmap P4)
- Backup: SAF, Google Drive, Dropbox (proprietary flavor)
- Map: Google Maps (gmap), OpenStreetMap (osm)

## Module index

| Module | File | Mô tả |
|---|---|---|
| Data layer | `.context/modules/MODULE_DATA_LAYER.md` | SQLDatabase, ContentProvider, Contract, migration |
| UI layer | `.context/modules/MODULE_UI.md` | Activity/Fragment, Loader, ViewModel+Flow |
| Backup layer | `.context/modules/MODULE_BACKUP.md` | SAF, Drive, Dropbox, permissions |
| Flavors | `.context/modules/MODULE_FLAVORS.md` | floss/proprietary × gmap/osm |
| Calculator | `.context/modules/MODULE_CALC.md` | MoneyFormatter, EquationSolver, BigDecimal |

## Invariants

- Package `com.oriondev.moneywallet` — không đổi.
- Không hardcode secret/API key trong source.
- SQL query dùng `selectionArgs`, không concat.
- Không commit `build/`, `.gradle/`, `local.properties`, `*.keystore`, `key.properties`.
- Không sửa code cũ khi chưa có test oracle pass.
- UTF-8 everywhere, tiếng Việt không mojibake.

## Phase scope (theo roadmap)

| Phase | Nội dung | Trạng thái |
|---|---|---|
| P0 | Toolchain & compliance | Current |
| P1 | Room core + validate trên `.db` thật | Upcoming |
| P2 | Vertical slice: currency + vàng trên stack mới | Upcoming |
| P3 | Port write orchestration sang Repository | Upcoming |
| P4 | Migrate UI: Loader → Flow, xóa Provider | Upcoming |
| P5 | UI modernization (M3, thay lib chết) | Upcoming |
| P6 | Vàng phase 2: giá tự động | Upcoming |
