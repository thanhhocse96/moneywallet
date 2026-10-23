<!-- AUTO_START | hash: 7e138799 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database/data/pdf`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `isMultiWalletSupported` (line 59)
```text
@Override public boolean isMultiWalletSupported()
```

### `getColumns` (line 64)
```text
@Override public String[] getColumns(boolean uniqueWallet, String[] optionalColumns)
```

### `shouldLoadPeople` (line 96)
```text
@Override public boolean shouldLoadPeople()
```

### `exportData` (line 101)
```text
@Override public void exportData(Cursor cursor, String[] columns, Wallet... wallets) throws IOException
```

### `close` (line 240)
```text
@Override public void close() throws IOException
```

### `getOutputFile` (line 245)
```text
@Override public File getOutputFile()
```

### `getResultType` (line 250)
```text
@Override public String getResultType()
```

## [auto] Types

### `PDFDataExporter`

| Field | Type |
|-------|------|
| `isMultiWalletSupported` | `method` |
| `getColumns` | `method` |
| `shouldLoadPeople` | `method` |
| `exportData` | `method` |
| `close` | `method` |
| `getOutputFile` | `method` |
| `getResultType` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database.data.pdf;
import android.content.Context;
import android.database.Cursor;
import android.text.TextUtils;
import com.itextpdf.text.BaseColor;
import com.itextpdf.text.Chapter;
import com.itextpdf.text.Chunk;
import com.itextpdf.text.Document;
import com.itextpdf.text.DocumentException;
import com.itextpdf.text.Element;
// ... +18 more
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