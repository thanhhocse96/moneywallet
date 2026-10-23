<!-- AUTO_START | hash: 028fa69d | built: 2026-10-20T15:42 -->
# Context: `app/src/proprietary/java/com/oriondev/moneywallet/api/google`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `getId` (line 62)
```text
@Override public String getId()
```

### `getName` (line 67)
```text
@Override public int getName()
```

### `getBackupCoverMessage` (line 72)
```text
@Override public int getBackupCoverMessage()
```

### `getBackupCoverAction` (line 77)
```text
@Override public int getBackupCoverAction()
```

### `isServiceEnabled` (line 82)
```text
@Override public boolean isServiceEnabled(Context context)
```

### `setup` (line 91)
```text
@Override public void setup(ComponentActivity activity) throws BackendException
```

### `teardown` (line 115)
```text
@Override public void teardown(final ComponentActivity activity) throws BackendException
```

### `handleActivityResult` (line 150)
```text
@Override public boolean handleActivityResult(Context context, int requestCode, int resultCode, Intent data)
```

### `upload` (line 72)
```text
@Override public GoogleDriveFile upload(GoogleDriveFile folder, File file, ProgressInputStream.UploadProgressListener listener) throws BackendException
```

### `download` (line 91)
```text
@Override public File download(File folder, @NonNull GoogleDriveFile file, ProgressOutputStream.DownloadProgressListener listener) throws BackendException
```

### `list` (line 106)
```text
@Override public List<IFile> list(GoogleDriveFile folder) throws BackendException
```

## [auto] Types

### `GoogleDriveBackendService`

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

### `GoogleDriveBackendServiceAPI`

| Field | Type |
|-------|------|
| `load` | `method` |
| `download` | `method` |
| `list` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.api.google;
import android.app.Activity;
import android.content.Context;
import android.content.Intent;
import com.afollestad.materialdialogs.DialogAction;
import com.afollestad.materialdialogs.MaterialDialog;
import com.google.android.gms.auth.api.signin.GoogleSignIn;
import com.google.android.gms.auth.api.signin.GoogleSignInAccount;
import com.google.android.gms.auth.api.signin.GoogleSignInClient;
import com.google.android.gms.auth.api.signin.GoogleSignInOptions;
// ... +37 more
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