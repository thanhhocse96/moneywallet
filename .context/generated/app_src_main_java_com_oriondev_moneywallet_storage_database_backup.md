<!-- AUTO_START | hash: a82e9079 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database/backup`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 6

## [auto] Public Functions

### `exportDatabase` (line 47)
```text
public abstract void exportDatabase(@NonNull File tempFolder) throws ExportException
```

### `exportAttachments` (line 49)
```text
public void exportAttachments(@NonNull File attachmentFolder) throws ExportException
```

### `importDatabase` (line 59)
```text
public void importDatabase(@NonNull File temporaryFolder, @NonNull File databaseFolder) throws ImportException
```

### `importAttachments` (line 73)
```text
public void importAttachments(@NonNull File attachmentFolder) throws ImportException
```

### `getBackupServices` (line 43)
```text
public static List<BackupService> getBackupServices()
```

### `getExtension` (line 47)
```text
public static String getExtension(boolean encrypted)
```

### `exportDatabase` (line 57)
```text
@Override public void exportDatabase(@NonNull File tempFolder) throws ExportException
```

### `importDatabase` (line 50)
```text
@Override public void importDatabase(@NonNull File temporaryFolder) throws ImportException
```

### `importAttachmentFiles` (line 107)
```text
@Override public void importAttachmentFiles(@NonNull File attachmentFolder) throws IOException, ImportException
```

## [auto] Types

### `AbstractBackupExporter`

| Field | Type |
|-------|------|
| `exportDatabase` | `method` |
| `exportAttachments` | `method` |

### `AbstractBackupImporter`

| Field | Type |
|-------|------|
| `importDatabase` | `method` |
| `importAttachments` | `method` |

### `BackupManager`

| Field | Type |
|-------|------|
| `getBackupServices` | `method` |
| `getExtension` | `method` |

### `DefaultBackupExporter`

| Field | Type |
|-------|------|
| `exportDatabase` | `method` |

### `DefaultBackupImporter`

| Field | Type |
|-------|------|
| `importDatabase` | `method` |
| `importAttachmentFiles` | `method` |

### `LegacyBackupImporter`

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database.backup;
import android.content.ContentResolver;
import android.database.Cursor;
import androidx.annotation.NonNull;
import com.oriondev.moneywallet.storage.database.ExportException;
import com.oriondev.moneywallet.storage.database.SQLDatabaseExporter;
import com.oriondev.moneywallet.storage.database.model.Attachment;
import java.io.File;
import java.util.ArrayList;
import java.util.List;
// ... +22 more
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