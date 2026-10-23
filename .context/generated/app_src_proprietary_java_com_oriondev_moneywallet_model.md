<!-- AUTO_START | hash: 9c48eb34 | built: 2026-10-20T15:42 -->
# Context: `app/src/proprietary/java/com/oriondev/moneywallet/model`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `createFromParcel` (line 84)
```text
@Override public DropBoxFile createFromParcel(Parcel in)
```

### `newArray` (line 89)
```text
@Override public DropBoxFile[] newArray(int size)
```

### `getPath` (line 95)
```text
public String getPath()
```

### `getName` (line 99)
```text
@Override public String getName()
```

### `getExtension` (line 104)
```text
@Override public String getExtension()
```

### `isDirectory` (line 110)
```text
@Override public boolean isDirectory()
```

### `getSize` (line 115)
```text
@Override public long getSize()
```

### `encodeToString` (line 120)
```text
@Override public String encodeToString()
```

### `describeContents` (line 134)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 139)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `createFromParcel` (line 77)
```text
@Override public GoogleDriveFile createFromParcel(Parcel in)
```

### `newArray` (line 82)
```text
@Override public GoogleDriveFile[] newArray(int size)
```

### `getName` (line 89)
```text
@Override public String getName()
```

### `getExtension` (line 94)
```text
@Override public String getExtension()
```

### `isDirectory` (line 100)
```text
@Override public boolean isDirectory()
```

### `getSize` (line 105)
```text
@Override public long getSize()
```

### `encodeToString` (line 110)
```text
@Override public String encodeToString()
```

### `getDriveFolder` (line 124)
```text
public DriveFolder getDriveFolder()
```

### `getDriveFile` (line 128)
```text
public DriveFile getDriveFile()
```

### `describeContents` (line 132)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 137)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

## [auto] Types

### `DropBoxFile`

| Field | Type |
|-------|------|
| `getPath` | `method` |
| `getName` | `method` |
| `getExtension` | `method` |
| `isDirectory` | `method` |
| `getSize` | `method` |
| `encodeToString` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `GoogleDriveFile`

| Field | Type |
|-------|------|
| `getName` | `method` |
| `getExtension` | `method` |
| `isDirectory` | `method` |
| `getSize` | `method` |
| `encodeToString` | `method` |
| `getDriveFolder` | `method` |
| `getDriveFile` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.model;
import android.os.Parcel;
import android.os.Parcelable;
import com.dropbox.core.v2.files.FileMetadata;
import com.dropbox.core.v2.files.FolderMetadata;
import com.dropbox.core.v2.files.Metadata;
import com.google.android.gms.drive.DriveId;
import org.json.JSONException;
import org.json.JSONObject;
import com.google.android.gms.drive.DriveFile;
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