# .context/modules/MODULE_UI.md — MoneyWallet
# UI layer: Activity/Fragment, Loader, ViewModel+Flow

[manual]
- Activity/Fragment, Loader (hiện tại), ViewModel+Flow (roadmap P4).
- Không xóa `DataContentProvider`, `SyncContentProvider`, `SQLDatabase`, `SQLCache`, `Contract`, `MultiUriCursorWrapper` khi chưa có test oracle pass.
- Migrate từng màn hình theo pattern đã chuẩn hóa.
- Hướng human xác nhận: theme + Material 3 + minimalism + Apple-like island; theo `docs/standards/ui-design-direction.md`.
[/manual]

### Rules

- Trước task thiết kế/implement UI, đọc `docs/standards/ui-artifact-digest.md`: phân biệt grouped cards với list phẳng, variant với theme, app canvas với khung mockup. Inset Grouped là pattern tham chiếu, không phải yêu cầu dùng iOS framework.

- Vertical slice chọn sau audit baseline; không mặc định currency/vàng.
- Inventory consumer `LocalBroadcastManager` và `startActivityForResult` theo SHA thực trước thay/xóa; số file trong ideation là lịch sử.
- Theme là hệ tokens/components nhất quán; Material dependency không đủ đánh dấu UI hoàn tất.
- Mỗi màn hình migrate có checklist test tay.
- Grep toàn bộ `CONTENT_` trước khi xóa provider.
