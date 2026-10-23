# Human–agent development và duy trì fork

Ngày: 2026-10-20. Áp dụng bổ sung cho AGENTS.md, không thay thế startup protocol hay build safety contract.

## Phân công

| Human/dev | Agent |
|---|---|
| Chọn ưu tiên, quyết kiến trúc/boundary, cung cấp dữ liệu mẫu đã ẩn danh | Đọc context, kiểm tra source, chuẩn bị bằng chứng và phương án |
| Chạy build/device/restore, đánh giá UX và số liệu nghiệp vụ | Implement task đã giao, viết test cần thiết, review diff và đưa lệnh kiểm chứng |
| Chấp nhận baseline, chuyển milestone, cho phép release | Ghi trạng thái thật, cập nhật docs khi có quyết định, đề xuất task kế tiếp |

Human không phải duyệt lại mỗi edit nhỏ đã được giao. Agent không dùng sự im lặng để suy ra một quyết định kiến trúc hoặc quyền publish.

## Một vòng làm việc

1. Load context theo AGENTS; đọc plan khi task thuộc plan đó.
2. Tạo task card ngắn có acceptance; nếu đã rõ hướng thì CODE_NOW, không chặn bằng plan dài.
3. Thay đổi một mục tiêu nghiệp vụ/kỹ thuật mỗi đợt; tránh trộn upstream, refactor và feature. Mặc định ≤5 file; nếu cần nhiều hơn, ghi lý do phạm vi liên kết.
4. Self-review diff: behavior, data, errors, permissions, secrets, encoding và tương thích dữ liệu cũ.
5. Ghi kiểm chứng đã chạy và chưa chạy. Human thực hiện runtime theo lệnh/checklist; agent chỉ sửa vòng tiếp sau khi có output hoặc task mới rõ ràng.
6. Hoàn tất acceptance rồi mới đánh DONE; cập nhật decision/context cùng đợt nếu premise thay đổi.

Trạng thái task: TODO → IN_PROGRESS → WAITING_HUMAN (nếu cần quyết định/output) → DONE. BLOCKED phải có nguyên nhân và điều kiện mở khóa. Không đánh DONE chỉ vì code đã viết.

## Task card

```markdown
## Context
Task ID; milestone; plan; baseline SHA; context/module đã đọc.
## Goal
Một kết quả quan sát được.
## Constraints / Invariants
Dữ liệu, API, permission, compatibility cần giữ.
## Allowed
Phạm vi files/layer và quyết định đã được phép.
## Forbidden
Những thay đổi nằm ngoài task.
## Acceptance
Input → expected output; kiểm chứng nào agent làm, phần nào human chạy.
## Known Tensions
ID tension hoặc không có; unknown không được giả định là fact.
## Handoff
Trạng thái; diff/commit; evidence; lệnh chưa chạy; lỗi còn lại; bước tiếp theo.
```

## Bằng chứng và kiểm thử

- Phân biệt FACT (đã kiểm chứng tại ref), PROPOSAL (chưa quyết), UNKNOWN và APPROVED (decision + phạm vi). Câu “đã có/chưa có trong repo” phải có tìm kiếm trước.
- Test tập trung vào rủi ro: tiền/làm tròn, write orchestration, schema/restore, failure path. Không thêm test chỉ lặp implementation hoặc cho chỉnh sửa docs đơn giản.
- Code cũ làm oracle cho behavior cần giữ; bug đã biết phải có expected result đúng được ghi rõ, không bắt implementation mới tái hiện bug để pass.
- Luôn ghi commit/command/result cho evidence. “Chưa chạy”, “không tái hiện” và “pass” là ba trạng thái khác nhau.
- Không tự chạy build/lint; command im lặng/timeout/tool kill thì dừng và giao exact command cho human, không retry/poll.

## Quản lý quyết định và tài liệu

- `.docs/ideations/`: ý tưởng và research; không phải lệnh triển khai.
- `docs/plans/`: work packages, dependencies và acceptance.
- `docs/decisions/`: decision có evidence; `.context/`: facts/invariants đang áp dụng.
- Chỉ cập nhật những nơi bị quyết định tác động. Không copy nguyên ideation vào context và biến claims chưa kiểm chứng thành invariants.
- Khi human chuyển milestone, cập nhật và archive đúng AGENTS.md; không tự renumber roadmap khi merge upstream.

## Quan hệ upstream

- Fork tự chịu trách nhiệm cho code do AI hỗ trợ: human review, kiểm chứng, provenance và maintenance vẫn bắt buộc.
- Giữ lịch sử, license và attribution theo nguồn đã kiểm chứng. Không nhận công upstream là phần tự viết.
- Trước đề xuất đóng góp, đọc contribution policy tại upstream; tuân thủ yêu cầu về AI nếu có. Không gửi issue/PR/comment khi chưa được human yêu cầu; không che giấu việc dùng AI để vượt chính sách.
- Không tự đồng bộ vào nhánh chính. Pin commit, đọc diff, ghi phần lấy/bỏ và lý do; chỉ tích hợp các thay đổi đã qua review tương ứng.

## Upstream ledger và release handoff

Từ TB-01, báo cáo mỗi đợt tiếp nhận lưu dưới `docs/plans/evidence/<task-id>.md` (chỉ dữ liệu không nhạy cảm). Tạo khi có evidence thực, không điền placeholder làm kết quả.

Mỗi entry chứa: local base SHA, upstream URL/tag/SHA, ngày review, commits/features nhận hoặc bỏ, conflict resolutions, dependency/license delta, test logs tham chiếu, known regressions, decision và rollback ref.

Trước release: gắn artifact với commit, ghi kết quả build/runtime, compatibility/restore, known issues và hướng khôi phục. Version/signing/publish chỉ đổi trong phạm vi human đã cho phép. Không gộp đồng ý sửa code với đồng ý phát hành.
