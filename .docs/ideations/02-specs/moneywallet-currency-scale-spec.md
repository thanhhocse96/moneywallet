# Spec: Currency Input Scale (đơn vị nhập rút gọn)

> Ngày: 2026-10-20. Liên quan: ADR-2 (ngày TEXT), roadmap P4.

## 1. Bối cảnh

VND (và một số tiền tệ khác) có đuôi số 0 vô nghĩa do lạm phát: 11.000đ thì phần mang thông tin chỉ là "11". Người dùng phải gõ đi gõ lại các số 0 này mỗi lần nhập liệu. Số lượng số 0 vô nghĩa khác nhau theo tiền tệ (×100, ×1000, …) nên hệ số phải cấu hình được, không hard-code.

## 2. Quyết định kiến trúc: hướng (a)

**DB luôn lưu số tiền thật (canonical). Scale chỉ tồn tại ở tầng nhập + hiển thị.**

- Gõ `11` với scale ×1000 → lưu `11000`. Không bao giờ lưu `11` rồi nhân lúc đọc.
- Hướng (b) (lưu số rút gọn, nhân lúc đọc theo bảng scale) **bị loại**: vỡ với số tiền lẻ không chia hết (1.500đ không biểu diễn được với INTEGER/decimals=0), vỡ transfer cross-wallet khác scale, mọi chỗ hiển thị phải nhớ nhân (blast radius), export/downgrade mất nghĩa. Chi tiết phản biện đã trao đổi 2026-10-20.
- Hệ quả: **đổi scale bất cứ lúc nào cũng không rewrite dữ liệu** — setting an toàn tuyệt đối với data cũ.

## 3. Data model

- Thêm cột `currencies.input_scale INTEGER NOT NULL DEFAULT 1` (migration additive — default ×1 = đúng hành vi hiện tại, không reinterpret dữ liệu cũ).
- Scale là **thuộc tính của currency** (không phải setting chung app, không phải theo ví):
  - Setting chung sai vì USD cần ×1 trong khi VND cần ×1000.
  - Theo ví sai vì hai ví cùng VND khác scale → transfer/báo cáo vỡ.
- Giá trị cho phép: 1, 100, 1000 (mở rộng 10000 nếu cần).

## 4. Semantics

### 4.1 Nhập liệu
- Ô nhập tiền đọc `input_scale` của currency đang dùng: `stored = round(typed × scale)` về đơn vị nhỏ nhất của currency.
- Khi scale > 1, ô nhập **cho phép gõ thập phân**: gõ `1.5` → ×1000 → `1500`đ (lưu đúng số lẻ mà hướng (b) không làm được). Quy tắc làm tròn: half-up về minor unit.

### 4.2 Hiển thị
- Khi scale > 1: hiển thị rút gọn ở list (`11K` / `11 nghìn`), hiện đầy đủ ở chi tiết giao dịch / long-press.
- Format rút gọn là pure display — không ảnh hưởng số lưu.

### 4.3 Đổi scale
- Đổi bất cứ lúc nào, chỉ ảnh hưởng nhập + hiển thị từ đó về sau. Không migration dữ liệu.

## 5. Setting UI & default

- Vị trí: màn hình sửa tiền tệ (Settings → Currency management → edit) → mục "Đơn vị nhập": ×1 / ×100 / ×1000.
- Default lúc seed tiền tệ mới: theo locale — máy tiếng Việt thì VND mặc định ×1000, các nơi khác ×1. DB cũ migrate lên: tất cả ×1 (giữ nguyên hành vi), user tự bật khi muốn.

## 6. Xử lý ví rút gọn legacy (dữ liệu cũ nhập thiếu số 0)

Bối cảnh: user từng nhập rút gọn trong app cũ (gõ `11` ý là 11.000đ, app cũ lưu `11`). Ví này nhất quán theo đơn vị nghìn nhưng sai tuyệt đối.

### 6.1 Phát hiện (gợi ý, KHÔNG tự áp)
Khi user **set scale > 1** cho một currency → quét các ví dùng currency đó, gắn cờ candidate nếu:
- Ví có **≥ 10 giao dịch**, và
- **≥ 60% giao dịch có amount < scale** (ví dụ < 1000 với VND).

Giải thích: ví VND thật gần như không thể có đa số giao dịch dưới 1.000đ (~4 cent). Ngưỡng 60% có điểm mù (khoản rút gọn lớn như `2500` = 2,5 triệu không lọt), nhưng sót thì user tự trigger thủ công — false negative chấp nhận được, false positive đã có dialog chặn.

### 6.2 Conversion một lần (action, KHÔNG phải setting)
- Dialog xác nhận có **preview trước/sau** (tổng số dư 250 → 250.000đ).
- **Auto-backup JSON trước khi chạy** (đúng pattern roadmap).
- Nhân ×scale **toàn bộ cột tiền của ví trong 1 transaction**: checklist exhaustive — `transactions.amount`, transfer 2 phía, số dư đầu kỳ, debt, budget target, saving goal, recurrence… Sót một bảng là ví lệch.
- **Idempotency:** đánh dấu ví đã chuẩn hóa sau khi chạy (cột flag); bấm lại không nhân lần 2.
- Manual trigger: nút "Chuẩn hóa dữ liệu" trong setting ví (cho ví bị sót bởi heuristic).
- Ví trộn lẫn (vừa đủ vừa thiếu): không auto-fix được — user soát tay; dialog cảnh báo rõ.

### 6.3 Đảm bảo
- Không cấu hình scale → mọi thứ y nguyên (default ×1). Không ai bị ép migrate.
- Conversion xong là xong vĩnh viễn — không còn khái niệm scale gắn với dữ liệu.

## 7. Guardrails

- Scale thay đổi không bao giờ rewrite dữ liệu đã lưu.
- Conversion là action một lần có xác nhận + backup — không bao giờ tự chạy ngầm.
- Không lưu số rút gọn vào DB dưới bất kỳ hình thức nào (kể cả tạm).

## 8. Effort estimate

~1 tuần: migration cột + setting UI + sửa widget nhập tiền (nhân + cho thập phân) + format hiển thị rút gọn + flow detect/convert.
