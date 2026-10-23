<!-- AUTO_START | hash: ec27ef46 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database/data`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `isMultiWalletSupported` (line 39)
```text
public abstract boolean isMultiWalletSupported()
```

### `getColumns` (line 41)
```text
public abstract String[] getColumns(boolean uniqueWallet, String[] optionalColumns)
```

### `shouldLoadPeople` (line 43)
```text
public abstract boolean shouldLoadPeople()
```

### `cachePeople` (line 45)
```text
public void cachePeople(Cursor cursor)
```

### `exportData` (line 61)
```text
public abstract void exportData(Cursor cursor, String[] columns, Wallet... wallets) throws IOException
```

### `close` (line 63)
```text
public abstract void close() throws IOException
```

### `getOutputFile` (line 65)
```text
public abstract File getOutputFile()
```

### `getResultType` (line 67)
```text
public abstract String getResultType()
```

### `importData` (line 42)
```text
public abstract void importData() throws IOException
```

### `close` (line 254)
```text
public abstract void close() throws IOException
```

## [auto] Types

### `AbstractDataExporter`

| Field | Type |
|-------|------|
| `isMultiWalletSupported` | `method` |
| `getColumns` | `method` |
| `shouldLoadPeople` | `method` |
| `cachePeople` | `method` |
| `exportData` | `method` |
| `close` | `method` |
| `getOutputFile` | `method` |
| `getResultType` | `method` |

### `AbstractDataImporter`

| Field | Type |
|-------|------|
| `importData` | `method` |
| `close` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database.data;
import android.content.Context;
import android.database.Cursor;
import androidx.collection.LongSparseArray;
import com.oriondev.moneywallet.model.Wallet;
import com.oriondev.moneywallet.storage.database.Contract;
import com.oriondev.moneywallet.utils.DateUtils;
import java.io.File;
import java.io.IOException;
import java.util.Date;
// ... +14 more
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