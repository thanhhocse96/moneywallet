# .context/modules/MODULE_UI.md — MoneyWallet
# UI layer: Activity/Fragment, Loader, ViewModel+Flow

[manual]
- Activity/Fragment, Loader (hiện tại), ViewModel+Flow (roadmap P4).
- Không xóa `DataContentProvider`, `SyncContentProvider`, `SQLDatabase`, `SQLCache`, `Contract`, `MultiUriCursorWrapper` khi chưa có test oracle pass.
- Migrate từng màn hình theo pattern đã chuẩn hóa.
[/manual]

### Rules

- Màn hình đầu tiên migrate sang ViewModel+Flow là currency (P2 vertical slice).
- Xóa `LocalBroadcastManager` (36 files) khi migrate xong.
- Xóa `startActivityForResult` (14 files) → Activity Result API.
- Mỗi màn hình migrate có checklist test tay.
- Grep toàn bộ `CONTENT_` trước khi xóa provider.
