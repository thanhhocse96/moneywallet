# Spec: Custom Icon cho Tag (3 tầng)

> Ngày: 2026-10-19. Liên quan: `moneywallet-hashtag-tag-spec.md` (bảng `tags`), ADR-7 (baseline tallybook).

## 1. Bối cảnh

Hệ icon hiện tại (`model/Icon.java`):
- Abstract class, 2 type: `resource` và `color`, serialize thành JSON TEXT.
- `VectorIcon` thực chất là **resource-by-name**: `{"type":"resource","resource":"ic_wallet"}` — không phải vector custom.
- `ColorIcon`: `{"type":"color","color":"#...","name":"..."}`.
- Đã có `IconPicker` + `IconAdapter` + `IconGroup` (icon nhóm theo bộ).
- Backup `.mwbx` = zip chứa `database.json` → **mọi thứ trong TEXT column được backup tự động**.

Mục tiêu: user thêm icon cho tag (và tái dùng cho category/wallet/…), theo nguyên tắc **byte trong DB < 4KB → tự backup; lớn hơn → ra file + mở rộng backup**.

## 2. Quyết định kiến trúc chung

1. Mọi icon custom đều serialize về envelope JSON hiện tại `{"type": "<type>", ...}` — **không thêm cột, không đổi schema** ngoài `tags.icon TEXT NULL` (đã nằm trong migration v11 của hashtag spec).
2. Mọi entity hiện có (`category_icon`, `wallet_icon`, …) tự hưởng type mới vì chung model `Icon`.
3. Thêm subclass `Icon` mới cho mỗi type mới; `IconPicker` thêm tab tương ứng.

---

## 3. Tầng 2 — Icon pack built-in (làm TRƯỚC, ~1 tuần)

### 3.1 Lựa chọn pack
- **Đề xuất: Material Symbols** (khớp M3 mà tallybook vừa migrate), curated ~300 icon chủ đề tài chính/đời sống, dạng **VectorDrawable XML** (`res/drawable/ic_pack_*`).
- Vì sao không dùng font: khỏi toolchain subset font, không lo font rendering lỗi, VectorDrawable tint được native, nhẹ (~1KB/icon → ~300KB APK một lần).
- Tooling export: script từ material-symbols repo → android vector drawable (có sẵn tooling cộng đồng).

### 3.2 Data model
- **Tái dùng type `resource` nguyên xi**: `{"type":"resource","resource":"ic_pack_coffee"}`.
- Không thêm type mới, không sửa model, không sửa backup. Đây là tầng rẻ nhất vì hạ tầng đã xong.

### 3.3 Picker UI
- Mở rộng `IconPicker` hiện có: thêm nhóm "Bộ sưu tập", ô search **tái dùng fuzzy logic của hashtag** (bỏ dấu, subsequence match, debounce).
- Grid + nhóm theo category (ăn uống, đi lại, …).

### 3.4 Chi phí
- Mỗi icon dùng: ~50 bytes trong DB. APK +~300KB một lần. Backup: free.

---

## 4. Tầng 1 — Custom vector (SVG) & emoji (~1 tuần)

### 4.1 SVG import
Pipeline lúc import (SAF picker → file `.svg`):
1. Parse XML, đọc `viewBox`. Thiếu viewBox → **reject + báo lỗi rõ** (không đoán mò).
2. Trích mọi thuộc tính `d` trong `<path>`. **Bỏ qua** gradient/filter/mask/script — chỉ giữ fill paths (icon style Material đều là fill phẳng; document giới hạn này trong UI).
3. Chuẩn hóa về viewBox `0 0 24 24` (scale transform).
4. Validate: tổng length(paths) ≤ 4KB **và** `PathParser.createPathFromPathData()` parse được → không thì reject.

Lưu: `{"type":"svg","vb":"0 0 24 24","paths":["M...","M..."]}` — thường 200–800 bytes.

