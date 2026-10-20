# docs/standards/decision-memo-format.md — MoneyWallet
# Format 7 mục khi xin human quyết định (tension, ASK_ARCHITECTURE, milestone approval, scope change, dependency mới).

```
1. Vấn đề (1 câu)
2. Phương án (2–3, mỗi cái kèm trade-off)
3. Khuyến nghị + lý do
4. Bằng chứng (artifact nhìn được: commit/file:line/screenshot/số đo)
5. Tự kiểm chứng (nguồn + file + xem gì — human research độc lập ≤10 phút)
6. Đảo ngược (2 chiều → quyết nhanh | 1 chiều → cần evidence dày)
7. Default nếu human không quyết trước [mốc] (conservative; quyết định chặn/HIGH → DỪNG)
```

Quy tắc kèm theo:

- Không điền được mục 4–5 = chưa đủ tư cách hỏi; quay lại research.
- Khẳng định về behavior thư viện ngoài phải cite docs/changelog đúng version trong `build.gradle`.
- Fix nào lật đổ premise trong decision doc thì update doc đó **trong cùng đợt fix**.
