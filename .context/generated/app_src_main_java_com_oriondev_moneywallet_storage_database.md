<!-- AUTO_START | hash: 71afb839 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/database`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 15

## [auto] Public Functions

### `fromValue` (line 465)
```text
public static CategoryType fromValue(int value)
```

### `getValue` (line 477)
```text
public int getValue()
```

### `fromValue` (line 504)
```text
public static DebtType fromValue(int value)
```

### `getValue` (line 515)
```text
public int getValue()
```

### `fromValue` (line 532)
```text
public static BudgetType fromValue(int value)
```

### `getValue` (line 545)
```text
public int getValue()
```

### `parseObjectIds` (line 577)
```text
public static List<Long> parseObjectIds(String encodedIds)
```

### `getObjectIds` (line 596)
```text
public static <T extends Identifiable> String getObjectIds(T[] objects)
```

### `getObjectIds` (line 610)
```text
public static <T extends Identifiable> String getObjectIds(List<T> objects)
```

### `onCreate` (line 169)
```text
@Override public boolean onCreate()
```

### `query` (line 175)
```text
@Nullable @Override public Cursor query(@NonNull Uri uri, String[] projection, String selection, String[] selectionArgs, String sortOrder)
```

### `getType` (line 484)
```text
@Nullable @Override public String getType(@NonNull Uri uri)
```

### `insert` (line 582)
```text
@Nullable @Override public Uri insert(@NonNull Uri uri, ContentValues contentValues)
```

### `delete` (line 657)
```text
@Override public int delete(@NonNull Uri uri, String selection, String[] selectionArgs)
```

### `update` (line 735)
```text
@Override public int update(@NonNull Uri uri, ContentValues values, String selection, String[] selectionArgs)
```

### `notifyDatabaseIsChanged` (line 820)
```text
@SuppressLint("Recycle") public static void notifyDatabaseIsChanged(Context context)
```

### `exportHeader` (line 30)
```text
void exportHeader() throws ExportException
```

### `exportCurrencies` (line 32)
```text
void exportCurrencies(Cursor cursor) throws ExportException
```

### `exportWallets` (line 34)
```text
void exportWallets(Cursor cursor) throws ExportException
```

### `exportCategories` (line 36)
```text
void exportCategories(Cursor cursor) throws ExportException
```

### `exportEvents` (line 38)
```text
void exportEvents(Cursor cursor) throws ExportException
```

### `exportPlaces` (line 40)
```text
void exportPlaces(Cursor cursor) throws ExportException
```

### `exportPeople` (line 42)
```text
void exportPeople(Cursor cursor) throws ExportException
```

### `exportEventPeople` (line 44)
```text
void exportEventPeople(Cursor cursor) throws ExportException
```

### `exportDebts` (line 46)
```text
void exportDebts(Cursor cursor) throws ExportException
```

### `exportDebtPeople` (line 48)
```text
void exportDebtPeople(Cursor cursor) throws ExportException
```

### `exportBudgets` (line 50)
```text
void exportBudgets(Cursor cursor) throws ExportException
```

### `exportBudgetWallets` (line 52)
```text
void exportBudgetWallets(Cursor cursor) throws ExportException
```

### `exportSavings` (line 54)
```text
void exportSavings(Cursor cursor) throws ExportException
```

### `exportRecurrentTransactions` (line 56)
```text
void exportRecurrentTransactions(Cursor cursor) throws ExportException
```

### `exportRecurrentTransfers` (line 58)
```text
void exportRecurrentTransfers(Cursor cursor) throws ExportException
```

### `exportTransactions` (line 60)
```text
void exportTransactions(Cursor cursor) throws ExportException
```

### `exportTransactionPeople` (line 62)
```text
void exportTransactionPeople(Cursor cursor) throws ExportException
```

### `exportTransactionModels` (line 64)
```text
void exportTransactionModels(Cursor cursor) throws ExportException
```

### `exportTransfers` (line 66)
```text
void exportTransfers(Cursor cursor) throws ExportException
```

### `exportTransferPeople` (line 68)
```text
void exportTransferPeople(Cursor cursor) throws ExportException
```

### `exportTransferModels` (line 70)
```text
void exportTransferModels(Cursor cursor) throws ExportException
```

### `exportAttachments` (line 72)
```text
void exportAttachments(Cursor cursor) throws ExportException
```

### `exportTransactionAttachments` (line 74)
```text
void exportTransactionAttachments(Cursor cursor) throws ExportException
```

### `exportTransferAttachments` (line 76)
```text
void exportTransferAttachments(Cursor cursor) throws ExportException
```

### `close` (line 78)
```text
void close() throws ExportException
```

### `importHeader` (line 30)
```text
void importHeader() throws ImportException
```

### `importCurrencies` (line 32)
```text
void importCurrencies(ContentResolver contentResolver) throws ImportException
```

### `importWallets` (line 34)
```text
void importWallets(ContentResolver contentResolver) throws ImportException
```

### `importCategories` (line 36)
```text
void importCategories(ContentResolver contentResolver) throws ImportException
```

### `importEvents` (line 38)
```text
void importEvents(ContentResolver contentResolver) throws ImportException
```

### `importPlaces` (line 40)
```text
void importPlaces(ContentResolver contentResolver) throws ImportException
```

### `importPeople` (line 42)
```text
void importPeople(ContentResolver contentResolver) throws ImportException
```

### `importEventPeople` (line 44)
```text
void importEventPeople(ContentResolver contentResolver) throws ImportException
```

### `importDebts` (line 46)
```text
void importDebts(ContentResolver contentResolver) throws ImportException
```

### `importDebtPeople` (line 48)
```text
void importDebtPeople(ContentResolver contentResolver) throws ImportException
```

### `importBudgets` (line 50)
```text
void importBudgets(ContentResolver contentResolver) throws ImportException
```

### `importBudgetWallets` (line 52)
```text
void importBudgetWallets(ContentResolver contentResolver) throws ImportException
```

### `importSavings` (line 54)
```text
void importSavings(ContentResolver contentResolver) throws ImportException
```

### `importRecurrentTransactions` (line 56)
```text
void importRecurrentTransactions(ContentResolver contentResolver) throws ImportException
```

### `importRecurrentTransfers` (line 58)
```text
void importRecurrentTransfers(ContentResolver contentResolver) throws ImportException
```

### `importTransactions` (line 60)
```text
void importTransactions(ContentResolver contentResolver) throws ImportException
```

### `importTransactionPeople` (line 62)
```text
void importTransactionPeople(ContentResolver contentResolver) throws ImportException
```

### `importTransactionModels` (line 64)
```text
void importTransactionModels(ContentResolver contentResolver) throws ImportException
```

### `importTransfers` (line 66)
```text
void importTransfers(ContentResolver contentResolver) throws ImportException
```

### `importTransferPeople` (line 68)
```text
void importTransferPeople(ContentResolver contentResolver) throws ImportException
```

### `importTransferModels` (line 70)
```text
void importTransferModels(ContentResolver contentResolver) throws ImportException
```

### `importAttachments` (line 72)
```text
void importAttachments(ContentResolver contentResolver) throws ImportException
```

### `importTransactionAttachments` (line 74)
```text
void importTransactionAttachments(ContentResolver contentResolver) throws ImportException
```

### `importTransferAttachments` (line 76)
```text
void importTransferAttachments(ContentResolver contentResolver) throws ImportException
```

### `close` (line 78)
```text
void close() throws ImportException
```

### `importDatabase` (line 54)
```text
public void importDatabase() throws ImportException
```

### `importAttachments` (line 83)
```text
public void importAttachments() throws ImportException
```

### `importPreferences` (line 122)
```text
public void importPreferences() throws ImportException
```

### `deactivate` (line 59)
```text
@Override public void deactivate()
```

### `requery` (line 72)
```text
@Override public boolean requery()
```

### `isClosed` (line 88)
```text
@Override public boolean isClosed()
```

### `close` (line 93)
```text
@Override public void close()
```

### `registerContentObserver` (line 101)
```text
@SuppressWarnings("deprecation") @Override public void registerContentObserver(ContentObserver observer)
```

### `unregisterContentObserver` (line 116)
```text
@Override public void unregisterContentObserver(ContentObserver observer)
```

### `setNotificationUri` (line 145)
```text
@Override public void setNotificationUri(ContentResolver contentResolver, Uri notifyUri)
```

### `getNotificationUri` (line 158)
```text
@Override public Uri getNotificationUri()
```

### `getCurrency` (line 55)
```text
public static Currency getCurrency(Cursor cursor)
```

### `getWallet` (line 68)
```text
public static Wallet getWallet(Cursor cursor)
```

### `getCategory` (line 85)
```text
public static Category getCategory(Cursor cursor)
```

### `getEvent` (line 101)
```text
public static Event getEvent(Cursor cursor)
```

### `getPlace` (line 116)
```text
public static Place getPlace(Cursor cursor)
```

### `getPerson` (line 136)
```text
public static Person getPerson(Cursor cursor)
```

### `getEventPerson` (line 149)
```text
public static EventPerson getEventPerson(Cursor cursor)
```

### `getDebt` (line 159)
```text
public static Debt getDebt(Cursor cursor)
```

### `getDebtPerson` (line 179)
```text
public static DebtPerson getDebtPerson(Cursor cursor)
```

### `getBudget` (line 189)
```text
public static Budget getBudget(Cursor cursor)
```

### `getBudgetWallet` (line 205)
```text
public static BudgetWallet getBudgetWallet(Cursor cursor)
```

### `getSaving` (line 215)
```text
public static Saving getSaving(Cursor cursor)
```

### `getRecurrentTransaction` (line 233)
```text
public static RecurrentTransaction getRecurrentTransaction(Cursor cursor)
```

### `getRecurrentTransfer` (line 257)
```text
public static RecurrentTransfer getRecurrentTransfer(Cursor cursor)
```

### `getTransaction` (line 282)
```text
public static Transaction getTransaction(Cursor cursor)
```

### `getTransactionPerson` (line 307)
```text
public static TransactionPerson getTransactionPerson(Cursor cursor)
```

### `getTransactionModel` (line 317)
```text
public static TransactionModel getTransactionModel(Cursor cursor)
```

### `getTransfer` (line 337)
```text
public static Transfer getTransfer(Cursor cursor)
```

### `getTransferPerson` (line 358)
```text
public static TransferPerson getTransferPerson(Cursor cursor)
```

### `getTransferModel` (line 368)
```text
public static TransferModel getTransferModel(Cursor cursor)
```

### `getAttachment` (line 389)
```text
public static Attachment getAttachment(Cursor cursor)
```

### `getTransactionAttachment` (line 403)
```text
public static TransactionAttachment getTransactionAttachment(Cursor cursor)
```

### `getTransferAttachment` (line 413)
```text
public static TransferAttachment getTransferAttachment(Cursor cursor)
```

### `getAllCurrencies` (line 423)
```text
public static Cursor getAllCurrencies(ContentResolver contentResolver)
```

### `getAllWallets` (line 429)
```text
public static Cursor getAllWallets(ContentResolver contentResolver)
```

### `getAllCategories` (line 435)
```text
public static Cursor getAllCategories(ContentResolver contentResolver)
```

### `getAllEvents` (line 442)
```text
public static Cursor getAllEvents(ContentResolver contentResolver)
```

### `getAllPlaces` (line 448)
```text
public static Cursor getAllPlaces(ContentResolver contentResolver)
```

### `getAllPeople` (line 455)
```text
public static Cursor getAllPeople(ContentResolver contentResolver)
```

### `getAllEventPeople` (line 462)
```text
public static Cursor getAllEventPeople(ContentResolver contentResolver)
```

### `getAllDebt` (line 469)
```text
public static Cursor getAllDebt(ContentResolver contentResolver)
```

### `getAllDebtPeople` (line 476)
```text
public static Cursor getAllDebtPeople(ContentResolver contentResolver)
```

### `getAllBudget` (line 483)
```text
public static Cursor getAllBudget(ContentResolver contentResolver)
```

### `getAllBudgetWallets` (line 490)
```text
public static Cursor getAllBudgetWallets(ContentResolver contentResolver)
```

### `getAllSavings` (line 497)
```text
public static Cursor getAllSavings(ContentResolver contentResolver)
```

### `getAllRecurrentTransactions` (line 503)
```text
public static Cursor getAllRecurrentTransactions(ContentResolver contentResolver)
```

### `getAllRecurrentTransfers` (line 509)
```text
public static Cursor getAllRecurrentTransfers(ContentResolver contentResolver)
```

### `getAllTransactions` (line 515)
```text
public static Cursor getAllTransactions(ContentResolver contentResolver)
```

### `getAllTransactionPeople` (line 522)
```text
public static Cursor getAllTransactionPeople(ContentResolver contentResolver)
```

### `getAllTransactionModels` (line 529)
```text
public static Cursor getAllTransactionModels(ContentResolver contentResolver)
```

### `getAllTransfers` (line 536)
```text
public static Cursor getAllTransfers(ContentResolver contentResolver)
```

### `getAllTransferPeople` (line 543)
```text
public static Cursor getAllTransferPeople(ContentResolver contentResolver)
```

### `getAllTransferModels` (line 550)
```text
public static Cursor getAllTransferModels(ContentResolver contentResolver)
```

### `getAllAttachments` (line 557)
```text
public static Cursor getAllAttachments(ContentResolver contentResolver)
```

### `getAllTransactionAttachments` (line 564)
```text
public static Cursor getAllTransactionAttachments(ContentResolver contentResolver)
```

### `getAllTransferAttachments` (line 571)
```text
public static Cursor getAllTransferAttachments(ContentResolver contentResolver)
```

### `insert` (line 36)
```text
public static long insert(ContentResolver contentResolver, Currency currency)
```

### `insert` (line 51)
```text
public static long insert(ContentResolver contentResolver, Wallet wallet)
```

### `insert` (line 70)
```text
public static long insert(ContentResolver contentResolver, Category category)
```

### `insert` (line 87)
```text
public static long insert(ContentResolver contentResolver, Event event)
```

### `insert` (line 103)
```text
public static long insert(ContentResolver contentResolver, Place place)
```

### `insert` (line 119)
```text
public static long insert(ContentResolver contentResolver, Person person)
```

### `insert` (line 133)
```text
public static long insert(ContentResolver contentResolver, EventPerson eventPerson)
```

### `insert` (line 145)
```text
public static long insert(ContentResolver contentResolver, Debt debt)
```

### `insert` (line 166)
```text
public static long insert(ContentResolver contentResolver, DebtPerson debtPerson)
```

### `insert` (line 178)
```text
public static long insert(ContentResolver contentResolver, Budget budget)
```

### `insert` (line 195)
```text
public static long insert(ContentResolver contentResolver, BudgetWallet budgetWallet)
```

### `insert` (line 207)
```text
public static long insert(ContentResolver contentResolver, Saving saving)
```

### `insert` (line 226)
```text
public static long insert(ContentResolver contentResolver, RecurrentTransaction recurrentTransaction)
```

### `insert` (line 251)
```text
public static long insert(ContentResolver contentResolver, RecurrentTransfer recurrentTransfer)
```

### `insert` (line 277)
```text
public static long insert(ContentResolver contentResolver, Transaction transaction)
```

### `insert` (line 303)
```text
public static long insert(ContentResolver contentResolver, TransactionPerson transactionPeople)
```

### `insert` (line 315)
```text
public static long insert(ContentResolver contentResolver, TransactionModel transactionModel)
```

### `insert` (line 336)
```text
public static long insert(ContentResolver contentResolver, Transfer transfers)
```

### `insert` (line 358)
```text
public static long insert(ContentResolver contentResolver, TransferPerson transferPerson)
```

### `insert` (line 370)
```text
public static long insert(ContentResolver contentResolver, TransferModel transferModel)
```

### `insert` (line 392)
```text
public static long insert(ContentResolver contentResolver, Attachment attachment)
```

### `insert` (line 407)
```text
public static long insert(ContentResolver contentResolver, TransactionAttachment transactionAttachment)
```

### `insert` (line 419)
```text
public static long insert(ContentResolver contentResolver, TransferAttachment transferAttachment)
```

### `getErrorCode` (line 40)
```text
public int getErrorCode()
```

### `onCreate` (line 126)
```text
@Override public boolean onCreate()
```

### `query` (line 186)
```text
@Nullable @Override public Cursor query(@NonNull Uri uri, @Nullable String[] projection, @Nullable String selection, @Nullable String[] selectionArgs, @Nullable String sortOrder)
```

### `getType` (line 196)
```text
@Nullable @Override public String getType(@NonNull Uri uri)
```

### `insert` (line 202)
```text
@Nullable @Override public Uri insert(@NonNull Uri uri, @Nullable ContentValues values)
```

### `delete` (line 213)
```text
@Override public int delete(@NonNull Uri uri, @Nullable String selection, @Nullable String[] selectionArgs)
```

### `update` (line 222)
```text
@Override public int update(@NonNull Uri uri, @Nullable ContentValues values, @Nullable String selection, @Nullable String[] selectionArgs)
```

### `notifyDatabaseIsChanged` (line 231)
```text
@SuppressLint("Recycle") public static void notifyDatabaseIsChanged(Context context)
```

## [auto] Types

### `Contract`

| Field | Type |
|-------|------|
| `arseObjectIds` | `method` |
| `getObjectIds` | `method` |
| `getObjectIds` | `method` |

### `Currency`

### `Wallet`

### `Transaction`

### `Transfer`

### `Category`

### `Debt`

### `Budget`

### `Saving`

### `Event`

### `RecurrentTransaction`

### `RecurrentTransfer`

### `TransactionModel`

### `TransferModel`

### `Place`

### `Person`

### `Attachment`

### `CategoryType`

### `CategoryTag`

### `DebtType`

### `BudgetType`

### `Direction`

### `TransactionType`

### `ErrorCode`

### `DataContentProvider`

| Field | Type |
|-------|------|
| `onCreate` | `method` |
| `query` | `method` |
| `getType` | `method` |
| `insert` | `method` |
| `delete` | `method` |
| `date` | `method` |
| `notifyDatabaseIsChanged` | `method` |

### `DatabaseExporter`

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

### `DatabaseImporter`

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

### `ExportException`

### `ImportException`

### `LegacyEditionImporter`

| Field | Type |
|-------|------|
| `importDatabase` | `method` |
| `importAttachments` | `method` |
| `importPreferences` | `method` |

### `MultiUriCursorWrapper`

| Field | Type |
|-------|------|
| `deactivate` | `method` |
| `requery` | `method` |
| `isClosed` | `method` |
| `close` | `method` |
| `registerContentObserver` | `method` |
| `nregisterContentObserver` | `method` |
| `setNotificationUri` | `method` |
| `getNotificationUri` | `method` |

### `SQLDatabaseExporter`

| Field | Type |
|-------|------|
| `getCurrency` | `method` |
| `getWallet` | `method` |
| `getCategory` | `method` |
| `getEvent` | `method` |
| `getPlace` | `method` |
| `getPerson` | `method` |
| `getEventPerson` | `method` |
| `getDebt` | `method` |
| `getDebtPerson` | `method` |
| `getBudget` | `method` |
| _(+36 more)_ | |

### `SQLDatabaseImporter`

| Field | Type |
|-------|------|
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| `insert` | `method` |
| _(+13 more)_ | |

### `SQLiteDataException`

| Field | Type |
|-------|------|
| `getErrorCode` | `method` |

### `SyncContentProvider`

| Field | Type |
|-------|------|
| `onCreate` | `method` |
| `query` | `method` |
| `getType` | `method` |
| `insert` | `method` |
| `delete` | `method` |
| `date` | `method` |
| `notifyDatabaseIsChanged` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database;
import android.text.TextUtils;
import com.oriondev.moneywallet.model.Identifiable;
import java.util.ArrayList;
import java.util.List;
import java.util.Locale;
import android.annotation.SuppressLint;
import android.content.ContentProvider;
import android.content.ContentProviderClient;
import android.content.ContentResolver;
// ... +73 more
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