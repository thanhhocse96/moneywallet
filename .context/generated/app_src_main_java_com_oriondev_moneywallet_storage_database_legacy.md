<!-- AUTO_START | hash: 6c45ac98 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database/legacy`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 3

## [auto] Public Functions

### `importHeader` (line 104)
```text
@Override public void importHeader() throws ImportException
```

### `importCurrencies` (line 109)
```text
@Override public void importCurrencies(ContentResolver contentResolver) throws ImportException
```

### `importWallets` (line 114)
```text
@Override public void importWallets(ContentResolver contentResolver) throws ImportException
```

### `importCategories` (line 144)
```text
@Override public void importCategories(ContentResolver contentResolver) throws ImportException
```

### `importEvents` (line 241)
```text
@Override public void importEvents(ContentResolver contentResolver) throws ImportException
```

### `importPlaces` (line 269)
```text
@Override public void importPlaces(ContentResolver contentResolver) throws ImportException
```

### `importPeople` (line 316)
```text
@Override public void importPeople(ContentResolver contentResolver) throws ImportException
```

### `importEventPeople` (line 321)
```text
@Override public void importEventPeople(ContentResolver contentResolver) throws ImportException
```

### `importDebts` (line 326)
```text
@Override public void importDebts(ContentResolver contentResolver) throws ImportException
```

### `importDebtPeople` (line 362)
```text
@Override public void importDebtPeople(ContentResolver contentResolver) throws ImportException
```

### `importBudgets` (line 367)
```text
@Override public void importBudgets(ContentResolver contentResolver) throws ImportException
```

### `importBudgetWallets` (line 448)
```text
@Override public void importBudgetWallets(ContentResolver contentResolver) throws ImportException
```

### `importSavings` (line 453)
```text
@Override public void importSavings(ContentResolver contentResolver) throws ImportException
```

### `importRecurrentTransactions` (line 489)
```text
@Override public void importRecurrentTransactions(ContentResolver contentResolver) throws ImportException
```

### `importRecurrentTransfers` (line 611)
```text
@Override public void importRecurrentTransfers(ContentResolver contentResolver) throws ImportException
```

### `importTransactions` (line 616)
```text
@Override public void importTransactions(ContentResolver contentResolver) throws ImportException
```

### `importTransactionPeople` (line 703)
```text
@Override public void importTransactionPeople(ContentResolver contentResolver) throws ImportException
```

### `importTransactionModels` (line 708)
```text
@Override public void importTransactionModels(ContentResolver contentResolver) throws ImportException
```

### `importTransfers` (line 713)
```text
@Override public void importTransfers(ContentResolver contentResolver) throws ImportException
```

### `importTransferPeople` (line 727)
```text
@Override public void importTransferPeople(ContentResolver contentResolver) throws ImportException
```

### `importTransferModels` (line 732)
```text
@Override public void importTransferModels(ContentResolver contentResolver) throws ImportException
```

### `importAttachments` (line 737)
```text
@Override public void importAttachments(ContentResolver contentResolver) throws ImportException
```

### `importTransactionAttachments` (line 742)
```text
@Override public void importTransactionAttachments(ContentResolver contentResolver) throws ImportException
```

### `importTransferAttachments` (line 747)
```text
@Override public void importTransferAttachments(ContentResolver contentResolver) throws ImportException
```

### `getAttachmentId` (line 752)
```text
public String getAttachmentId(String legacyIdentifier) throws ImportException
```

### `importAttachment` (line 756)
```text
public void importAttachment(ContentResolver contentResolver, String file, long size) throws ImportException
```

### `close` (line 836)
```text
@Override public void close() throws ImportException
```

### `getDateFormat` (line 65)
```text
public int getDateFormat()
```

### `getColorIn` (line 90)
```text
public int getColorIn()
```

### `getColorOut` (line 94)
```text
public int getColorOut()
```

### `getGroupType` (line 98)
```text
public Group getGroupType()
```

### `getFirstDayOfMonth` (line 112)
```text
public int getFirstDayOfMonth()
```

### `getFirstDayOfWeek` (line 116)
```text
public int getFirstDayOfWeek()
```

### `isReminderEnabled` (line 120)
```text
public boolean isReminderEnabled()
```

### `getReminderHour` (line 124)
```text
public int getReminderHour()
```

### `isCurrencySymbolEnabled` (line 128)
```text
public boolean isCurrencySymbolEnabled()
```

### `isGroupDigitsEnabled` (line 132)
```text
public boolean isGroupDigitsEnabled()
```

### `isRoundDecimalsEnabled` (line 137)
```text
public boolean isRoundDecimalsEnabled()
```

### `destroy` (line 142)
```text
public void destroy()
```

## [auto] Types

### `LegacyDatabaseImporter`

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
| _(+17 more)_ | |

### `LegacyUserPreferences`

| Field | Type |
|-------|------|
| `getDateFormat` | `method` |
| `getColorIn` | `method` |
| `getColorOut` | `method` |
| `getGroupType` | `method` |
| `getFirstDayOfMonth` | `method` |
| `getFirstDayOfWeek` | `method` |
| `isReminderEnabled` | `method` |
| `getReminderHour` | `method` |
| `isCurrencySymbolEnabled` | `method` |
| `isGroupDigitsEnabled` | `method` |
| _(+2 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database.legacy;
import android.content.ContentResolver;
import android.database.Cursor;
import android.database.sqlite.SQLiteDatabase;
import android.database.sqlite.SQLiteException;
import android.net.Uri;
import androidx.collection.LongSparseArray;
import android.text.TextUtils;
import com.oriondev.moneywallet.model.ColorIcon;
import com.oriondev.moneywallet.model.CurrencyUnit;
// ... +40 more
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