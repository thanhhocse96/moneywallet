# Hướng thiết kế UI MoneyVibe

Status: hướng sản phẩm được human xác nhận ngày 2026-10-20; chi tiết implementation chưa chọn.

Đọc kèm [digest artifact](ui-artifact-digest.md) trước task UI. “Apple-like island” là mô tả hướng thị giác; tên pattern Apple gần nhất cho list nhóm bo góc là **Inset Grouped**. Không có tên chính thức duy nhất cho toàn bộ artifact; không gọi nó là Liquid Glass. Hai variant khác cả bố cục, không chỉ màu theme.

## Yêu cầu đã xác nhận

**Theme + Material 3 + minimalism + Apple-like island.** Đây là yêu cầu trải nghiệm, không chỉ thay library hoặc đổi màu Material.

- Theme: hệ token dùng chung cho màu, chữ, khoảng cách, shape, elevation; không hardcode style riêng cho từng màn hình.
- Material 3: nền component/tương tác Android; audit phần kế thừa trước khi bổ sung.
- Minimalism: phân cấp rõ, ưu tiên số tiền và thao tác chính, tiết chế trang trí, giữ thông tin nghiệp vụ cần thiết.
- Apple-like island: hướng thị giác thể hiện qua màn hình mẫu. Prototype có nhóm nội dung dạng island; đây là cơ sở đề xuất, chưa khóa hình học, animation hay vị trí.

## Artifact tham chiếu

- `.docs/ideations/ui/Money Lover Redesign Preview (3).html`: hai variant vibrant/minimal, bốn màn hình; caption Transactions mô tả island theo tuần, source có comment “one island per week”.
- `.docs/ideations/ui/tag-merge-ui-prototype.html`: Material 3 minimal cho chọn tag và merge preview.

HTML là concept, không phải implementation Android hoặc bằng chứng theme đã hoàn thành. `.island` trên khung điện thoại mô phỏng cutout; chưa có yêu cầu xây Dynamic Island overlay/service hoặc mô phỏng phần cứng iPhone trong app.

## Task thiết kế khi triển khai UI

1. Inventory theme/components thực từ baseline.
2. Đề xuất tokens và theme modes (light/dark/system, preset nếu cần); mode, picker, persistence xác định trong task, không suy ra từ hai variant HTML.
3. Dựng màn hình mẫu với số tiền dài/âm, nhiều currency, tiếng Việt, font lớn và keyboard.
4. Human kiểm tra hình thức/tương tác trước khi nhân rộng; ghi lựa chọn để agent sau không tự đổi style.
5. Rollout từng màn hình; View/XML/Compose là lựa chọn sau audit, không tự động rewrite UI.

## Acceptance

- Tokens nhất quán; đổi theme không sửa dữ liệu/nghiệp vụ.
- Số tiền, dấu âm, currency và hành động chính rõ ràng trong mọi theme đã chọn.
- Island nhóm nội dung có mục đích, không che dữ liệu/cản điều hướng.
- Kiểm tra contrast, font scale, touch targets, focus/accessibility labels, insets và keyboard.
- Preview và kết quả kiểm chứng gắn commit; thêm dependency Material chưa đủ để đánh DONE.
