<!-- AUTO_START | hash: e62652f5 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/api/disk`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `getId` (line 51)
```text
@Override public String getId()
```

### `getName` (line 56)
```text
@Override public int getName()
```

### `getBackupCoverMessage` (line 61)
```text
@Override public int getBackupCoverMessage()
```

### `getBackupCoverAction` (line 66)
```text
@Override public int getBackupCoverAction()
```

### `isServiceEnabled` (line 71)
```text
@Override public boolean isServiceEnabled(Context context)
```

### `setup` (line 78)
```text
@Override public void setup(final ComponentActivity activity) throws BackendException
```

### `teardown` (line 115)
```text
@Override public void teardown(ComponentActivity activity) throws BackendException
```

### `handlePermissionsResult` (line 120)
```text
@Override public boolean handlePermissionsResult(Context context, int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults)
```

### `upload` (line 53)
```text
@Override public LocalFile upload(LocalFile folder, File file, ProgressInputStream.UploadProgressListener listener) throws BackendException
```

### `download` (line 74)
```text
@Override public File download(File folder, @NonNull LocalFile file, ProgressOutputStream.DownloadProgressListener listener) throws BackendException
```

### `list` (line 80)
```text
@Override public List<IFile> list(LocalFile folder) throws BackendException
```

### `newFolder` (line 95)
```text
@Override public LocalFile newFolder(LocalFile parent, String name) throws BackendException
```

### `getRootFolder` (line 113)
```text
public static LocalFile getRootFolder()
```

## [auto] Types

### `DiskBackendService`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getBackupCoverMessage` | `method` |
| `getBackupCoverAction` | `method` |
| `isServiceEnabled` | `method` |
| `setup` | `method` |
| `teardown` | `method` |
| `handlePermissionsResult` | `method` |

### `DiskBackendServiceAPI`

| Field | Type |
|-------|------|
| `load` | `method` |
| `download` | `method` |
| `list` | `method` |
| `newFolder` | `method` |
| `getRootFolder` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.api.disk;
import android.Manifest;
import android.content.Context;
import android.content.pm.PackageManager;
import com.afollestad.materialdialogs.DialogAction;
import com.afollestad.materialdialogs.MaterialDialog;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.api.AbstractBackendServiceDelegate;
import com.oriondev.moneywallet.api.BackendException;
import com.oriondev.moneywallet.api.BackendServiceFactory;
// ... +24 more
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