# P0 — Tiếp nhận tallybook và tổ chức phát triển MoneyVibe

Ngày: 2026-10-20. Trạng thái: kế hoạch thực thi; chưa tích hợp source tallybook.

## Context

- Human yêu cầu planning để dev và agent tiếp nhận tallybook, phát triển từng bước và duy trì fork có hệ thống.
- Milestone vẫn **P0 — Toolchain & compliance**. Scope theo MILESTONES hiệu chỉnh 2026-10-20: giá vàng tự động ngoài scope; UI theme/M3/minimalism/Apple-like island. Không chuyển milestone hoặc tự renumber phase còn lại.
- Startup protocol: `AGENTS.md` → `.context/GLOBAL.md` → `MILESTONES.md` → tensions → module liên quan. Workflow bổ sung: `docs/standards/human-agent-development.md`.
- Ideation là đầu vào thiết kế; các tuyên bố về tallybook và những mục ghi “đã chốt” cần được đối chiếu với source/decision trước khi thực thi.

## Goal

Tiếp nhận một commit tallybook xác định, bảo toàn lịch sử và tài sản riêng, chứng minh app và dữ liệu hoạt động, rồi phát triển bằng các thay đổi nhỏ có thể review và quay lại bản trước.

## Constraints / Invariants

- Giữ package `com.oriondev.moneywallet`; applicationId, signing, version và đường nâng cấp cần quyết định riêng trước khi sửa.
- Không reset --hard, force-push, ghi đè nhánh chính hoặc xóa tài sản riêng để lấy upstream.
- Không mặc định version v1.13.0, schema v10/27 bảng hoặc các bug “đã sửa” trong ideation là baseline thực tế.
- Không tự chạy Gradle, SDK, emulator hay device; human chạy và trả output theo AGENTS.md.
- Thay đổi dependency/flavor từ upstream vẫn phải qua contract và quyết định có bằng chứng; merge không được dùng để bỏ qua các giới hạn này.
- Không mở DB thật của user bằng schema mới trước khi có backup và bài kiểm chứng trên bản sao.

## Allowed / Forbidden

- Allowed: inventory, nghiên cứu source, pin SHA, lập bảng khác biệt, đề xuất patch nhỏ, viết test và checklist; chỉ sửa source khi task triển khai tương ứng được giao.
- Forbidden: đồng thời tiếp nhận upstream + Room + rebrand + feature; tự coi kế hoạch này là phê duyệt mọi thay đổi kiến trúc/dependency trong upstream.
- Không gửi issue/PR/message upstream khi chưa có yêu cầu rõ ràng. Không suy diễn thái độ với AI thành chính sách chính thức của upstream; đọc contribution policy tại ref được chọn trước bất kỳ đóng góp nào.

## Evidence hiện có

Kiểm tra local ngày 2026-10-20, trước đợt viết kế hoạch này:

- HEAD `ba9b04c`, nhánh `master`, `git status --short` sạch.
- `origin`: `https://github.com/thanhhocse96/moneywallet.git`; `upstream`: `https://github.com/AndreAle94/moneywallet.git`; chưa có remote tên `tallybook` trong `git remote -v`.
- `git diff --stat 071be04..HEAD`: 33 file thuộc docs/context/protocol/assets và `.gitignore`; không có thay đổi app source trong khoảng commit này.
- `app/build.gradle`: applicationId `com.oriondev.moneywallet`, versionCode 75, versionName 4.0.5.10, compile/target 29, min 21.
- `.local/ENVIRONMENT.md` hiện chứa placeholder; chưa đủ thông tin để lập lệnh runtime theo máy.
- Chưa fetch/kiểm chứng tallybook trong đợt planning này. Không có kết luận về tương thích backup, bugfix, license dependency hay khả năng build của baseline đích.

## Work packages và cổng kiểm chứng

Mỗi hàng là một task riêng. Trạng thái khởi tạo: **TODO**. Chỉ đánh DONE khi artifact và acceptance đều đủ; chờ human chạy test là **WAITING_HUMAN**, không phải DONE.

