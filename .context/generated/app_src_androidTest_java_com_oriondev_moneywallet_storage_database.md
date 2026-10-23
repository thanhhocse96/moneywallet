<!-- AUTO_START | hash: 6787fe41 | built: 2026-10-20T15:41 -->
# Context: `app/src/androidTest/java/com/oriondev/moneywallet/storage/database`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `setUp` (line 58)
```text
@Before public void setUp()
```

### `tearDown` (line 74)
```text
@After public void tearDown()
```

### `insertWallet` (line 853)
```text
@Test public void insertWallet() throws Exception
```

### `updateWallet` (line 867)
```text
@Test public void updateWallet() throws Exception
```

### `deleteWallet` (line 886)
```text
@Test public void deleteWallet() throws Exception
```

### `testEnsureDatabaseCleanAfterWalletDelete` (line 902)
```text
@Test public void testEnsureDatabaseCleanAfterWalletDelete()
```

### `deleteWalletInTransfer` (line 930)
```text
@Test(expected = SQLiteDataException.class) public void deleteWalletInTransfer() throws Exception
```

### `insertTransaction` (line 939)
```text
@Test public void insertTransaction() throws Exception
```

### `updateTransaction` (line 955)
```text
@Test public void updateTransaction() throws Exception
```

### `deleteTransaction` (line 978)
```text
@Test public void deleteTransaction() throws Exception
```

### `insertTransfer` (line 1000)
```text
@Test public void insertTransfer() throws Exception
```

### `updateTransfer` (line 1018)
```text
@Test public void updateTransfer() throws Exception
```

### `deleteTransfer` (line 1051)
```text
@Test public void deleteTransfer() throws Exception
```

### `insertCategory` (line 1076)
```text
@Test public void insertCategory() throws Exception
```

### `testInsertNestedCategories` (line 1090)
```text
@Test(expected = SQLiteDataException.class) public void testInsertNestedCategories()
```

### `testInsertInconsistentCategoryTree` (line 1097)
```text
@Test(expected = SQLiteDataException.class) public void testInsertInconsistentCategoryTree()
```

### `updateCategory` (line 1103)
```text
@Test public void updateCategory() throws Exception
```

### `testUpdateNestedCategories1` (line 1121)
```text
@Test(expected = SQLiteDataException.class) public void testUpdateNestedCategories1()
```

### `testUpdateNestedCategories2` (line 1130)
```text
@Test(expected = SQLiteDataException.class) public void testUpdateNestedCategories2()
```

### `testUpdateInconsistentChildrenCategory` (line 1139)
```text
@Test(expected = SQLiteDataException.class) public void testUpdateInconsistentChildrenCategory()
```

### `testUpdateInconsistentParentCategory` (line 1148)
```text
@Test(expected = SQLiteDataException.class) public void testUpdateInconsistentParentCategory()
```

### `deleteCategory` (line 1157)
```text
@Test public void deleteCategory() throws Exception
```

### `testDeleteCategoryWithChildren` (line 1172)
```text
@Test(expected = SQLiteDataException.class) public void testDeleteCategoryWithChildren()
```

### `testDeleteSystemCategory` (line 1180)
```text
@Test(expected = SQLiteDataException.class) public void testDeleteSystemCategory()
```

### `testDeleteCategoryUsedInTransaction` (line 1187)
```text
@Test(expected = SQLiteDataException.class) public void testDeleteCategoryUsedInTransaction()
```

### `testDeleteCategoryUsedInTransactionModel` (line 1196)
```text
@Test(expected = SQLiteDataException.class) public void testDeleteCategoryUsedInTransactionModel()
```

### `testDeleteCategoryUsedInBudget` (line 1205)
```text
@Test(expected = SQLiteDataException.class) public void testDeleteCategoryUsedInBudget()
```

### `insertDebt` (line 1214)
```text
@Test public void insertDebt() throws Exception
```

### `updateDebt` (line 1231)
```text
@Test public void updateDebt() throws Exception
```

### `deleteDebt` (line 1255)
```text
@Test public void deleteDebt() throws Exception
```

### `insertBudget` (line 1278)
```text
@Test public void insertBudget() throws Exception
```

### `insertBudgetWithNoWallets` (line 1304)
```text
@Test(expected = SQLiteDataException.class) public void insertBudgetWithNoWallets() throws Exception
```

### `insertBudgetWithNotConsistentWallets` (line 1314)
```text
@Test(expected = SQLiteDataException.class) public void insertBudgetWithNotConsistentWallets() throws Exception
```

