# Digest artifact UI — MoneyVibe

Ngày: 2026-10-20. Mục đích: giúp agent triển khai đúng thiết kế, không suy diễn từ tên style.

## Phạm vi và mức kiểm chứng

- Artifact chính: `.docs/ideations/ui/Money Lover Redesign Preview (3).html`.
- Artifact bổ sung: `.docs/ideations/ui/tag-merge-ui-prototype.html`.
- Đã đọc HTML/CSS/JS và đối chiếu thuật ngữ Apple. Chưa visual QA qua screenshot: browser tool từ chối URL `file:` theo policy. Không coi phân tích source là bằng chứng render/font/layout thực đã pass.
- Các giá trị dưới là giá trị khai báo trong prototype, chưa phải design tokens production đã duyệt. Tailwind/CDN/font và CSS cascade có thể ảnh hưởng hình thức khi render.

## Tên gọi đúng và giới hạn

**Artifact là thiết kế fintech dạng card/list, có ảnh hưởng iOS; không có một tên chính thức duy nhất cho toàn bộ tổ hợp này.**

| Thuật ngữ | Ý nghĩa / mức áp dụng |
|---|---|
| **Inset Grouped** | Tên chính thức của kiểu list Apple: nhóm section thụt vào hai bên và bo góc. Gần nhất với các nhóm giao dịch theo tuần ở bản Vibrant; không phải tên toàn bộ app |
| **Card-based UI / grouped sections** | Tên mô tả thông dụng cho card budget, chart và nhóm form. Dùng khi cấu trúc không phải list |
| **Minimal / typography-led UI** | Tên mô tả bản Minimal: chữ, khoảng trắng và separators dẫn phân cấp. Không phải nhãn thiết kế độc quyền Apple |
| **Material 3** | Nền design system Android đã được human chọn; artifact redesign là HTML/Tailwind custom, chưa chứng minh tuân thủ M3. Prototype tag sử dụng tokens kiểu M3 rõ hơn |
| **Liquid Glass** | Tên chính thức của material Apple mang đặc tính quang học/động. Các card nội dung ở đây là nền đục; không có cơ sở gọi artifact là Liquid Glass |
| **Dynamic Island** | Không phải tên của các card nội dung. `.island` trong HTML là mô phỏng cutout trên khung điện thoại; không tạo feature Android overlay từ chi tiết này |

