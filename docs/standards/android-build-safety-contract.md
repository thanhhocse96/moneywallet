# docs/standards/android-build-safety-contract.md — MoneyWallet
# Bắt buộc đọc trước khi sửa build.gradle, app/build.gradle, dependencies, ProGuard, flavor, signing.

## Quy tắc

1. Không tự bump `versionCode`/`versionName` trừ khi human xác nhận.
2. Không tự xóa/thêm dependency trừ khi human approve.
3. Không commit `build/`, `.gradle/`, `local.properties`, `*.keystore`, `key.properties`.
4. API key (Google Maps, Dropbox, Drive) phải ở `gradle.properties` / `local.properties`, KHÔNG commit.
5. Giữ build khả thi trên mọi combo flavor (`floss`/`proprietary` × `gmap`/`osm`).
6. ProGuard rules trong `app/proguard-rules.pro` — không xóa rule cũ mà không lý do rõ.
7. Signing config không hardcode trong source; dùng `gradle.properties` / `local.properties`.

## Lệnh verify

```bash
# Lint/compile
./gradlew :app:lintDebug
./gradlew :app:assembleDebug

# Unit test
./gradlew :app:testDebugUnitTest
```

> Agent không tự chạy build/lint qua tool. Output lệnh trên để human tự chạy.
