# .context/MILESTONES.md — MoneyWallet / MoneyVibe
# Source of truth cho scope và trạng thái; ideation không tự cấp quyền triển khai.

Current milestone: **P0 — Toolchain & compliance**

## Scope đã cập nhật ngày 2026-10-20

- Human chọn hướng tiếp nhận tallybook và duy trì fork bằng human–agent theo từng bước.
- UI đã xác nhận: **theme + Material 3 + minimalism + Apple-like island**; xem `docs/standards/ui-design-direction.md`.
- **Giá vàng tự động ngoài scope**: không có checklist API/scrape/worker giá vàng; không tự khôi phục từ roadmap cũ.
- Không giao xây lại vàng như vertical slice mặc định. Ideation ghi vàng đã làm riêng; TB-01 phải tìm artifact nếu cần bảo toàn, không coi là bằng chứng code đã nằm trong repo.
- Vẫn P0, không chuyển milestone/archive tensions hoặc tự renumber theo ideation 5 phase. Các phase tương lai là định hướng, chưa phải quyền triển khai mọi hạng mục.

## P0 — Tiếp nhận tallybook, toolchain & compliance

Plan: `docs/plans/000_P0_TALLYBOOK_ADOPTION_PLAN.md`. Workflow: `docs/standards/human-agent-development.md`.

- [ ] TB-01: audit local/upstream, pin SHA, xác minh schema/toolchain/backend/dependency/license/contribution policy.
- [ ] TB-02: quyết thay đổi dependency/flavor/backend/applicationId/signing/version có bằng chứng.
- [ ] TB-03: tích hợp trên nhánh riêng, giữ lịch sử/docs/phần riêng; ghi conflict resolutions.
- [ ] TB-04: human chạy build/lint/test và smoke test trên baseline ứng viên.
- [ ] TB-05: human kiểm chứng restore/upgrade trên bản sao và backup round-trip.
- [ ] TB-06: cập nhật context và audit lại backlog theo SHA được chấp nhận.
- [ ] TB-07: chuẩn bị task dev nhỏ đầu tiên có acceptance và rollback.

Audit P0 gồm SDK/JDK/Gradle, repositories, hidden API, scoped storage, biometric, service/alarm permissions và release configuration. Chỉ lập task sửa phần còn thiếu đã xác minh; không mặc định bump version, bỏ flavor hay thay dependency từ checklist cũ.

**Exit:** human chấp nhận baseline sau log build theo variant thực, smoke/restore đạt; thay đổi hành vi đã được quyết; context khớp source. Không tuyên bố đạt chuẩn Play Store nếu chưa kiểm chứng yêu cầu phát hành tại thời điểm đó.

## P1 — Room core + validation (sau baseline)

- [ ] Inventory schema thật: bảng/cột/default/FK/index và DB version tại SHA đích.
- [ ] Thiết kế entities/DAO giữ tên và semantics; ngày giờ TEXT theo invariant hiện hành.
- [ ] Chọn migration version theo baseline và thứ tự release; không hardcode 3→4 hay 10→11 từ ideation.
- [ ] Export schema; test DB rỗng/có dữ liệu/sau restore, đối chiếu số dòng và giá trị nghiệp vụ.
- [ ] Backup trước lần đầu backend mới mở DB cũ; kiểm chứng recovery.
- [ ] Xác minh khả năng KMP theo dependency/version thực trước quyết định shared module.

**Exit:** migration và round-trip đạt trên bộ mẫu thống nhất, không mất dữ liệu. Premise về Room validation/index phải được kiểm chứng bằng nguồn đúng version và test.

## P2 — Vertical slice trên stack mới (chưa chọn domain)

- [ ] Chọn một luồng end-to-end nhỏ sau TB-06.
- [ ] Chốt semantics, dữ liệu, màn hình mẫu và acceptance trước code.
- [ ] Chứng minh DAO/repository → ViewModel/state → UI và regression với hành vi cần giữ.

Không mặc định vàng/currency. Tag và currency scale là ứng viên từ ideation, chưa phải lựa chọn được duyệt.

## P3 — Repository write orchestration

- [ ] Inventory transfer, debt, budget, saving, recurrence, split nếu có theo baseline.
- [ ] Port theo aggregate, bảo đảm atomicity và failure recovery.
- [ ] Characterization test DB state, kèm expected result đúng cho bug đã biết.
- [ ] Giữ Provider làm cầu nối khi còn consumer; chỉ bỏ code sau test oracle phù hợp.

## P4 — Migrate UI data flow

- [ ] Chuẩn hóa pattern từ vertical slice; chuyển từng màn hình sang ViewModel + Flow.
- [ ] Inventory rồi thay Loader/broadcast/activity-result cũ; không dùng số file lịch sử làm acceptance.
- [ ] Kiểm tra consumer và regression trước khi xóa Provider/cache/Contract.

## P5 — Theme và thiết kế trải nghiệm

Hướng thiết kế áp dụng cho UI mới ngay khi làm, không phải chờ P5 mới có theme.

- [ ] Audit theme/components kế thừa; không mặc định tallybook đáp ứng thiết kế MoneyVibe.
- [ ] Tokens màu, typography, spacing, shape, elevation dùng chung; xác định modes/theme và preference trong task thiết kế.
- [ ] Material 3 làm nền component; minimalism và Apple-like island định hình bố cục/phân cấp.
- [ ] Màn hình mẫu Transactions / New transaction / Budgets / Overview và tag merge đối chiếu prototype trước rollout.
- [ ] Kiểm chứng số tiền dài/âm, font scale, contrast, touch targets, keyboard/insets, empty/loading/error.
- [ ] Chọn View/XML/Compose và thay lib theo nhu cầu đã kiểm chứng; danh sách thay lib không thay thế mục tiêu thiết kế.

**Exit từng slice:** human kiểm chứng hình thức/tương tác; theme nhất quán, nghiệp vụ và accessibility không regress.

## Feature intake từ ideation — chưa tự lên lịch release

| Feature | Nội dung giữ khi lập task | Điều kiện trước implementation |
|---|---|---|
| Tag/hashtag | Text là nguồn sự thật; parse-on-write; merge/rename/alias nguyên tử | Grammar, split-note attribution, history scan, dedupe khi merge và migration thống nhất |
| Currency scale | DB lưu tiền thật; scale chỉ nhập/hiển thị | Minor units, làm tròn/overflow; conversion legacy là task riêng có preview và backup |
| Icon | Pack → SVG/emoji → raster tùy nhu cầu | Chốt pack/format; xác minh backup/export cột mới và file |

Nguồn: `.docs/ideations/02-specs/`. Thứ tự feature chưa quyết; không tự nhét tất cả vào P2.

## Nợ kỹ thuật cần xác minh lại

Nguồn lịch sử: `.docs/ideations/03-backlog/moneywallet-outstanding-backlog.md`.

- SAF #177/#221; tiền/làm tròn #205/#189/#290/#128/#45/#32.
- Wallet notes #303, restore #197, orphan attachments #298, CSV/import.
- TB-01/TB-06 phân loại còn lỗi / xác minh đã sửa / chưa tái hiện tại SHA đích. Không kết luận hotfix bắt buộc hoặc bug đã hết từ tài liệu cũ.

## Quyết định và bằng chứng

- Giữ invariants: migrate từng bước, semantics ngày TEXT, dữ liệu/package/security theo AGENTS/module.
- SDK/flavor, license dependency, KMP và migration numbering cần evidence baseline; nhãn ADR trong ideation không thay decision record.
- Audit: `docs/plans/evidence/2026-10-20-governance-reconciliation.md`.
