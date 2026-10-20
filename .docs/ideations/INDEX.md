# INDEX.md — Ideations / MoneyVibe

> Thư mục chứa các tài liệu ideation (ý tưởng, spec, phân tích, prototype) cho dự án MoneyVibe (hiện đại hóa MoneyWallet).
> Đây là scratch area — nội dung có thể bị thay đổi, chưa nhất quán với code sản phẩm.
> Các file đã promote thành quyết định sẽ được chuyển sang `docs/decisions/` hoặc `.context/`.

---

## Cấu trúc thư mục

| Thư mục | Mô tả |
|---|---|
| `00-overview/` | Tổng quan dự án, branding, logo |
| `01-architecture/` | Kiến trúc, đánh giá framework, phân tích tầng data |
| `02-specs/` | Spec chi tiết tính năng (tag, icon, currency scale, roadmap) |
| `03-backlog/` | Backlog bugs & thứ tự fix |
| `ui/` | UI prototypes, mockup HTML |

---

## 00-overview — Tổng quan & branding

| File | Mô tả | Trạng thái |
|---|---|---|
| `moneyvibe-bao-cao-tong-hop.md` | Báo cáo tổng hợp dự án MoneyVibe: merge tallybook, roadmap 5 phase, branding, câu hỏi mở cho human quyết | Planning hoàn tất, chưa code |
| `moneyvibe.png` | Logo MoneyVibe (raster) | Asset |
| `moneyvibe.svg` | Logo MoneyVibe (vector, flat concept) | Asset |

**Nội dung chính:** baseline = tallybook v1.13.0, stack Kotlin + Room + KMP, GPL v3, merge trước khi làm mọi thứ khác, 4-5 tháng part-time tới P3.

---

## 01-architecture — Kiến trúc & phân tích

| File | Mô tả | Trạng thái |
|---|---|---|
| `moneywallet-cross-platform-evaluation.md` | Đánh giá framework đa nền tảng (Native/KMP vs Flutter vs Tauri vs React Native vs Dioxus), khuyến nghị ở native Android + KMP `commonMain` | Quyết định đã chốt |
| `moneywallet-data-layer-deep-analysis.md` | Phân tích sâu tầng data hiện tại (24 bảng, ContentProvider-as-Repository, SQLDatabase, backup/export, migration Room, effort ~6-10 tuần) | Tham khảo cho P1-P3 |

**Nội dung chính:** Khuyến nghị KMP thay vì rewrite Flutter/Tauri; tầng data hiện tại không có transaction SQLite (bug tiềm ẩn), migration sang Room sẽ sửa luôn.

---

## 02-specs — Spec tính năng

| File | Mô tả | Trạng thái |
|---|---|---|
| `moneywallet-currency-scale-spec.md` | Spec đơn vị nhập tiền tệ (scale ×1/×100/×1000, DB lưu số thật, chỉ hiển thị rút gọn, BigDecimal + HALF_UP) | Chưa code |
| `moneywallet-hashtag-tag-spec.md` & `moneywallet-hashtag-tag-spec.md` | Spec hashtag → tag entity: grammar, data model (tags + transaction_tags + tag_aliases), merge 5 bước, bulk rename, forward-only parsing | Chưa code |
| `moneywallet-icon-spec.md` | Spec custom icon 3 tầng (pack built-in, SVG/emoji, raster file), backup matrix, guardrails (cap 200 icon, cấm Base64) | Chưa code |
| `moneywallet-migration-roadmap.md` | Roadmap hiện đại hóa 7 phase (P0 toolchain → P6 vàng tự động), ADR-1 đến ADR-6, checklist không bao giờ quên | Tham khảo |

**Nội dung chính:** Các spec đã được chốt grammar, data model, merge flow, icon tiers. Còn các câu hỏi mở (Xem mục 10 của báo cáo tổng hợp).

---

## 03-backlog — Backlog & bug tracking

| File | Mô tả | Trạng thái |
|---|---|---|
| `moneywallet-outstanding-backlog.md` | 17 bugs đã audit (Critical/High/Medium/Low), root cause, effort, thứ tự fix đề xuất, đã loại khỏi scope | Tham khảo |

**Bug ưu tiên cao nhất:** #177/#221 (SAF boot loop), 1-cent bugs (#205/#189/#290/#128), #303 (wallet notes mất), #197 (restore subset).

---

## ui — UI prototypes & mockup

| File | Mô tả | Trạng thái |
|---|---|---|
| `tag-merge-ui-prototype.html` | Prototype màn hình merge tag (Material 3 minimal, phone frame 390px, 587 dòng) | Concept đã duyệt |
| `Money Lover Redesign Preview (3).html` | Concept redesign Money Lover (Tailwind CSS, dark theme, 2 variant rực rỡ/tối giản, 1337 dòng) | Tham khảo UI |

---

## Cross-reference giữa các file

- `00-overview/moneyvibe-bao-cao-tong-hop.md` trỏ tới: `02-specs/moneywallet-hashtag-tag-spec.md`, `02-specs/moneywallet-icon-spec.md`, `02-specs/moneywallet-data-layer-deep-analysis.md`, `ui/tag-merge-ui-prototype.html`, `02-specs/moneywallet-migration-roadmap.md`.
- `02-specs/moneywallet-hashtag-tag-spec.md` trỏ tới: `02-specs/moneywallet-icon-spec.md` (bảng `tags` có cột `icon`).
- `02-specs/moneywallet-icon-spec.md` trỏ tới: `02-specs/moneywallet-hashtag-tag-spec.md` (migration v11), ADR-7 (baseline tallybook).

---

## Câu hỏi mở (chờ human quyết)

1. Merge tallybook: trường hợp A (`reset --hard`) hay B (merge/rebase)?
2. Tên "MoneyVibe" — "Vibe" đúng hay còn ý khác?
3. Logo flat đã chốt chưa?
4. Hashtag: forward-only + history scan opt-in, hay quét toàn bộ lịch sử?
5. Icon pack: bao nhiêu icon, ai duyệt danh sách?

---

## Quy tắc sử dụng

- Ideation là **scratch**: không code trực tiếp theo ideation chưa promote.
- Khi human approve một ý tưởng → di chuyển facts chính sang `docs/decisions/` (ADR) hoặc `.context/` (GLOBAL/MILESTONES/module).
- Không xóa file ideation trừ khi human xác nhận không cần nữa.
