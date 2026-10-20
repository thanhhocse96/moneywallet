# docs/standards/ — MoneyWallet
# Tiêu chuẩn coding và quy ước dự án.

## Danh sách file tiêu chuẩn

- `android-build-safety-contract.md` — Build safety (bắt buộc đọc trước khi sửa Gradle).
- `decision-memo-format.md` — Format 7 mục khi xin human quyết định.

## Quy tắc chung

- UTF-8 everywhere, tiếng Việt không mojibake.
- Package `com.oriondev.moneywallet`; không đổi package-id.
- Sanitize input, tránh SQL injection (dùng selectionArgs).
- Không hardcode secret/API key trong source.
- Không dùng `@SuppressLint` trừ khi có lý do rõ và ghi comment.
- Runtime permission: kiểm tra trước khi truy cập storage/camera/location.
