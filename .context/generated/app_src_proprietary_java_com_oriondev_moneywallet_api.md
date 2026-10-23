<!-- AUTO_START | hash: 9dc82101 | built: 2026-10-20T15:42 -->
# Context: `app/src/proprietary/java/com/oriondev/moneywallet/api`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `getServiceById` (line 54)
```text
public static AbstractBackendServiceDelegate getServiceById(String backendId, AbstractBackendServiceDelegate.BackendServiceStatusListener listener)
```

### `getServiceAPIById` (line 68)
```text
public static IBackendServiceAPI getServiceAPIById(Context context, String backendId) throws BackendException
```

### `getBackupServices` (line 83)
```text
public static List<BackupService> getBackupServices()
```

### `getFile` (line 94)
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
import com.oriondev.moneywallet.api.dropbox.DropboxBackendService;
import com.oriondev.moneywallet.api.dropbox.DropboxBackendServiceAPI;
import com.oriondev.moneywallet.api.google.GoogleDriveBackendService;
import com.oriondev.moneywallet.api.google.GoogleDriveBackendServiceAPI;
// ... +10 more
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