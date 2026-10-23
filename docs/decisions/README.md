# docs/decisions/ — MoneyWallet
# Decision records (ADR). Tiền tố hai chữ số tăng tuần tự theo thứ tự tạo.

## Tình trạng hồ sơ

Kiểm tra 2026-10-20: thư mục chỉ có README và `00-template.md`. Tên 01–06 dưới là danh mục dự kiến, **không phải decision record đã tồn tại**. ADR-7/8 trong ideation không tự thành hồ sơ được duyệt.

Scope theo `.context/MILESTONES.md`; UI human xác nhận ở `docs/standards/ui-design-direction.md`. Không dùng mục SDK/flavor/license cũ dưới đây để tự thay dependency, bỏ flavor hoặc đưa kết luận pháp lý.

## Danh mục lịch sử/dự kiến (không phải danh sách file hiện có)

| STT | File | Nội dung |
|---|---|---|
| 00 | `00-template.md` | Mẫu decision record |
| 01 | `01-adr-1-java-to-kotlin.md` | ADR-1: Thay thế thay vì convert Java→Kotlin hàng loạt |
| 02 | `02-adr-2-datetime-text.md` | ADR-2: Giữ ngày giờ dạng TEXT `"yyyy-MM-dd HH:mm:ss"` |
| 03 | `03-adr-3-gold-unit.md` | ADR-3: Đơn vị lưu trữ vàng = phân (INTEGER), decimals = 2 |
| 04 | `04-adr-4-vau-currency.md` | ADR-4: Không dùng ISO `XAU` → dùng `VAU` |
| 05 | `05-adr-5-sdk-flavor.md` | ADR-5: minSdk 26, targetSdk 35/36; bỏ flavor proprietary/gmap |
| 06 | `06-adr-6-license.md` | ADR-6: GPL v3 + iText AGPL license |

## Quy tắc đặt tên

`00-<ten-quyet-dinh>.md`, số tăng tuần tự. Trước khi tạo mới, kiểm tra số lớn nhất hiện có và tăng thêm 1.