Render — class `SvgIcon extends Icon`:
- Dùng **`androidx.core.graphics.PathParser`** (đã có trong androidx, không thêm dependency) build `Path`, vẽ vào custom Drawable bằng Paint fill.
- Tint qua `DrawableCompat.setTint()` → ăn dark mode.

### 4.2 Emoji
- Lưu: `{"type":"emoji","value":"☕"}` (~8 bytes). Thiếu VS16 thì append `\uFE0F`.
- Render qua TextView/EmojiCompat. Không tint.

### 4.3 Picker UI
- Thêm tab "SVG" (nút Import → SAF) và tab "Emoji" (grid theo nhóm Unicode).
- Preview trước khi lưu; báo lỗi cụ thể khi SVG không đạt (quá lớn / parse fail / không có path).

### 4.4 Chi phí
- SVG ~0.2–1KB, emoji ~8 bytes trong DB. Backup: free (TEXT).

---

## 5. Tầng 3 — Ảnh raster custom (~2 tuần, optional)

### 5.1 Import pipeline
1. SAF image picker → decode bounds (từ chối file > 10MB / decode fail).
2. Downscale về **max 192px** cạnh dài, nén **WebP quality 80** → ~4–10KB/file.
3. Lưu `files/custom_icons/<sha256>.webp` — **tên file = hash nội dung → tự dedupe** nếu nhiều tag dùng chung ảnh.

### 5.2 Data model
- Type mới `FILE("file")`: `{"type":"file","name":"<sha256>.webp"}`. Class `FileIcon extends Icon`.
- `getDrawable()` đọc file; **file mất → fallback drawable mặc định** (không crash).

### 5.3 Backup/restore (phần duy nhất phải sửa backup)
- `BackupManager`: thêm entries `custom_icons/*.webp` vào zip `.mwbx`; manifest thêm `"has_custom_icons": true`.
- Restore: giải nén vào `files/custom_icons/`; backup cũ không có thư mục → bỏ qua êm thấm.
- **Orphan cleanup** (bài học bug #298): khi tag đổi/xóa icon file → kiểm tra còn reference nào không (`tags` + các bảng có icon), không còn → xóa file. Chạy lúc delete/update, không để file mồ côi phình storage.

### 5.4 Hiển thị
- Circle crop, 96dp, **không tint** (ảnh màu thật).

---

## 6. UI tổng thể

- Tag editor: preview icon + nút "Đổi icon" → bottom sheet 4 tab: **[Bộ sưu tập | Emoji | SVG | Ảnh]**.
- Tag list: icon hiện trước tên tag.
- Dark mode: pack/svg tint theo `?attr/colorOnSurface`; file/emoji giữ nguyên.

## 7. Ma trận backup

| Tầng | Lưu ở đâu | Có phải sửa backup không |
|---|---|---|
| Pack (resource) | ID trong TEXT | Không |
| SVG / Emoji | TEXT trong DB | Không |
| File | `files/custom_icons/` | **Có** — thêm vào zip + restore + orphan cleanup |

## 8. Guardrails (chống lạm dụng)

- Cap **200 custom icon/user** (SVG + file) để chặn phình storage.
- SVG: ≤ 4KB path data, chỉ fill paths.
- File: ≤ 192px, WebP q80.
- **Cấm**: Base64 ảnh nhét vào TEXT (phình DB, chậm query, backup JSON phình theo) — đúng điều user muốn tránh.

## 9. Thứ tự implement & effort

| Thứ tự | Tầng | Effort | Phụ thuộc |
|---|---|---|---|
| 1 | Pack built-in | ~1 tuần | Không |
| 2 | SVG + emoji | ~1 tuần | Không (làm song song được) |
| 3 | Raster file | ~2 tuần | BackupManager, orphan cleanup |

## 10. Câu hỏi mở

- Pack curated bao nhiêu icon, ai duyệt danh sách cuối? (đề xuất bắt đầu 300)
- Có cho export/share icon custom giữa các máy không? (backup đã cover; share file riêng thì chưa)
