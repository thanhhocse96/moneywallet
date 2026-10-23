<!-- AUTO_START | hash: 75a9badc | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/api`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 4

## [auto] Public Functions

### `uploadFile` (line 44)
```text
@Override public IFile uploadFile(IFile folder, File file, ProgressInputStream.UploadProgressListener listener) throws BackendException
```

### `downloadFile` (line 55)
```text
@Override public File downloadFile(File folder, IFile file, ProgressOutputStream.DownloadProgressListener listener) throws BackendException
```

### `getFolderContent` (line 66)
```text
@Override public List<IFile> getFolderContent(IFile folder) throws BackendException
```

### `createFolder` (line 77)
```text
@Override public IFile createFolder(IFile parent, String name) throws BackendException
```

### `getId` (line 40)
```text
public abstract String getId()
```

### `getBackupCoverMessage` (line 42)
```text
@StringRes public abstract int getBackupCoverMessage()
```

### `getName` (line 45)
```text
@StringRes public abstract int getName()
```

### `getBackupCoverAction` (line 48)
```text
@StringRes public abstract int getBackupCoverAction()
```

### `isServiceEnabled` (line 51)
```text
public abstract boolean isServiceEnabled(Context context)
```

### `setup` (line 53)
```text
public abstract void setup(ComponentActivity activity) throws BackendException
```

### `teardown` (line 55)
```text
public abstract void teardown(ComponentActivity activity) throws BackendException
```

### `handlePermissionsResult` (line 57)
```text
public boolean handlePermissionsResult(Context context, int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults)
```

### `handleActivityResult` (line 61)
```text
public boolean handleActivityResult(Context context, int requestCode, int resultCode, Intent data)
```

### `onBackendStatusChange` (line 73)
```text
void onBackendStatusChange(boolean enabled)
```

### `isRecoverable` (line 46)
```text
public boolean isRecoverable()
```

### `uploadFile` (line 34)
```text
IFile uploadFile(IFile folder, File file, ProgressInputStream.UploadProgressListener listener) throws BackendException
```

### `downloadFile` (line 36)
```text
File downloadFile(File folder, IFile file, ProgressOutputStream.DownloadProgressListener listener) throws BackendException
```

### `getFolderContent` (line 38)
```text
List<IFile> getFolderContent(IFile folder) throws BackendException
```

### `createFolder` (line 40)
```text
IFile createFolder(IFile parent, String name) throws BackendException
```

## [auto] Types

### `AbstractBackendServiceAPI`

| Field | Type |
|-------|------|
| `loadFile` | `method` |
| `downloadFile` | `method` |
| `getFolderContent` | `method` |
| `createFolder` | `method` |

### `AbstractBackendServiceDelegate`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getBackupCoverMessage` | `method` |
| `getName` | `method` |
| `getBackupCoverAction` | `method` |
| `isServiceEnabled` | `method` |
| `setup` | `method` |
| `teardown` | `method` |
| `handlePermissionsResult` | `method` |
| `handleActivityResult` | `method` |

### `BackendServiceStatusListener`

| Field | Type |
|-------|------|
| `onBackendStatusChange` | `method` |

### `BackendException`

| Field | Type |
|-------|------|
| `isRecoverable` | `method` |

### `IBackendServiceAPI`

| Field | Type |
|-------|------|
| `loadFile` | `method` |
| `downloadFile` | `method` |
| `getFolderContent` | `method` |
| `createFolder` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.api;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import com.oriondev.moneywallet.model.IFile;
import com.oriondev.moneywallet.utils.ProgressInputStream;
import com.oriondev.moneywallet.utils.ProgressOutputStream;
import java.io.File;
import java.util.List;
import android.content.Context;
import android.content.Intent;
// ... +2 more
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