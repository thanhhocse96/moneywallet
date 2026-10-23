# .context/modules/MODULE_DATA_LAYER.md — MoneyWallet
# Data layer: SQLDatabase, ContentProvider, Contract

[manual]
- `SQLDatabase`, `ContentProvider`, `Contract` — không thay đổi schema cũ mà không migration test.
- Dùng `selectionArgs`, KHÔNG concat chuỗi vào SQL.
- Migration Room (nếu có) phải có test trên `.db` thật.
- Auto-backup JSON trước lần đầu Room mở DB cũ (theo roadmap P1).
[/manual]

### Schema source of truth

- Inventory từ `storage/database/Schema.java` và DB thật tại SHA được chọn; không dùng tên domain rút gọn làm tên SQL. Source hiện tại dùng `wallets`, `transactions`, `currencies`.
- Không hardcode 24/27 bảng từ ideation cho acceptance; ghi danh sách bảng/cột/default/FK/index thực trong báo cáo baseline.

### Rules

- Mọi query ghi đọc qua `ContentProvider` hoặc `SQLDatabase` trực tiếp.
- Không dùng raw SQL concat với user input.
- FK cascade đúng như schema gốc.
- Migration version và indices theo schema baseline/target thực; test với Room version đã chọn. Không mặc định thiếu index FK luôn gây validation failure từ research cũ.
