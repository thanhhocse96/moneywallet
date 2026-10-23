<!-- AUTO_START | hash: 878fdfb1 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database/json`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 7

## [auto] Public Functions

### `exportHeader` (line 52)
```text
@Override public void exportHeader() throws ExportException
```

### `exportCurrencies` (line 64)
```text
@Override public void exportCurrencies(Cursor cursor) throws ExportException
```

### `exportWallets` (line 80)
```text
@Override public void exportWallets(Cursor cursor) throws ExportException
```

### `exportCategories` (line 96)
```text
@Override public void exportCategories(Cursor cursor) throws ExportException
```

### `exportEvents` (line 112)
```text
@Override public void exportEvents(Cursor cursor) throws ExportException
```

### `exportPlaces` (line 128)
```text
@Override public void exportPlaces(Cursor cursor) throws ExportException
```

### `exportPeople` (line 144)
```text
@Override public void exportPeople(Cursor cursor) throws ExportException
```

### `exportEventPeople` (line 160)
```text
@Override public void exportEventPeople(Cursor cursor) throws ExportException
```

### `exportDebts` (line 176)
```text
@Override public void exportDebts(Cursor cursor) throws ExportException
```

### `exportDebtPeople` (line 192)
```text
@Override public void exportDebtPeople(Cursor cursor) throws ExportException
```

### `exportBudgets` (line 208)
```text
@Override public void exportBudgets(Cursor cursor) throws ExportException
```

### `exportBudgetWallets` (line 224)
```text
@Override public void exportBudgetWallets(Cursor cursor) throws ExportException
```

### `exportSavings` (line 240)
```text
@Override public void exportSavings(Cursor cursor) throws ExportException
```

### `exportRecurrentTransactions` (line 256)
```text
@Override public void exportRecurrentTransactions(Cursor cursor) throws ExportException
```

### `exportRecurrentTransfers` (line 272)
```text
@Override public void exportRecurrentTransfers(Cursor cursor) throws ExportException
```

### `exportTransactions` (line 288)
```text
@Override public void exportTransactions(Cursor cursor) throws ExportException
```

### `exportTransactionPeople` (line 304)
```text
@Override public void exportTransactionPeople(Cursor cursor) throws ExportException
```

### `exportTransactionModels` (line 320)
```text
@Override public void exportTransactionModels(Cursor cursor) throws ExportException
```

### `exportTransfers` (line 336)
```text
@Override public void exportTransfers(Cursor cursor) throws ExportException
```

### `exportTransferPeople` (line 352)
```text
@Override public void exportTransferPeople(Cursor cursor) throws ExportException
```

### `exportTransferModels` (line 368)
```text
@Override public void exportTransferModels(Cursor cursor) throws ExportException
```

### `exportAttachments` (line 384)
```text
@Override public void exportAttachments(Cursor cursor) throws ExportException
```

### `exportTransactionAttachments` (line 400)
```text
@Override public void exportTransactionAttachments(Cursor cursor) throws ExportException
```

### `exportTransferAttachments` (line 416)
```text
@Override public void exportTransferAttachments(Cursor cursor) throws ExportException
```

### `close` (line 435)
```text
@Override public void close() throws ExportException
```

### `importHeader` (line 78)
```text
@Override public void importHeader() throws ImportException
```

### `importCurrencies` (line 98)
```text
@Override public void importCurrencies(ContentResolver contentResolver) throws ImportException
```

### `importWallets` (line 120)
```text
@Override public void importWallets(ContentResolver contentResolver) throws ImportException
```

### `importCategories` (line 140)
```text
@Override public void importCategories(ContentResolver contentResolver) throws ImportException
```

### `importEvents` (line 160)
```text
@Override public void importEvents(ContentResolver contentResolver) throws ImportException
```

### `importPlaces` (line 180)
```text
@Override public void importPlaces(ContentResolver contentResolver) throws ImportException
```

### `importPeople` (line 200)
```text
@Override public void importPeople(ContentResolver contentResolver) throws ImportException
```

### `importEventPeople` (line 220)
```text
@Override public void importEventPeople(ContentResolver contentResolver) throws ImportException
```

### `importDebts` (line 239)
```text
@Override public void importDebts(ContentResolver contentResolver) throws ImportException
```

### `importDebtPeople` (line 259)
```text
@Override public void importDebtPeople(ContentResolver contentResolver) throws ImportException
```

### `importBudgets` (line 278)
```text
@Override public void importBudgets(ContentResolver contentResolver) throws ImportException
```

### `importBudgetWallets` (line 298)
```text
@Override public void importBudgetWallets(ContentResolver contentResolver) throws ImportException
```

### `importSavings` (line 317)
```text
@Override public void importSavings(ContentResolver contentResolver) throws ImportException
```

### `importRecurrentTransactions` (line 337)
```text
@Override public void importRecurrentTransactions(ContentResolver contentResolver) throws ImportException
```

### `importRecurrentTransfers` (line 357)
```text
@Override public void importRecurrentTransfers(ContentResolver contentResolver) throws ImportException
```

### `importTransactions` (line 377)
```text
@Override public void importTransactions(ContentResolver contentResolver) throws ImportException
```

### `importTransactionPeople` (line 397)
```text
@Override public void importTransactionPeople(ContentResolver contentResolver) throws ImportException
```

### `importTransactionModels` (line 416)
```text
@Override public void importTransactionModels(ContentResolver contentResolver) throws ImportException
```

### `importTransfers` (line 435)
```text
@Override public void importTransfers(ContentResolver contentResolver) throws ImportException
```

### `importTransferPeople` (line 455)
```text
@Override public void importTransferPeople(ContentResolver contentResolver) throws ImportException
```

### `importTransferModels` (line 474)
```text
@Override public void importTransferModels(ContentResolver contentResolver) throws ImportException
```

### `importAttachments` (line 493)
```text
@Override public void importAttachments(ContentResolver contentResolver) throws ImportException
```

### `importTransactionAttachments` (line 513)
```text
@Override public void importTransactionAttachments(ContentResolver contentResolver) throws ImportException
```

### `importTransferAttachments` (line 532)
```text
@Override public void importTransferAttachments(ContentResolver contentResolver) throws ImportException
```

### `close` (line 551)
```text
@Override public void close() throws ImportException
```

## [auto] Types

### `JSONDatabaseExporter`

| Field | Type |
|-------|------|
| `exportHeader` | `method` |
| `exportCurrencies` | `method` |
| `exportWallets` | `method` |
| `exportCategories` | `method` |
| `exportEvents` | `method` |
| `exportPlaces` | `method` |
| `exportPeople` | `method` |
| `exportEventPeople` | `method` |
| `exportDebts` | `method` |
| `exportDebtPeople` | `method` |
| _(+15 more)_ | |

### `JSONDatabaseImporter`

| Field | Type |
|-------|------|
| `importHeader` | `method` |
| `importCurrencies` | `method` |
| `importWallets` | `method` |
| `importCategories` | `method` |
| `importEvents` | `method` |
| `importPlaces` | `method` |
| `importPeople` | `method` |
| `importEventPeople` | `method` |
| `importDebts` | `method` |
| `importDebtPeople` | `method` |
| _(+15 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database.json;
import com.oriondev.moneywallet.storage.database.model.*;
import org.json.JSONObject;
import java.util.HashMap;
import java.util.Map;
import com.oriondev.moneywallet.storage.database.model.Attachment;
import com.oriondev.moneywallet.storage.database.model.Budget;
import com.oriondev.moneywallet.storage.database.model.BudgetWallet;
import com.oriondev.moneywallet.storage.database.model.Category;
import com.oriondev.moneywallet.storage.database.model.Currency;
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