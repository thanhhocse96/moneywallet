# BÁO CÁO TỔNG HỢP: DỰ ÁN MONEYVIBE
## Hiện đại hóa MoneyWallet → app quản lý chi tiêu thế hệ mới

> Ngày lập: 2026-10-19 · Trạng thái: **planning hoàn tất, chưa viết code sản phẩm mới**
> Tài liệu chi tiết kèm theo: `moneywallet-migration-roadmap.md`, `moneywallet-hashtag-tag-spec.md`,
> `moneywallet-icon-spec.md`, `moneywallet-data-layer-deep-analysis.md`, `tag-merge-ui-prototype.html`

---

## 1. Tổng quan dự án

| Hạng mục | Nội dung |
|---|---|
| Tên app | **MoneyVibe** (chính tả "VV" chờ xác nhận — cố ý hay typo của "Vibe"?) |
| Baseline | `herrerad85/tallybook` v1.13.0 — fork active duy nhất (push gần như hằng ngày, có trên F-Droid) |
| Điểm xuất phát | tallybook hơn repo gốc 308 commits / 300+ files; DB v3→v10, 24→27 bảng |
| Stack đích | Kotlin, Room, coroutines/Flow, targetSdk 35/36, Material 3 minimal, native Android |
| License | GPL v3 (giữ nguyên; đã loại iText để gỡ ràng buộc AGPL) |
| Cross-platform | P1–P3 đặt trong KMP `commonMain` để sau này dùng lại; Flutter chỉ nếu cần iOS ngay từ đầu |

**Mục tiêu cuối:** app quản lý chi tiêu hiện đại, có hệ hashtag/tag kèm merge, custom icon 3 tầng, thương hiệu MoneyVibe.

---

## 2. Bước 0 — Merge tallybook vào repo (làm TRƯỚC mọi việc khác)

### Cách làm
- **Trường hợp A** — repo của bạn còn nguyên sơ (khuyến nghị nếu đúng):
  ```bash
  git remote add tallybook https://github.com/herrerad85/tallybook.git
  git fetch tallybook
  git reset --hard tallybook/master
  # 1 commit riêng: đổi applicationId, tên app, icon
  ```
- **Trường hợp B** — repo đã có commit riêng: `git merge tallybook/master`, hoặc `git rebase --onto tallybook/master 071be04 <nhánh>`; muốn chia nhỏ thì merge theo từng tag release v1.0.0→v1.13.0.

### Checklist sau merge
1. `applicationId` đổi thành của riêng bạn (Java package `com.oriondev.moneywallet` tallybook giữ nguyên — không cần rename).
2. Build release pass, cài máy thật Android 14/15 chạy được.
3. Restore thử backup `.mwbx` cũ (đã verify tương thích đầy đủ, cả bản mã hóa AES).
4. Rebrand: tên MoneyVibe + logo (mục 6).
5. **Giữ remote `tallybook`** để định kỳ `git fetch` kéo fix mới (họ push hằng ngày).

### Lưu ý đã biết trước
- Merge = **mất Google Drive/Dropbox** (tallybook xóa 2 backend này; chỉ còn disk/saf/webdav). Chấp nhận, thay bằng WebDAV + local folder.
- Không fork nào khác đáng merge (đã quét toàn bộ: MWPlus 15 commits cũ, DodoLeDev 5 commits icon, c-pedro y hệt gốc).

---

## 3. Roadmap 5 phase — việc làm & cách làm

### P0 — Toolchain & compliance (~1 tuần)
tallybook đã làm phần lớn → chủ yếu verify + bù thiếu.
- Verify AGP/Gradle, compileSdk/targetSdk/minSdk hiện tại; gắn Kotlin plugin 2.x (chưa viết Kotlin).
- License scan: xác nhận không còn iText (AGPL) hay lib chết.
- Verify scoped storage, Biometric, foreground service types (tallybook fix Android 14/15 ở v1.0.0).
- **Exit:** `assembleRelease` pass; backup/restore OK trên máy thật.

### P1 — Room core + validation (2 tuần, phase de-risk quan trọng nhất)
- 27 `@Entity` map 1:1 schema tallybook v10 (gồm `transaction_splits`, `budget_categories`, `category_rules`); **giữ ngày giờ dạng TEXT**, không đổi millis.
- `RoomDatabase` version 11 + migration 10→11 (tạo index FK theo naming Room).
- **Test quyết định:** mở file `.db` thật từ tallybook bằng Room, assert đủ 27 bảng + khớp số dòng (3 sample: db trống, có data, sau restore).
- Lần đầu Room chạm DB cũ → **auto-export JSON backup trước**.
- **Exit:** test mở db thật pass.

