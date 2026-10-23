<!-- AUTO_START | hash: 0cae4721 | built: 2026-10-20T15:42 -->
# Context: `app/src/proprietary/java/com/oriondev/moneywallet/api/dropbox`

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

### `setup` (line 76)
```text
@Override public void setup(ComponentActivity activity) throws BackendException
```

### `teardown` (line 81)
```text
@Override public void teardown(final ComponentActivity activity) throws BackendException
```

### `upload` (line 74)
```text
@Override public DropBoxFile upload(DropBoxFile folder, File file, ProgressInputStream.UploadProgressListener listener) throws BackendException
```

### `download` (line 87)
```text
@Override public File download(File folder, @NonNull DropBoxFile file, ProgressOutputStream.DownloadProgressListener listener) throws BackendException
```

### `list` (line 99)
```text
@Override public List<IFile> list(DropBoxFile folder) throws BackendException
```

## [auto] Types

### `DropboxBackendService`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getBackupCoverMessage` | `method` |
| `getBackupCoverAction` | `method` |
| `isServiceEnabled` | `method` |
| `setup` | `method` |
| `teardown` | `method` |

### `DropboxBackendServiceAPI`

| Field | Type |
|-------|------|
| `load` | `method` |
| `download` | `method` |
| `list` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.api.dropbox;
import android.app.Activity;
import android.content.Context;
import android.content.SharedPreferences;
import androidx.activity.ComponentActivity;
import androidx.annotation.NonNull;
import com.afollestad.materialdialogs.DialogAction;
import com.afollestad.materialdialogs.MaterialDialog;
import com.dropbox.core.android.Auth;
import com.oriondev.moneywallet.BuildConfig;
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