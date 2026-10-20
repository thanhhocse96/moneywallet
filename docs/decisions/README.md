# docs/decisions/ — MoneyWallet
# Decision records (ADR). Tiền tố hai chữ số tăng tuần tự theo thứ tự tạo.

## Danh sách decision (theo roadmap)

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
