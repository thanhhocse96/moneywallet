# Đánh giá framework đa nền tảng cho MoneyWallet rebuild

> Ngày: 2026-10-14. Dựa trên research hiện trạng 2026 (search + GitHub) và yêu cầu cụ thể của MoneyWallet: SQLite 24 bảng, charts tài chính, backup/export (JSON/CSV/XLS/PDF), file access (SAF), notification, biometric, background task (recurrence, auto-backup).

---

## Kết luận trước

**Nếu mục tiêu là ship app tốt nhất với nguồn lực solo dev: ở lại native Android (Kotlin), nhưng cấu trúc theo hướng Kotlin Multiplatform ngay từ đầu.** Lý do:

1. Roadmap migration 7 phases đã có là đúng đắn (được validate độc lập bởi issue #155 và research) — rebuild cross-platform là **vứt bỏ** toàn bộ phân tích đó.
2. KMP cho phép share chính xác phần khó nhất (domain + data layer: 24 bảng, business rules) mà vẫn giữ native Android UI — đúng thứ MoneyWallet cần (SAF, notification, biometric, background work đều là điểm đau đã ghi trong issues).
3. Flutter/Tauri = học stack mới + viết lại ~70k LOC domain + test 2 nền tảng — với solo dev, đó là 2–3x effort so với migration native.

**Chỉ chọn Flutter** nếu iOS là yêu cầu ngày đầu (không phải "sau này"). **Chỉ chọn Tauri** nếu Rust là yêu cầu cứng, chấp nhận mobile còn "rough".

---

## Ma trận so sánh (2026)

| Tiêu chí | Native Android + KMP | Flutter 3.47 | Tauri Mobile 2.x (Rust) | React Native (New Arch) | Dioxus (Rust) |
|---|---|---|---|---|---|
| Độ chín mobile | ✅✅✅ Native | ✅✅✅ Rất chín | ✅✅ Production-ready nhưng rough | ✅✅✅ Chín | ✅ Thô |
| Share code | 40–60% (logic) / 85%+ nếu +CMP UI | 85–95% | ~90% (UI web + Rust core) | 85–95% | ~90% |
| SQLite (24 bảng) | Room KMP-ready (Google official) | drift/sqflite (chín) | rusqlite qua plugin (tự lo) | expo-sqlite/drizzle | tự lo |
| Charts tài chính | Vico / MPAndroidChart | fl_chart (rất tốt) | lib web (ECharts...) | victory-native | lib web |
| SAF / file access | ✅ Native trực tiếp | plugin (ổn) | plugin-fs (mobile hạn chế) | expo-file-system | hạn chế |
| Notification/background | ✅ WorkManager native | plugin workmanager | plugin, coverage chưa đủ | expo-notifications | hạn chế |
| Biometric | ✅ BiometricPrompt | local_auth (chín) | có plugin mobile | expo-local-auth | tự lo |
| Cộng đồng | Kotlin: lớn, Google back | Lớn nhất cross-platform (46% usage 2025) | Mạnh (~109k stars) nhưng mobile ít app production | Lớn nhất overall (JS) | Nhỏ, đang lớn |
| Học lại từ Java | Thấp (Kotlin) | Trung bình (Dart dễ) | Cao (Rust + web UI) | Trung bình (TS) | Cao (Rust) |
| Tận dụng roadmap hiện tại | ✅ 100% | ❌ Viết lại | ❌ Viết lại | ❌ Viết lại | ❌ Viết lại |
| iOS | Sau này (CMP stable từ 5/2025) | Ngay | Ngay (cần macOS build) | Ngay | Ngay (thô) |

---

## Đánh giá từng framework cho MoneyWallet

### 1. Kotlin Multiplatform + (sau này) Compose Multiplatform — KHUYẾN NGHỊ

**Hiện trạng 2026:** KMP stable, Google officially support để share business logic Android↔iOS; Jetpack libraries (Room, ViewModel, lifecycle, DataStore, Paging, SQLite) đều KMP-ready. Compose Multiplatform iOS **stable từ 1.8.0 (5/2025)**, hiện tại 1.12.1, render Metal 120Hz.

**Vì sao hợp nhất với MoneyWallet:**
- Phase 1–3 của roadmap (entities, DAO, repository) **chính là** shared KMP module — chỉ cần đặt vào `commonMain` ngay từ đầu thay vì module Android thuần. Không tốn thêm effort mà có sẵn option iOS.
- Mọi điểm đau trong issues đều là native Android (SAF crash #177, Drive #192, Dropbox #258, scoped storage #253) — ở lại native là giải quyết trực tiếp, không qua plugin trung gian.
- Không học ngôn ngữ mới; Kotlin là đích đến của roadmap rồi.

**Hạn chế:** nếu cần iOS *ngay*, CMP iOS dù stable vẫn ít app production hơn Flutter; share UI 85%+ đòi hỏi đầu tư CMP nghiêm túc.

### 2. Flutter 3.47 — lựa chọn cross-platform an toàn nhất (nếu cần iOS ngay)

**Hiện trạng 2026:** bản stable 8/2026; Impeller là renderer mặc định mọi nền tảng (xóa Skia trên Android 10+), hết jank shader-compile; 46% cross-platform dev dùng Flutter. Production users: Google Ads/Pay, Alibaba, BMW, Grab.

**Vì sao là plan B hợp lý:** ecosystem chín nhất cho finance app (fl_chart, drift ORM cho SQLite rất tốt, plugin biometric/workmanager ổn định), hot reload nhanh, một codebase ra 2 store.

**Cái giá:** vứt roadmap hiện tại; viết lại toàn bộ domain (transfer orchestration, recurrence, system categories...) bằng Dart — chính là phần dễ sai nhất (đã thấy họ bug 1-cent). Ước tính solo dev: **6–9 tháng** để đạt feature parity, so với 4–5 tháng migration native.

### 3. Tauri Mobile 2.x (Rust) — đáp ứng yêu cầu "Rust + cộng đồng ổn"

**Hiện trạng 2026:** Tauri 2.0 stable 10/2024 kèm iOS/Android; dòng hiện tại 2.11.x. Đánh giá chung: **"production-ready but not fully feature-complete" / "rough"** — ít app production mobile, một số plugin chỉ có bản desktop, iOS build bắt buộc macOS + Xcode. Cộng đồng mạnh (~109k stars, CrabNebula backing), plugin mobile có biometric, fs, notification nhưng coverage chưa đủ desktop.

**Vì sao chưa hợp cho MoneyWallet:** UI là webview (HTML/CSS/JS) — toàn bộ 356 layouts phải làm lại bằng web tech; SQLite qua Rust (rusqlite) tự lo schema/migration; background task + SAF trên mobile là vùng yếu nhất của Tauri. Rust cho correctness là tốt, nhưng **bạn đang cần ship app tài chính, không phải demo kỹ thuật**.

**Khi nào chọn:** nếu ưu tiên số 1 là "viết Rust" và chấp nhận mobile là second-class citizen trong 1–2 năm tới.

### 4. React Native (New Architecture) — không khuyến nghị cho trường hợp này

Mature, talent pool lớn nhất — nhưng lợi thế đó chỉ có ý nghĩa với team. Solo dev thì JS ecosystem churn + bridge native modules cho SAF/background là việc không đáng. Không có lý do gì chọn RN thay vì Flutter cho project này.

### 5. Dioxus (Rust) — chưa đủ chín cho mobile production

Mobile là "real target" (webview wry), nhưng consensus cộng đồng Rust 2026: *"nothing in rust ui is really mature especially on mobile"*; Dioxus mạnh ở web/desktop, YC-backed, dùng bởi Airbus/ESA — nhưng cho **mobile finance app production thì chưa**. Loại.

---

## Đề xuất hành động cụ thể

1. **Giữ roadmap 7 phases**, với 1 điều chỉnh nhỏ ở Phase 1: đặt entities/DAO/repository vào **Kotlin Multiplatform shared module** (`commonMain`) dùng Room KMP, thay vì module Android thuần. Android app consume như bình thường. Effort tăng không đáng kể, nhưng mở sẵn cửa iOS.
2. **Không** đầu tư Flutter/Tauri lúc này. Nếu sau này cần iOS gấp: đánh giá lại giữa CMP (share tiếp từ module đã có) vs Flutter (viết lại UI).
3. Vàng (P2) làm trên shared module → sau này iOS có luôn tính năng vàng miễn phí.

---

## Nguồn

- Tauri mobile status 2026: research notes từ cộng đồng (autonome/peek, murmur-io, mindos wiki, rust-gui-desktop-ecosystem-state) — đồng thuận "production-ready but rough".
- KMP/CMP: Google developer.android.com/kotlin/multiplatform (9/2026) — "officially supported... stable and production-ready"; CMP iOS stable từ 1.8.0.
- Flutter: 3.47 release notes (8/2026); so sánh softaims.com 2026 (code sharing 85–95% vs KMM 40–60% logic-only).
- Dioxus: vibingtalk + botmonster 2026 — mobile chưa mature.
