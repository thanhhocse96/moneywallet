# AGENTS_ARCH.md — MoneyWallet
# Architecture, Naming, Android Security
# Đọc khi task liên quan đến architecture decision, thêm file mới, hoặc security review.

---

## Architecture — Biết rõ trước khi code

### Boundary rules

| Thuộc về | Layer | Ví dụ |
|---|---|---|
| `moneywallet/` (source repo) | App source | Java/Kotlin source, XML layouts, resources, Gradle build, ProGuard rules |
| `build/`, `.gradle/`, `local.properties` | Generated | KHÔNG edit thủ công, KHÔNG commit |
| External libs | Không sửa source | Thư viện trong `build.gradle` (material, room, etc.) — chỉ thêm/bớt khi human approve |
| Android SDK / Emulator | Runtime | Không cài toolchain vào repo |

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
