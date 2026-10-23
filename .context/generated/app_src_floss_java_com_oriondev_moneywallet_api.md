<!-- AUTO_START | hash: 5d35d1c3 | built: 2026-10-20T15:41 -->
# Context: `app/src/floss/java/com/oriondev/moneywallet/api`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `getServiceById` (line 46)
```text
public static AbstractBackendServiceDelegate getServiceById(String backendId, AbstractBackendServiceDelegate.BackendServiceStatusListener listener)
```

### `getServiceAPIById` (line 56)
```text
public static IBackendServiceAPI getServiceAPIById(Context context, String backendId) throws BackendException
```

### `getBackupServices` (line 67)
```text
public static List<BackupService> getBackupServices()
```

### `getFile` (line 76)
```text
public static IFile getFile(String backendId, String encoded)
```

## [auto] Types

### `BackendServiceFactory`

| Field | Type |
|-------|------|
| `getServiceById` | `method` |
| `getServiceAPIById` | `method` |
| `getBackupServices` | `method` |
| `getFile` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.api;
import android.content.Context;
import android.os.Build;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.api.disk.DiskBackendService;
import com.oriondev.moneywallet.api.disk.DiskBackendServiceAPI;
import com.oriondev.moneywallet.api.saf.SAFBackendService;
import com.oriondev.moneywallet.api.saf.SAFBackendServiceAPI;
import com.oriondev.moneywallet.model.BackupService;
import com.oriondev.moneywallet.model.IFile;
// ... +4 more
```

<!-- AUTO_END -->

<!-- MANUAL_START -->
## [manual] Design Decisions
> Tại sao module này được thiết kế như vậy? Trade-off gì đã được chọn?

_Chưa có ghi chú._

## [manual] Invariants & Constraints
> Các quy tắc KHÔNG BAO GIỜ được vi phạm khi sửa code ở đây.

_Chưa có ghi chú._

## [manual] Test Strategy
> Cách test module này: unit/integration, mock gì, test case quan trọng nhất là gì?

_Chưa có ghi chú._

## [manual] Behavior chưa implement (TODO)
> Các behavior đã thiết kế nhưng chưa code. LLM đọc để không "sáng tác" sai hướng.

_Chưa có ghi chú._
<!-- MANUAL_END -->