| ID | Việc và người thực hiện | Artifact / Acceptance | Phụ thuộc |
|---|---|---|---|
| TB-01 | Agent inventory local và upstream, xác minh URL/ref/tag; fetch read-only khi được giao tiếp nhận | Báo cáo pin SHA nguồn/đích, merge-base, diff stat, contribution/license files, toolchain/schema/backend thực tế; không dựa vào số liệu ideation | Không |
| TB-02 | Agent lập bảng thay đổi; human quyết các boundary cần đổi | Decision memo theo 7 mục: dependency/flavor, backup backend, applicationId/signing/update, version, dữ liệu vàng riêng. Mỗi mục có file:line tại SHA đã pin, tác động, cách quay lại, phạm vi được duyệt | TB-01 |
| TB-03 | Agent tạo điểm khôi phục và tích hợp trên nhánh `codex/tallybook-adoption` | Ghi SHA local trước merge và ref khôi phục; merge từ SHA đã pin, giữ lịch sử; lưu bảng conflict và resolution. Giữ `.context/`, docs, AGENTS, ignore rules của fork | TB-02 |
| TB-04 | Agent chuẩn bị lệnh + checklist; human build và smoke test | Log lint/build/test theo variant thực; thiết bị/OS; cold start, nhập/sửa/xóa giao dịch, transfer, debt, budget/saving, recurrence, permission, backup/export. Pass hoặc lỗi có cách tái hiện | TB-03 |
| TB-05 | Agent thiết kế bộ dữ liệu; human chạy restore/upgrade trên bản sao | Kiểm chứng DB rỗng, có dữ liệu, sau restore; round-trip backup, wallet notes, attachment, transfer/split, số dư. Backup MoneyWallet cũ và tallybook, mã hóa nếu hỗ trợ. Đối chiếu số dòng theo bảng và giá trị nghiệp vụ | TB-04 |
| TB-06 | Agent đồng bộ context theo bằng chứng, audit lại backlog | GLOBAL/module/MILESTONES phản ánh baseline thực; upstream ledger và acceptance report; phân loại từng bug còn tồn tại/đã xác minh sửa/chưa tái hiện. Human chấp nhận baseline | TB-05 |
| TB-07 | Agent đề xuất task dev đầu tiên; human chọn scope | Một task nhỏ có acceptance, test oracle và rollback. Room/KMP/tag/icon/scale chỉ mở khi prerequisites và quyết định liên quan đủ | TB-06 |

### TB-01 — Nội dung báo cáo bắt buộc

- Exact SHA và ngày kiểm tra; tag chỉ là nhãn, SHA là đầu vào tái lập.
- Kiểm tra merge-base thật; nếu không có lịch sử chung hoặc conflict lớn, lập memo về chiến lược khác trước khi tích hợp.
- So sánh schema/version, business rules, backup/import/export, dependency/repository, SDK/JDK/Gradle, permissions, manifest components, flavor, signing và CI nếu có.
- Mỗi feature/backend cũ: giữ / thay thế / mất / chưa xác minh. Ghi cả PDF export và Drive/Dropbox/WebDAV, không che thay đổi hành vi dưới tên “nâng cấp toolchain”.
- Xác định code vàng mà ideation nói đã hoàn thành nằm ở đâu; nếu chưa có artifact, ghi UNKNOWN và không kết luận đã bảo toàn hoặc đã bỏ khỏi scope.

### TB-02 — Cách chuẩn bị quyết định

Mặc định đề xuất merge trên nhánh riêng để giữ provenance và docs riêng. Chưa chọn lệnh merge cụ thể trước khi biết merge-base và diff.

Mọi yêu cầu quyết định dùng `docs/standards/decision-memo-format.md`: vấn đề, 2–3 phương án, khuyến nghị, evidence, tự kiểm chứng ≤10 phút, đảo ngược, default. Không xin duyệt bằng tuyên bố chung “tallybook tốt hơn”.

Nếu thay đổi đề xuất xung đột `[manual]`, ghi tension OPEN theo AGENTS.md. HIGH thì dừng bước phụ thuộc cho đến khi human resolve. Không tạo tension chỉ vì kế hoạch đang có một bước kiểm tra tương lai.

### TB-03 — Tích hợp có thể kiểm tra

