# .context/modules/MODULE_DATA_LAYER.md — MoneyWallet
# Data layer: SQLDatabase, ContentProvider, Contract

[manual]
- `SQLDatabase`, `ContentProvider`, `Contract` — không thay đổi schema cũ mà không migration test.
- Dùng `selectionArgs`, KHÔNG concat chuỗi vào SQL.
- Migration Room (nếu có) phải có test trên `.db` thật.
- Auto-backup JSON trước lần đầu Room mở DB cũ (theo roadmap P1).
[/manual]

### Tables (24 bảng theo schema hiện tại)

- `wallet`, `transaction_item`, `person`, `category`, `budget`, `saving`, `debt`, `recurrence`, `currency`, `exchange_rate`, `attachment`, và các junction table...

### Rules

- Mọi query ghi đọc qua `ContentProvider` hoặc `SQLDatabase` trực tiếp.
- Không dùng raw SQL concat với user input.
- FK cascade đúng như schema gốc.
- Migration 3→4: thêm `CREATE INDEX` cho các cột FK (DB cũ không có index).