### `insertBudgetWithInvalidWallet` (line 1332)
```text
@Test(expected = SQLiteDataException.class) public void insertBudgetWithInvalidWallet() throws Exception
```

### `updateBudget` (line 1345)
```text
@Test public void updateBudget() throws Exception
```

### `updateBudgetWithNoWallets` (line 1381)
```text
@Test(expected = SQLiteDataException.class) public void updateBudgetWithNoWallets() throws Exception
```

### `updateBudgetWithNotConsistentWallets` (line 1398)
```text
@Test(expected = SQLiteDataException.class) public void updateBudgetWithNotConsistentWallets()
```

### `updateBudgetWithInvalidWallet` (line 1416)
```text
@Test(expected = SQLiteDataException.class) public void updateBudgetWithInvalidWallet() throws Exception
```

### `deleteBudget` (line 1434)
```text
@Test public void deleteBudget() throws Exception
```

### `considerExternalTransactionsInIncomeBudget` (line 1475)
```text
@Test public void considerExternalTransactionsInIncomeBudget() throws Exception
```

### `considerExternalTransactionsInExpenseBudget` (line 1501)
```text
@Test public void considerExternalTransactionsInExpenseBudget() throws Exception
```

### `ignoreInternalTransactionsInBudget` (line 1527)
```text
@Test public void ignoreInternalTransactionsInBudget() throws Exception
```

### `considerTransactionsWithinBudgetDurationOnly` (line 1555)
```text
@Test public void considerTransactionsWithinBudgetDurationOnly() throws Exception
```

### `getBudgetTransactions` (line 1588)
```text
@Test public void getBudgetTransactions() throws Exception
```

### `insertSaving` (line 1632)
```text
@Test public void insertSaving() throws Exception
```

### `updateSaving` (line 1642)
```text
@Test public void updateSaving() throws Exception
```

### `deleteSaving` (line 1656)
```text
@Test public void deleteSaving() throws Exception
```

### `insertEvent` (line 1680)
```text
@Test public void insertEvent() throws Exception
```

### `updateEvent` (line 1694)
```text
@Test public void updateEvent() throws Exception
```

### `deleteEvent` (line 1715)
```text
@Test public void deleteEvent() throws Exception
```

### `insertTransactionModel` (line 1737)
```text
@Test public void insertTransactionModel() throws Exception
```

### `updateTransactionModel` (line 1747)
```text
@Test public void updateTransactionModel() throws Exception
```

### `deleteTransactionModel` (line 1760)
```text
@Test public void deleteTransactionModel() throws Exception
```

### `insertTransferModel` (line 1775)
```text
@Test public void insertTransferModel() throws Exception
```

### `updateTransferModel` (line 1785)
```text
@Test public void updateTransferModel() throws Exception
```

### `deleteTransferModel` (line 1798)
```text
@Test public void deleteTransferModel() throws Exception
```

### `insertPlace` (line 1813)
```text
@Test public void insertPlace() throws Exception
```

### `updatePlace` (line 1821)
```text
@Test public void updatePlace() throws Exception
```

### `deletePlace` (line 1832)
```text
@Test public void deletePlace() throws Exception
```

### `insertPerson` (line 1856)
```text
@Test public void insertPerson() throws Exception
```

### `updatePerson` (line 1864)
```text
@Test public void updatePerson() throws Exception
```

### `deletePerson` (line 1875)
```text
@Test public void deletePerson() throws Exception
```

### `insertAttachment` (line 1897)
```text
@Test public void insertAttachment() throws Exception
```

### `updateAttachment` (line 1905)
```text
@Test public void updateAttachment() throws Exception
```

### `deleteAttachment` (line 1916)
```text
@Test public void deleteAttachment() throws Exception
```

## [auto] Types

### `SQLDatabaseTest`

| Field | Type |
|-------|------|
| `setUp` | `method` |
| `tearDown` | `method` |
| `insertWallet` | `method` |
| `dateWallet` | `method` |
| `deleteWallet` | `method` |
| `testEnsureDatabaseCleanAfterWalletDelete` | `method` |
| `deleteWalletInTransfer` | `method` |
| `insertTransaction` | `method` |
| `dateTransaction` | `method` |
| `deleteTransaction` | `method` |
| _(+55 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.database;
import android.app.Instrumentation;
import android.content.ContentValues;
import android.content.Context;
import android.database.Cursor;
import android.database.sqlite.SQLiteException;
import android.test.RenamingDelegatingContext;
import android.test.suitebuilder.annotation.LargeTest;
import android.text.TextUtils;
import androidx.test.platform.app.InstrumentationRegistry;
// ... +12 more
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