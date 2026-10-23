# Audit sai biệt Ideation ↔ governance

Ngày: 2026-10-20. Phạm vi: docs/governance local; không audit upstream hoặc chạy app.

## Kết luận

Governance sao chép roadmap MoneyWallet cũ thành checklist thực thi, trong khi ideation chuyển sang tallybook/MoneyVibe và có thêm feature/design. Các đề xuất/claims nghiên cứu bị trình bày như facts hoặc quyết định. Plan tiếp nhận lượt trước còn giữ checklist cũ nên chưa xử lý triệt để sai biệt.

Human xác nhận theme, Material 3, minimalism, Apple-like island và phản đối checklist giá vàng tự động. Đợt này sửa ngay scope đã rõ, không chờ audit upstream.

## Ma trận sai biệt

| Vấn đề | Evidence / nguồn đối chiếu | Xử lý |
|---|---|---|
| Giá vàng tự động thành P6 | Roadmap mục Phase 6; MILESTONES/AGENTS/GLOBAL cũ; overview mục 8 bỏ vàng | Bỏ checklist đang giao việc, ghi ngoài scope; không xóa code vàng hoặc khẳng định đã implement |
| P2 khóa vào vàng/currency | Roadmap Phase 2, MODULE_UI cũ | Giữ slot vertical slice, domain chọn sau baseline |
| UI chỉ M3/thay lib | Checklist P5 cũ so với yêu cầu human và HTML redesign | Standard theme/M3/minimal/island + acceptance, áp dụng UI mới xuyên suốt |
| Hai nghĩa island | HTML redesign `.island` dòng 31, caption dòng 76, comment dòng 160 | Phân biệt cutout trang trí với nhóm nội dung; không tự tạo overlay feature |
| Hai hệ phase | Roadmap P0–P6, overview P0–P4 | Giữ current P0; MILESTONES làm nguồn scope, không renumber/archive |
| Checklist toolchain giả định baseline cũ | GLOBAL và app/build.gradle; overview nói upstream làm phần lớn | P0 audit gap + TB-01–07; version cụ thể chọn sau baseline |
| Bỏ flavor trái manual | MILESTONES cũ so MODULE_FLAVORS/build safety | Bỏ lệnh xóa vô điều kiện; giữ gate TB-02, chưa sửa source nên không tạo HIGH tension cho thao tác tương lai |
| Schema/version hardcode | Data analysis 24 bảng v3; overview 27 bảng v10; SQLDatabase hiện DATABASE_VERSION=3 | Inventory theo SHA/DB thật, phân biệt bảng ứng dụng/cache/hệ thống; bỏ số cứng khỏi acceptance |
| Tên domain bị dùng như SQL | MODULE_DATA_LAYER cũ so Schema.java (wallets/transactions/currencies) | Dẫn source schema thực, bỏ danh sách tên sai |
| Room index premise chưa đủ nguồn | Data analysis mục 5 và roadmap P1 kết luận thiếu FK index luôn fail | Không promote; yêu cầu docs đúng version/test, chưa kết luận behavior thay thế |
| Backlog lịch sử thành hiện trạng | Backlog Critical/High so overview mục 9 | Tái xác minh tại SHA, không mặc định hotfix hoặc fixed |
| Thiếu feature intake | Specs tag, scale, icon so milestone cũ | Thêm intake/prerequisites, không tự lên lịch tất cả ở P2 |
| ADR/plan file giả định tồn tại | `rg --files docs/decisions docs/plans` so README | ADR index ghi rõ dự kiến; plan index chỉ giữ artifact thực |
| Cấm mọi sửa code cũ | GLOBAL “không sửa” so AGENTS/UI “không xóa” trước oracle | Bảo vệ thay thế/xóa; bugfix có regression, không giữ bug làm expected đúng |
| License/SDK thành kết luận tắt | ADR-5/6 roadmap và overview khác premise | Gỡ kết luận tắt khỏi active milestone; kiểm kê license/dependency ở TB-01, không đưa kết luận pháp lý mới |

## Nội dung chưa thể coi là đã chốt

- **Tag:** prose/regex khác phạm vi dấu `-`; forward-only vừa “Quyết” vừa câu hỏi mở; split_note đã chốt ở overview nhưng mở trong spec. Schema ba bảng, checklist ghi hai. Merge UPDATE có nguy cơ trùng composite key khi giao dịch chứa cả hai tag: cần dedupe/test nguyên tử, chưa tự sửa semantics.
- **Migration:** Room và tag cùng nhắm v11 ở thời điểm khác nhau; cần thứ tự release/migration thực.
- **Scale:** phải rõ typed × scale × minor-unit factor khi currency có decimals; test làm tròn/overflow. Conversion legacy/cross-wallet cần task riêng.
- **Icon:** claim “TEXT tự backup” cần kiểm tra exporter/importer và whitelist cột/bảng mới; SVG transforms/emoji cần fixture, không coi spec ngắn là implementation đầy đủ.
- **KMP:** “không tốn effort” và commonMain trong evaluation chưa là constraint kiểm chứng theo dependency/API baseline.
- **Theme:** hướng đã rõ; số preset/mode, picker, tokens, motion/hình học island chọn qua màn hình mẫu, không suy ra hai variant HTML thành hai theme bắt buộc.
- **Upstream:** SHA, bugfix, backup compatibility, iText removal và M3 status xử lý ở TB-01; chưa xác minh trong đợt governance này.

## Phạm vi và kiểm chứng

- Sửa hơn 5 file có chủ đích vì scope lặp ở AGENTS/GLOBAL/MILESTONES/module/index/plan; sửa một nơi sẽ để chỉ dẫn trái nhau.
- Giữ research gốc, thêm banner; không archive milestone/tensions. Giữ manual về dữ liệu, backup và flavors.
- Không thay source/build/dependency, chạy Gradle hoặc gửi upstream.
- Kiểm chứng bằng grep scope/phase/reference, `git diff --check`, UTF-8 strict. Upstream/runtime không thuộc kết luận pass.

## Tiếp theo

TB-01 pin/audit baseline. Unresolved spec là input cho task tương ứng, không yêu cầu human quyết tất cả ngay. Không xin lại xác nhận scope giá vàng tự động/hướng UI đã rõ.
