<!-- AUTO_START | hash: 8b1c35b9 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database/data/csv`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 3

## [auto] Public Functions

### `isMultiWalletSupported` (line 43)
```text
@Override public boolean isMultiWalletSupported()
```

### `getColumns` (line 50)
```text
@Override public String[] getColumns(boolean uniqueWallet, String[] optionalColumns)
```

### `shouldLoadPeople` (line 81)
```text
@Override public boolean shouldLoadPeople()
```

### `exportData` (line 86)
```text
@Override public void exportData(Cursor cursor, String[] columns, Wallet... wallets) throws IOException
```

### `close` (line 153)
```text
@Override public void close() throws IOException
```

### `getOutputFile` (line 158)
```text
@Override public File getOutputFile()
```

### `getResultType` (line 163)
```text
@Override public String getResultType()
```

### `importData` (line 32)
```text
@Override public void importData() throws IOException
```

### `close` (line 82)
```text
@Override public void close() throws IOException
```

## [auto] Types

### `CSVDataExporter`

| Field | Type |
|-------|------|
| `isMultiWalletSupported` | `method` |
| `getColumns` | `method` |
| `shouldLoadPeople` | `method` |
| `exportData` | `method` |
| `close` | `method` |
| `getOutputFile` | `method` |
| `getResultType` | `method` |

### `CSVDataImporter`

| Field | Type |
|-------|------|
| `importData` | `method` |
| `close` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database.data.csv;
import android.content.Context;
import android.database.Cursor;
import android.text.TextUtils;
import com.opencsv.CSVParserWriter;
import com.opencsv.CSVWriter;
import com.oriondev.moneywallet.model.CurrencyUnit;
import com.oriondev.moneywallet.model.Wallet;
import com.oriondev.moneywallet.storage.database.Contract;
import com.oriondev.moneywallet.storage.database.data.AbstractDataExporter;
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