### P2 — Port write orchestration sang Repository (3–4 tuần)
- Repository per aggregate: Transaction (gồm transfer + split), Debt, Budget, Saving, Recurrence…; mỗi method bọc `@Transaction` (sửa bug không-transaction của code cũ).
- Port ~30 method từ `SQLDatabase`, giữ nguyên business rule (system category tags, junction sync, recurrence UUID deterministic, split parts).
- **Characterization test:** dùng code cũ làm oracle — cùng input, so DB state cũ vs mới (đặc biệt insertTransfer, updateTransaction, insertDebt, split CRUD).
- `DataContentProvider` thành delegate mỏng gọi Repository (strangler) — UI chưa đổi.
- **Exit:** toàn bộ test oracle pass.

### P3 — Migrate UI: Loader → Flow, xóa Provider (3–4 tuần)
- Làm 1–2 màn hình mẫu chuẩn hóa pattern (màn hình tag mới có thể làm mẫu bằng Compose).
- Từng màn hình: `CursorLoader` → `ViewModel` + `StateFlow`; xóa `LocalBroadcastManager` (36 files), `startActivityForResult` (14 files) → Activity Result API.
- Cuối phase: xóa `DataContentProvider`, `SyncContentProvider`, `SQLDatabase`, `Contract`…
- Test upgrade: cài tallybook hiện tại → nhập data → upgrade → verify không mất data.
- **Exit:** 0 reference tới provider/loader/broadcast.

### P4 — UI modernization (ongoing)
tallybook đã migrate Material 3 (10/2026) → kế thừa, không làm lại theme. Tập trung:
- Màn hình hashtag/tag mới theo M3 minimal (prototype `tag-merge-ui-prototype.html` đã duyệt concept).
- Thay lib chết còn lại: `material-dialogs`→MDC, `bottomsheetpickers`→MDC pickers, `MPAndroidChart`→Vico/Compose, `jxl`→Apache POI, iText→PdfDocument/PDFBox nếu còn.
- Compose cho màn hình mới; giữ View/XML cho màn hình cũ ổn định.

**Tổng estimate tới P3:** ~3–4 tháng part-time (~10–15h/tuần) hoặc ~1.5–2 tháng full-time.

---

## 4. Tính năng hashtag/tag (làm song song từ P2)

Spec đầy đủ: `moneywallet-hashtag-tag-spec.md`. Tóm tắt cách làm:

- **Grammar:** `#[\p{L}\p{N}_]+` — cho tiếng Việt và `_`, không giới hạn ASCII.
- **Bảng mới (migration v11):** `tags` + `transaction_tags` + `tag_aliases` (pattern UUID/`LAST_EDIT`/`DELETED` như bảng mới của tallybook). Bảng `tags` có thêm cột `icon` TEXT (mục 5).
- **Identity:** `tag_fold = NFC(name).lowercase(ROOT)`, UNIQUE — case-insensitive (`#tag`=`#TAG`) nhưng giữ dấu (`#ăn_sáng`≠`#an_sang`). Không dùng SQLite NOCASE (chỉ ASCII).
- **Source of truth = description** (và `split_note` — ADR-8, vì splits đã là feature chính thức). Bảng tag là materialized index, parse lúc insert/update.
- **Fuzzy autocomplete:** load tag vào RAM một lần, debounce 200ms, `mapLatest`, prefix trước → subsequence → edit distance; gợi ý từ ký tự thứ 2, bỏ dấu khi match; highlight live khi gõ.
- **Merge (multi-select ≥2 → bottom sheet):** chọn canonical (default = count cao nhất) → 1 transaction nguyên tử: re-point joins → flatten alias (không chain) → rewrite description bằng boundary regex → xóa tag bị gộp → bump `last_edit`. Có preview hệ quả; có tách alias (không fake undo).
- **Bulk rename:** 1 transaction: update `tag_name`/`tag_fold` + rewrite description + bump `last_edit`.
- **Còn mở:** forward-only mặc định + history scan opt-in, hay quét toàn bộ lịch sử?

---

## 5. Tính năng custom icon (3 tầng)

Spec đầy đủ: `moneywallet-icon-spec.md`. Nguyên tắc: **byte trong DB < 4KB → tự backup theo `database.json`; lớn hơn → ra file + mở rộng backup**.

