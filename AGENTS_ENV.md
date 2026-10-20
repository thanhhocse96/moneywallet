# AGENTS_ENV.md — MoneyWallet
# Environment, Runtime, Gradle, Android SDK
# Đọc khi task liên quan đến chạy Gradle, build, emulator, thiết bị thực.

---

## Dev Repo vs Android Runtime — Không được nhầm

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

### Local dev runtime — máy hiện tại

Thông tin chi tiết của máy hiện tại nằm trong `.local/ENVIRONMENT.md`. File này local-only, có thể chứa credential, KHÔNG commit.

### Build commands

```bash
# Lint/compile (chạy trong PowerShell, thư mục repo root)
./gradlew :app:lintDebug
./gradlew :app:assembleDebug

# Unit test
./gradlew :app:testDebugUnitTest

# Assemble release (cần keystore/keys — KHÔNG commit)
./gradlew :app:assembleRelease
```

### Build flavors

```
floss × gmap
floss × osm
proprietary × gmap
proprietary × osm
```

Giữ build khả thi trên mọi combo. Không tự xóa flavor trừ khi human xác nhận.

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

### Tension trigger

Nếu không chắc path thuộc source hay runtime → ghi LOW tension + hỏi human.
