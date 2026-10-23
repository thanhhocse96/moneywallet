<!-- AUTO_START | hash: 07122472 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/api/saf`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `getId` (line 58)
```text
@Override public String getId()
```

### `getName` (line 63)
```text
@Override public int getName()
```

### `getBackupCoverMessage` (line 68)
```text
@Override public int getBackupCoverMessage()
```

### `getBackupCoverAction` (line 73)
```text
@Override public int getBackupCoverAction()
```

### `isServiceEnabled` (line 78)
```text
@Override public boolean isServiceEnabled(Context context)
```

### `setup` (line 83)
```text
@Override public void setup(final ComponentActivity activity)
```

### `teardown` (line 104)
```text
@Override public void teardown(final ComponentActivity activity)
```

### `handleActivityResult` (line 154)
```text
@Override public boolean handleActivityResult(Context context, int requestCode, int resultCode, Intent data)
```

### `upload` (line 60)
```text
@Override public SAFFile upload(@Nullable SAFFile folder, File file, ProgressInputStream.UploadProgressListener listener) throws BackendException
```

### `download` (line 140)
```text
@Override public File download(File folder, @NonNull SAFFile file, ProgressOutputStream.DownloadProgressListener listener) throws BackendException
```

### `list` (line 193)
```text
@Override public List<IFile> list(@Nullable SAFFile folder) throws BackendException
```

### `newFolder` (line 214)
```text
@Override public SAFFile newFolder(SAFFile parent, String name) throws BackendException
```

## [auto] Types

### `SAFBackendService`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getBackupCoverMessage` | `method` |
| `getBackupCoverAction` | `method` |
| `isServiceEnabled` | `method` |
| `setup` | `method` |
| `teardown` | `method` |
| `handleActivityResult` | `method` |

### `SAFBackendServiceAPI`

| Field | Type |
|-------|------|
| `load` | `method` |
| `download` | `method` |
| `list` | `method` |
| `newFolder` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.api.saf;
import android.content.Context;
import android.content.Intent;
import android.content.SharedPreferences;
import android.net.Uri;
import com.afollestad.materialdialogs.DialogAction;
import com.afollestad.materialdialogs.MaterialDialog;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.api.AbstractBackendServiceDelegate;
import com.oriondev.moneywallet.api.BackendServiceFactory;
// ... +25 more
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