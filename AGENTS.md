# AGENTS.md — MoneyWallet

> Đọc file này TRƯỚC KHI làm bất kỳ task nào.
> Đây là protocol bắt buộc cho mọi AI agent làm việc trong project này.

---

## 0. Milestone hiện tại

Current milestone: **P0 — Toolchain & compliance**

Milestone source of truth: `.context/MILESTONES.md`.

Quy tắc quản lý tension theo milestone:

- Trong cùng milestone hiện tại, tension đã `RESOLVED_ACTIVE` nằm trong `.context/TENSIONS_ACTIVE.md`.
- Chỉ khi human tuyên bố chuyển sang milestone/version mới, agent mới move các tensions đã `RESOLVED_ACTIVE` sang `.context/TENSIONS_HISTORY.md` (Status: ARCHIVED).
- Khi chuyển milestone, agent phải update cả `AGENTS.md` và `.context/MILESTONES.md`, đồng thời move milestone cũ sang `.context/MILESTONES_HISTORY.md`.
- `.context/TENSIONS_HISTORY.md` và `MILESTONES_HISTORY.md` không load mặc định.

---

## 1. Đọc trước — Bắt buộc

Mỗi task bắt đầu bằng 5 bước này, không có ngoại lệ:

```
1. Đọc .context/GLOBAL.md       → hiểu stack, module index, invariants, phase scope
2. Đọc .context/MILESTONES.md   → biết milestone hiện tại và checklist
3. Đọc .context/TENSIONS_OPEN.md     → check toàn bộ OPEN tensions
4. Đọc .context/TENSIONS_ACTIVE.md   → check RESOLVED_ACTIVE của milestone (dùng tag filter)
5. Đọc .context/modules/<module>.md  → load context của module sắp sửa
```

Nếu `.context/modules/<module>.md` chưa tồn tại → load GLOBAL + hỏi lại trước khi tạo.

Nếu `[manual]` section trong module file còn template placeholder → **DỪNG, báo lại**, không tự điền assumption.

### Context load rules

- `.context/planning/*.md` chỉ đọc khi task liên quan scope, architecture, data model, version planning, hoặc tương lai feature boundary.
- `.context/proposals/` (nếu có) là local review, không active protocol. Không load mặc định.
- History files chỉ load khi audit hoặc human yêu cầu.
- Folder structure giúp human; startup protocol trong `AGENTS.md` là source of truth cho load order.

### Encoding rules

- Context, docs, Java, Kotlin, XML, JSON, Gradle files must remain UTF-8.
- Tiếng Việt và dấu phải giữ nguyên (không mojibake).
- Nếu đọc thấy lỗi encoding → dừng, fix trước khi edit semantic.

### Build & runtime safety — Bắt buộc

Trước mọi task sửa `build.gradle`, `app/build.gradle`, dependencies, ProGuard, flavor, signing, agent PHẢI đọc:

`docs/standards/android-build-safety-contract.md`

---

## 2. Architecture — Biết rõ trước khi code

### Boundary rules

| Thuộc về | Layer | Ví dụ |
|---|---|---|
| `moneywallet/` (source repo) | App source | Java/Kotlin source, XML layouts, resources, Gradle build, ProGuard rules |
| `build/`, `.gradle/`, `local.properties` | Generated | KHÔNG edit thủ công, KHÔNG commit |
| External libs | Không sửa source | Thư viện trong `build.gradle` (material, room, etc.) — chỉ thêm/bớt khi human approve |
| Android SDK / Emulator | Runtime环境 | Không cài toolchain vào repo |

**Rule quyết định nhanh**: nếu thay dependency mà feature bị mất → feature thuộc app source.

### Naming — Không bao giờ đổi

```
Package:              com.oriondev.moneywallet
Class prefix (Java):  MoneyWallet (không prefix hàm toàn cục như PHP)
Text domain (i18n):   com.oriondev.moneywallet
Build flavors:        floss/proprietary × gmap/osm
ProGuard rules:       app/proguard-rules.pro
```

### Android security — Không thương lượng