Nguồn thuật ngữ: [Apple UITableView insetGrouped](https://developer.apple.com/documentation/uikit/uitableview/style-swift.enum/insetgrouped), [Apple HIG Materials](https://developer.apple.com/design/human-interface-guidelines/materials). Nhận định artifact “gần Inset Grouped” là phân tích của agent từ source, không phải Apple chứng nhận.

Tên mô tả dùng trong brief: **“MoneyVibe — Material 3 với grouped sections lấy cảm hứng từ iOS và cách trình bày tối giản.”** Đây là mô tả nội bộ, không đặt ra một tiêu chuẩn chính thức mới. Hướng human “Apple-like island” được hiểu qua cấu trúc cụ thể, không đồng nhất với Liquid Glass.

## Hai variant thực sự khác nhau

| Đặc điểm | Vibrant / Rực rỡ (`src-*`) | Minimal / Tối giản (`src-min-*`) |
|---|---|---|
| Canvas app | `#F4F6FB` | `#FFFFFF` |
| Surface | Card trắng, bo góc 24px, shadow khai báo `0 8px 30px rgba(15,23,42,.08)` | Phần lớn section phẳng, separator `#EBEBEB`, ít shadow |
| Chữ chính/phụ | `#0B1226` / `#64748B` | `#161616` / `#6E6E6E` |
| Accent | Indigo `#4F46E5` → violet `#7C3AED`, nhiều category màu | Action đen, màu nhẹ cho category và màu semantic cho tiền |
| Tiền thu/chi | `#10B981` / `#F43F5E` | `#2F9E44` / `#E03131` |
| Typography | Plus Jakarta Sans, nhiều semibold/bold/extrabold | Cùng font, tiêu đề/light và số lớn/extralight, label nhỏ uppercase |
| Transactions | Summary tháng gọn, card theo tuần có tổng thu/chi | Hero total balance, list phẳng theo ngày |
| Chọn category | Recent chips + danh sách chữ theo nhóm | Grid 4 cột với icon/initial tròn |
| Navigation | Icon + label, nút thêm gradient nổi giữa | Label, nút thêm đen, ít trang trí |
| Overview | Donut nhiều màu, insight card gradient | Donut grayscale, insight dạng section phẳng |

**Hai variant không chỉ là hai theme màu.** Chúng khác grouping, hierarchy và interaction surface; không implement toggle theme bằng cách thay toàn bộ information architecture theo prototype. Bản Minimal hiện không giữ các card island theo tuần của Vibrant.

Cả hai app canvas là **light mode** (`SCREEN_HEAD` và `MIN_HEAD` đều khai báo `color-scheme:light`). Nền tối/glow bên ngoài là trang trình diễn, không phải dark theme của app. Toggle mặc định mở Vibrant không có nghĩa human đã chọn Vibrant làm default sản phẩm.

## Bản đồ màn hình → implementation brief

| Screen / source anchor | Cấu trúc cần hiểu | Cần làm thật khi có task |
|---|---|---|
| Transactions: `src-transactions`, `src-min-transactions` | Period, balance/income/expense, filters, transaction rows, navigation/add | Chọn grouping ngày/tuần rõ ràng; dữ liệu từ domain; filter/navigation thực; số tiền dài và state rỗng/lỗi |
| New transaction: `src-new`, `src-min-new` | Expense/Income/Transfer, amount nổi bật, category, date/wallet/note, Save cố định | Input/validation/keyboard thật, save một lần, giữ draft khi lỗi, category UX được chọn |
| Budgets: `src-budgets`, `src-min-budgets` | Summary, từng budget có spent/limit/remaining, progress và cảnh báo | Tính đúng remaining/over-budget, không suy rule cảnh báo hoặc ngưỡng từ số mẫu |
| Overview: `src-overview`, `src-min-overview` | Period/mode, donut + total, legend, insight và category ranking | Report có semantics rõ; không coi Transfer/Deposit trong mock là quy tắc tính expense, accessible summary cho chart |
| Tag merge: artifact riêng | Select nhiều tag → chọn canonical → preview → confirm; alias/rename demo | Dùng workflow làm tham chiếu; dedupe joins/count theo dữ liệu thật, atomicity, failure state, xác nhận tác động |

Shared components dự kiến cho task thiết kế: AmountText, TransactionRow, GroupedSection, FilterChip, CategoryPicker, BudgetProgress, ReportSummary, Navigation, MergePreview. Đây là phân rã trách nhiệm, không buộc tên class/framework.

## Tương tác đã có và chưa có

- Redesign có JS đổi variant qua `iframe.srcdoc`, đổi selected class cho chips/segments, toggle switch và animation bar/donut.
- Các thao tác đó chủ yếu đổi hình thức; không chứng minh filter query, nhập amount, Save, database hoặc navigation nghiệp vụ hoạt động. Nội dung “Tap to edit” đang là text.
- Tag prototype có state demo trong RAM; merge cộng `count` của tags. Không dùng phép cộng đó cho số transaction unique nếu tags trùng transaction. Ô tìm tag ở header là placeholder trình bày, không suy ra search production hoàn tất.
- Prototype không đủ failure/empty/loading/persistence states; agent phải bổ sung trong task, không đánh hoàn tất từ screenshot happy path.

## Điều cần giữ / điều không copy nguyên xi

Giữ: số tiền rõ ràng, nhóm nội dung có ý nghĩa, nhịp spacing nhất quán, action chính dễ tìm, separators nhẹ, preview hệ quả merge, màu thu/chi kèm dấu/nhãn.

Không copy: khung iPhone, giờ/pin giả, cutout/home indicator, nền studio/glow, kích thước cố định 390×844, USD/ngày/số liệu mẫu, CDN/font runtime từ HTML vào app native.

Không khóa px thành dp/sp máy móc. Prototype dùng gutter `px-5`, card radius 24px, khoảng section 16px; coi là tham chiếu tỷ lệ, cần kiểm chứng trên Android với font scale/insets.

## Những lỗi/giới hạn source phải xử lý trước chốt visual

- Minimal yêu cầu `font-extralight` nhưng URL font MIN_HEAD nạp weight 300–700, không có 200; cần xác minh font thực trước dùng ảnh làm chuẩn typography.
- Nhiều label 10–12px, màu phụ nhạt và số tiền weight nhẹ: chưa chứng minh đạt readability/contrast trên thiết bị.
- Shared `button` CSS khai báo reset background/border/font; cần kiểm tra computed style khi render thay vì suy class Tailwind chắc chắn thắng cascade.
- Reduced-motion rule xử lý bar/caret, còn donut transition được gán trong JS: production phải xử lý toàn bộ motion theo preference.
- Bản Minimal chart dùng nhiều sắc xám lặp: cần legend/text/số liệu, không chỉ màu để phân biệt category.
- Nhóm theo tuần so theo ngày và category list so grid là các quyết định UX riêng; không ngầm chọn khi đổi theme.

## Handoff cho agent triển khai

1. Đọc MODULE_UI + ui-design-direction + digest này; audit components/theme trên tallybook SHA đã pin.
2. Trong task màn hình mẫu, chỉ rõ cấu trúc lấy từ variant nào. Nếu kết hợp minimal typography với grouped cards thì ghi là **bản tổng hợp mới**, không nói đã có nguyên xi trong artifact.
3. Map tokens sang theme Material 3, dùng components phù hợp; dependency/font mới theo approval hiện hành. Không thêm iOS framework hoặc overlay vì chữ Apple-like.
4. Hoàn thiện một màn Transactions với state thật và screenshot/preview trước rollout; chốt grouping/category pattern khi đến task liên quan bằng evidence, không đòi quyết tất cả ngay.
5. Verify font scale, locale, số tiền dài/âm, multi-currency, keyboard, navigation và theme modes đã chọn; đảm bảo theme không đổi phép tính/filter/grouping.
6. Báo rõ source review / render review / device verification. Render artifact và nghiệm thu màn hình vẫn còn cần làm; digest này không phải approval pixel-perfect.