| Tầng | Cách làm | Chi phí/lưu trữ |
|---|---|---|
| **2 — Pack built-in** (làm trước, ~1 tuần) | Bundle ~300 icon Material Symbols dạng VectorDrawable (`ic_pack_*`); tái dùng type `resource` hiện có, không sửa model/backup; mở rộng `IconPicker` + search fuzzy | ~50 bytes/icon; APK +~300KB một lần |
| **1 — SVG & emoji** (~1 tuần) | Type mới `svg`: import file → trích path `d`, chuẩn hóa 24×24, validate ≤4KB → `{"type":"svg","paths":[...]}`; render bằng `PathParser` (không thêm lib). Type `emoji`: vài bytes | SVG ~0.2–1KB, emoji ~8 bytes; backup free |
| **3 — Ảnh raster** (~2 tuần, optional) | Downscale 192px + WebP q80 (~4–10KB) → `files/custom_icons/<sha256>.webp` (tên = hash → tự dedupe); type `file`. **Sửa `BackupManager`** nhét vào zip + orphan cleanup (bài học bug #298) | File riêng; backup phải mở rộng |

Guardrails: cap 200 custom icon/user; **cấm Base64 ảnh vào TEXT**.

---

## 6. Branding — MoneyVibe

- **Logo đã chốt concept:** flat vector — ví xanh 2 mặt (trước `#3B71AC` kiểu Facebook đậm hơn chút, sau `#101F4D` navy), thẻ xanh lá (`#57A047`/`#1E6B3B`), đồng xu vàng `#E9B751` khắc `$` kẹp trong miệng ví, nền kem `#F9ECD7`.
- File vector: `moneyvibe-logo.svg` — 5 group riêng (`background`, `wallet-back`, `cards`, `coin`, `wallet-front`), mở trực tiếp bằng Illustrator. Chữ `$` nên Create Outlines.
- Việc còn lại sau chốt: xuất PNG các density (mdpi→xxxhdpi) / adaptive icon; splash screen.

---

## 7. Quyết định kiến trúc đã chốt (không bàn lại)

- **ADR-1:** Thay thế thay vì convert Java→Kotlin hàng loạt.
- **ADR-2:** Ngày giờ giữ TEXT `"yyyy-MM-dd HH:mm:ss"`.
- **ADR-5:** minSdk 26, targetSdk 35/36; bỏ flavor proprietary/gmap.
- **ADR-6:** GPL v3; bỏ iText gỡ AGPL.
- **ADR-7:** Baseline = tallybook; giữ remote để kéo fix mới.
- **ADR-8:** Hashtag parse cả `split_note`.
- Plugin = **ports & adapters nội bộ** (kế thừa `IBackendServiceAPI`/`BackendDescriptor`), KHÔNG dynamic loading; trong KMP thì expect/actual chính là cơ chế plugin.
- **DuckDB: loại** — `SQLiteAnalyticsEngine` trước, chỉ xem lại khi benchmark ≥50k rows chứng minh query >500ms.
- Analytics: định nghĩa interface `AnalyticsEngine` từ đầu.

---

## 8. Đã loại khỏi scope (ghi để khỏi quay lại)

- **Vàng (VAU, phân/chỉ/lượng):** user đã tự implement xong 2026-10-19 — bỏ khỏi roadmap (trước là P2/P6). Tallybook không có tính năng này.
- PDF export kiểu cũ (iText) — bỏ hoặc viết lại bằng PdfDocument/PDFBox.
- Google Drive/Dropbox backup — mất theo tallybook, thay bằng WebDAV + local folder.

---

## 9. Bug backlog cần nhớ (17 bugs đã audit)

Critical/High: #303 (wallet notes mất khi restore), họ "1-cent" #205/#189/#290/#128.
Lưu ý: nhiều bug đã được tallybook fix (debt date, #303, #290, #211, #197) — khi làm P1–P2 **audit lại trên baseline tallybook**, không mang nguyên backlog của repo gốc sang. Riêng #177/#221 (SAF boot loop) **không cần hotfix** nếu fork tallybook.

---

## 10. Câu hỏi mở (chờ bạn quyết)

1. Merge tallybook: **trường hợp A** (reset --hard) hay **B** (merge/rebase)?
2. Tên "MoneyVibe" — "VV" cố ý hay typo?
3. Logo flat chốt chưa? (rồi xuất bộ PNG/adaptive icon)
4. Hashtag: forward-only + history scan opt-in, hay quét toàn bộ lịch sử?
5. Icon pack: chốt bao nhiêu icon, ai duyệt danh sách?

---

## 11. Thứ tự triển khai đề xuất

1. **Merge tallybook** (mục 2) → build + restore test → rebrand.
2. **P0** (~1 tuần) → **P1** (2 tuần, de-risk DB).
3. Song song từ P2: **hashtag/tag** (migration v11 + parser + autocomplete) → **icon tầng 2+1**.
4. **P2 → P3** (repository → UI migration).
5. **P4**: màn hình tag/merge (M3 minimal) + thay lib chết; icon tầng 3 nếu cần.