```java
// Input — luôn validate/sanitize
String input = ...; // không concat trực tiếp vào SQL

// SQLite query — dùng selectionArgs, KHÔNG chuỗi concat
db.query("wallet", null, "id = ?", new String[]{id}, null, null, null);

// Output — KHông hardcode secret, API key trong source
// API key (Google Maps, Dropbox, Drive) phải ở gradle.properties / local.properties, KHÔNG commit
```

---

## 3. Workflow — Mỗi Task

1. Load context (GLOBAL → MILESTONES → TENSIONS_OPEN → TENSIONS_ACTIVE → module)
2. Đọc [manual] của module — hiểu constraints và invariants
3. Nếu [manual] còn placeholder → DỪNG, hỏi lại
4. Detect tensions (xem Section 4)
5. Nếu tension HIGH → generate `TENSIONS_OPEN.md` entry → DỪNG, chờ quyết định
6. Nếu tension LOW hoặc không có → tiếp tục
7. Route response (CODE_NOW / ASK_ARCHITECTURE / EXPLAIN)
8. Implement — follow coding standards (package, security, ProGuard, permissions)
9. Self-check (xem checklist cuối file)
10. Update `.context/` nếu có quyết định mới
11. Chỉ human chuyển milestone mới thì update AGENTS + MILESTONES + move archive

### Sau khi implement (khi có code)

```bash
# Lint/compile Gradle (chạy trong PowerShell, thư mục repo root)
./gradlew :app:lintDebug
./gradlew :app:assembleDebug

# Unit test (nếu có)
./gradlew :app:testDebugUnitTest
```

> Cuối mỗi lượt có thay đổi code, agent phải **output lệnh trên dưới dạng text** để user tự copy và chạy. Agent không được tự chạy build/lint qua tool.

### Command responsiveness — Bắt buộc

- Nếu command không trả output, timeout, hoặc tool kill → **DỪNG ngay**.
- Không tự retry / poll.
- Đưa exact command + lý do cho human chạy thủ công.
- Ưu tiên human cho Gradle, Android SDK, emulator, device.
- Agent chỉ được chạy lại sau khi human cung cấp output hoặc yêu cầu rõ ràng agent thử lại.

### Agent response routing — Bắt buộc

Sau khi load context, agent **không** mặc định viết plan dài rồi chờ approve. Chọn một trong ba mode:

| Mode | Khi nào | Agent làm gì |
|---|---|---|
| **`CODE_NOW`** | Human chỉ đường implement rõ (`theo E`, `làm T-1 A+C1`, `fix`, `implement`, đã chọn phương án A/B/C) | Đọc context → sửa source ngay → self-check → báo human chạy build/test. Plan trong response **ngắn** (files + mục tiêu), không chặn bằng “chờ approve”. |
| **`ASK_ARCHITECTURE`** | Nhiều hướng hợp lệ, boundary chưa rõ, HIGH tension, hoặc human hỏi *nên làm thế nào / so sánh* | Chỉ hỏi hoặc trình bày trade-off **kiến trúc & phạm vi** — **không** sửa file. Chờ human chọn hướng rồi chuyển `CODE_NOW`. |
| **`EXPLAIN`** | Human hỏi *giải thích kỹ*, *tại sao*, *T2 là gì*, audit/review only | Giải thích đủ sâu; **không** code trừ khi human nói tiếp “làm luôn” / chọn phương án. |

**Quy tắc nhanh:**

- Có **một** hướng đã được human chọn → `CODE_NOW` (không hỏi lại “bạn có muốn implement không?”).
- Human hỏi **so sánh phương án** → `ASK_ARCHITECTURE` hoặc `EXPLAIN`; chưa code.
- Human giao **audit / đọc codebase** → báo cáo compact theo domain; chỉ code khi human giao fix cụ thể hoặc milestone checklist.
- Human giao **ghi milestone / standard / protocol** → cập nhật `.context/` hoặc `docs/standards/` ngay (`CODE_NOW` cho docs).
- `[manual]` còn placeholder, tension HIGH, hoặc đụng `build/`/`.gradle/` → **DỪNG** (không thuộc ba mode trên).

### Decision Memo — Bắt buộc khi xin human quyết định