- Kiểm tra lại working tree trước mọi thao tác; không stash/ghi đè thay đổi của human một cách ngầm định.
- Đặt điểm khôi phục bền vững cho SHA local; nhánh chính giữ nguyên trong lúc review.
- Merge upstream và các sửa tương thích của fork phải phân biệt được trong lịch sử. Mỗi conflict có lý do và kiểm chứng liên quan.
- Tách rebrand, Room, tính năng mới thành đợt riêng. Sửa tối thiểu để baseline chạy và đáp ứng quyết định đã duyệt.
- Agent không push/merge PR vào nhánh chính chỉ vì test pass. Chấp nhận baseline và publish/release là các hành động riêng.

### TB-04/TB-05 — Bằng chứng hoàn tất

- Human cung cấp SDK/JDK/device thực trước thao tác runtime. Agent cung cấp lệnh đúng variant sau khi đọc build config; vẫn output các lệnh chuẩn theo AGENTS.md khi có code.
- Log gắn commit, command, exit status, variant, thiết bị/OS và ngày chạy; không commit secret, dữ liệu cá nhân hoặc backup thật.
- Với tiền: kiểm tra minor units, decimals, số âm, làm tròn, transfer hai phía/phí; số dòng khớp chưa đủ để chứng minh số dư đúng.
- Upgrade in-place chỉ test khi applicationId/signing/version tương thích. Nếu chọn appId riêng, kiểm chứng luồng cài song song + import backup; không gọi đó là upgrade in-place.
- Restore lỗi phải có trạng thái rõ ràng và không làm hỏng bản dữ liệu tốt trước đó. Không mặc định giải pháp “catch rồi tiếp tục” bảo đảm tính nhất quán.
- Rollback source bằng ref khôi phục khác với rollback dữ liệu: không mở DB đã migrate bằng APK cũ nếu chưa chứng minh tương thích. Khôi phục bằng bản backup/bản sao phù hợp.

## Acceptance toàn đợt

- [ ] Baseline upstream pin SHA; các thay đổi sản phẩm/dependency được quyết và ghi lại.
- [ ] Git history, docs/protocol và phần riêng được bảo toàn; conflict được giải thích.
- [ ] Human xác nhận build/smoke/restore theo commit ứng viên; failure chưa giải quyết phải hiện rõ, không đánh pass.
- [ ] Không mất số dư, quan hệ transfer/split, notes và attachment trong bộ mẫu.
- [ ] Context, backlog và upstream ledger khớp baseline đã chấp nhận.
- [ ] Task kế tiếp nhỏ; không tự chuyển P1, tạo giá vàng tự động hoặc xóa phần vàng riêng nếu tìm thấy.

## Sau khi tiếp nhận: phát triển và maintaining

1. Đánh giá lại P0 còn thiếu gì trên baseline mới; hoàn tất hoặc ghi deferred có quyết định. Human mới tuyên bố chuyển milestone.
2. Theo scope hiện hành trong MILESTONES, không theo số phase ideation. Chọn vertical slice/migration numbering sau baseline; không tái dùng v11 cho nhiều release. Giá vàng tự động đã ngoài scope, không hỏi duyệt lại việc đó.
3. Trước Room: xác minh schema thật và compatibility; trước KMP: chứng minh dependency/API boundary phù hợp phiên bản đã chọn, không mặc định chuyển vào commonMain là miễn phí.
4. Tag, scale và icon đi thành task riêng sau prerequisites. Mỗi feature cần source-of-truth và semantics nhất quán trước code.
5. Mỗi đợt cập nhật upstream dùng cùng quy trình pin → diff → decide → integrate → verify. Có thể review hàng tháng hoặc khi có bugfix liên quan; đây là nhịp làm việc đề xuất, không phải automation đã tạo.

## Known tensions / Unknowns

Tension files lúc lập kế hoạch không có OPEN/RESOLVED_ACTIVE. Planning này không sửa source hoặc override manual constraints.

Các unknown chặn tích hợp: SHA đích, thay đổi dependency/flavor/backend, application identity và dữ liệu vàng riêng. Các unknown chặn runtime: SDK/JDK/device và bộ mẫu đã ẩn danh. Chúng được xử lý ở TB-01/TB-02, không yêu cầu human quyết mù trong đợt lập kế hoạch.