Human quyết định trên bằng chứng, không quyết trên lời khai. Mọi lần agent cần human quyết (tension, `ASK_ARCHITECTURE`, milestone approval, scope change, dependency mới), agent phải trình theo format 7 mục:

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
- Khẳng định về behavior thư viện ngoài phải cite docs/changelog đúng version trong `build.gradle`; kiến thức tổng quát không đủ điều kiện làm premise cho invariant/decision doc.
- Fix nào lật đổ premise trong decision doc thì update doc đó **trong cùng đợt fix**.

### Tension Detection

Ghi tension khi phát hiện conflict giữa task yêu cầu và constraint đã có trong `[manual]`.

### Format ghi vào `.context/TENSIONS_OPEN.md`

```markdown
## [YYYY-MM-DD HH:MM] | [module]
Tension:    Mô tả conflict ngắn gọn
Context:    Đang làm task gì
Proposal:   Agent muốn làm gì
Constraint: [manual] rule nào conflict (quote lại)
Severity:   low | high
Tags:       tag-one, tag-two
Milestone:  P0 / P1 / ...
Evidence:   [artifact nhìn được chứng minh tension có thật — optional nhưng nên có]
Default:    [severity low: phương án conservative + mốc nếu human không quyết. Severity high: luôn ghi "DỪNG chờ human"]
Status:     OPEN
Resolved:
Decision:   OPEN
```

Agent không được parse `Decision` để suy ra state. Chỉ dùng `Status`.

Allowed `Status`: `OPEN`, `RESOLVED_ACTIVE`, `ARCHIVED`.

Allowed `Severity`: `low`, `high`.

Tag taxonomy hiện tại:

```text
agent
android
build
data-layer
ui
flavor
backup
security
permission
sql
proguard
migration
planning
```

Khi cần tag mới, update taxonomy trong file này trước khi dùng.

### Routing

```
Severity LOW  → ghi tension → tiếp tục theo hướng conservative → báo human review sau
Severity HIGH → ghi tension → DỪNG task → chờ human fill Decision
```

### Tension files và archive

`.context/TENSIONS_OPEN.md` chỉ chứa `Status: OPEN`.

`.context/TENSIONS_ACTIVE.md` chỉ chứa `Status: RESOLVED_ACTIVE` của milestone hiện tại.

`.context/TENSIONS_HISTORY.md` chỉ chứa `Status: ARCHIVED`.

Khi human resolve một OPEN tension, agent move entry từ `TENSIONS_OPEN.md` sang `TENSIONS_ACTIVE.md`, set `Status: RESOLVED_ACTIVE`, set `Resolved: YYYY-MM-DD`, và ghi decision.

Khi human tuyên bố chuyển sang version/milestone mới, agent phải move các entry `Status: RESOLVED_ACTIVE` của milestone cũ sang `.context/TENSIONS_HISTORY.md`, đổi `Status: ARCHIVED`.

Không load `.context/TENSIONS_HISTORY.md` mặc định khi bắt đầu task. Chỉ đọc history khi cần audit quyết định cũ hoặc human yêu cầu.

`Status: OPEN` luôn đọc đầy đủ, không filter theo tag. `TENSIONS_ACTIVE.md` được đọc với tag filter: entries match task tag đọc đầy đủ; entries không match chỉ đọc title/status/tags. Nếu không chắc, đọc đầy đủ.

---

## 4. Coding Standards (Java/Kotlin/Android)

- Android Coding Standards mindset.
- Package `com.oriondev.moneywallet`; không đổi package-id.
- Sanitize input, tránh SQL injection (dùng selectionArgs).
- Không hardcode secret/API key trong source; dùng `gradle.properties` / `local.properties`.
- Không dùng `@SuppressLint` trừ khi có lý do rõ và ghi comment.
- Runtime permission: kiểm tra trước khi truy cập storage/camera/location.
- UTF-8 everywhere.
- Không commit `build/`, `.gradle/`, `local.properties`, `*.keystore`, `key.properties`.

---

## 5. Module-Specific Rules

Xem `.context/modules/*.md` (load theo task).

Tóm tắt nhanh:

- Data layer: `SQLDatabase`, `ContentProvider`, `Contract` — không thay đổi schema cũ mà không migration test.
- UI layer: Activity/Fragment, Loader (hiện tại), ViewModel+Flow (roadmap P4).
- Backup: SAF (Storage Access Framework), Google Drive, Dropbox — không abort app khi lỗi.
- Flavors: `floss`/`proprietary` × `gmap`/`osm`; giữ build khả thi trên mọi combo.
- Không xóa code cũ khi chưa có test oracle pass (theo roadmap migration).

---

## 6. Task Format (khi viết prompt / plan)

```
## Context
(loaded from .context/ + docs/)

## Goal
...

## Constraints / Invariants
...

## Allowed
...

## Forbidden
...

## Acceptance
...

## Known Tensions (nếu có)
...
```

---

## 7. Self-Check Checklist (bắt buộc cuối task)

- [ ] Đã load 5 files `.context/` theo protocol.
- [ ] Current milestone trong AGENTS.md match MILESTONES.md.
- [ ] Không vi phạm invariants (no hardcoded secret, SQL selectionArgs, package đúng, ProGuard ok).
- [ ] Tensions mới (nếu có) đã ghi OPEN đúng format.
- [ ] `.context/` files được update nếu có decision mới (GLOBAL, module, planning, MILESTONES).
- [ ] Không sửa >5 files trừ khi có lý do rõ (và note).
- [ ] Encoding UTF-8, tiếng Việt ok.
- [ ] (khi có code) Output exact commands cho human build/test/verify.
- [ ] Command timeout → handed off exact cmd.
- [ ] **Mọi câu "repo chưa có X" / "repo đã có X" đều đã grep trước khi viết.**
- [ ] **Không sửa `build/`, `.gradle/`, `local.properties`.**

---

## 8. Version & Milestones (dựa trên roadmap hiện có)

Theo `.context/MILESTONES.md`:

| Phase | Nội dung |
|---|---|
| P0 | Toolchain & compliance |
| P1 | Room core + validate trên `.db` thật |
| P2 | Vertical slice: currency + vàng trên stack mới |
| P3 | Port write orchestration sang Repository |
| P4 | Migrate UI: Loader → Flow, xóa Provider |
| P5 | UI modernization (M3, thay lib chết) |
| P6 | Vàng phase 2: giá tự động |

### Quy tắc version

- Version dùng `versionCode` / `versionName` trong `app/build.gradle`.
- Không tự bump versionCode/versionName trừ khi human xác nhận.
- Khi chuyển phase, update đồng bộ `AGENTS.md`, `.context/MILESTONES.md`.

---

## 9. Dev Repo vs Android Runtime — Không được nhầm

Repo này (`D:\Github\moneywallet`) là **source repo để dev**, KHÔNG phải Android runtime.

Android runtime cần: Android SDK, emulator hoặc thiết bị thực, JDK.

Nếu có file `.local/ENVIRONMENT.md`, agent phải đọc file đó để biết path môi trường local của máy hiện tại.

Nếu chưa có `.local/ENVIRONMENT.md` và task cần thao tác với Android runtime (build/install trên thiết bị, chạy emulator, adb), agent PHẢI hỏi human cung cấp Android SDK path và device/emulator trước.

Tạo `.local/ENVIRONMENT.md` (gitignored, local-only) khi có:

```text
ANDROID_HOME=...
ANDROID_SDK_ROOT=...
EMULATOR_SERIAL=... (hoặc thiết bị thực serial)
JDK_HOME=...
```

File `.local/ENVIRONMENT.md` là machine-local, có thể chứa credential, KHÔNG commit.

### Source repo chỉ chứa

- App source: `app/src/`
- Gradle files: `build.gradle`, `settings.gradle`, `gradle.properties`
- Context/docs/dev files: `.context/`, `docs/`, `AGENTS.md`, `README.md`

### Source repo KHÔNG được chứa

- `build/`
- `.gradle/`
- `local.properties`
- `*.keystore`, `key.properties`
- `captures/`
- `.externalNativeBuild/`
- External libs source

---

Nếu conflict hoặc không chắc → ghi tension + hỏi human.

**Bắt đầu mọi session bằng việc đọc GLOBAL + MILESTONES + TENSIONS_OPEN.**
