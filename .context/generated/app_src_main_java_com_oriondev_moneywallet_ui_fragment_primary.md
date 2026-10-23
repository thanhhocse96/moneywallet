<!-- AUTO_START | hash: 281a0ce7 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/fragment/primary`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 11

## [auto] Public Functions

### `newInstance` (line 50)
```text
public static BudgetListFragment newInstance(boolean expired)
```

### `onCreateLoader` (line 69)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onBudgetClick` (line 111)
```text
@Override public void onBudgetClick(long id)
```

### `newInstance` (line 54)
```text
public static CategoryListFragment newInstance(Contract.CategoryType type, boolean showChildren)
```

### `onCreateLoader` (line 74)
```text
@NonNull @Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onAttach` (line 107)
```text
@Override public void onAttach(Context context)
```

### `onDetach` (line 115)
```text
@Override public void onDetach()
```

### `onCategoryClick` (line 121)
```text
@Override public void onCategoryClick(long id)
```

### `onCategoryClick` (line 138)
```text
void onCategoryClick(long id)
```

### `newInstance` (line 56)
```text
public static DebtListFragment newInstance(Contract.DebtType debtType)
```

### `onCreateLoader` (line 75)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onDebtClick` (line 132)
```text
@Override public void onDebtClick(long id)
```

### `onPayClick` (line 143)
```text
@Override public void onPayClick(long id)
```

### `onReceiveClick` (line 152)
```text
@Override public void onReceiveClick(long id)
```

### `newInstance` (line 49)
```text
public static EventListFragment newInstance(boolean completed)
```

### `onCreateLoader` (line 68)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onEventClick` (line 98)
```text
@Override public void onEventClick(long id)
```

### `onCreateLoader` (line 61)
```text
@NonNull @Override public Loader<Cursor> onCreateLoader(int id, @Nullable Bundle args)
```

### `onRecurrentTransactionClick` (line 84)
```text
@Override public void onRecurrentTransactionClick(long id)
```

### `onCreateLoader` (line 61)
```text
@NonNull @Override public Loader<Cursor> onCreateLoader(int id, @Nullable Bundle args)
```

### `onRecurrentTransferClick` (line 85)
```text
@Override public void onRecurrentTransferClick(long id)
```

### `newInstance` (line 51)
```text
public static SavingListFragment newInstance(boolean completed)
```

### `onCreateLoader` (line 70)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onSavingClick` (line 105)
```text
@Override public void onSavingClick(long id)
```

### `onWithdrawEverything` (line 116)
```text
@Override public void onWithdrawEverything(long id)
```

### `onWithdraw` (line 125)
```text
@Override public void onWithdraw(long id)
```

### `onDeposit` (line 134)
```text
@Override public void onDeposit(long id)
```

### `onCreateLoader` (line 67)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onHeaderClick` (line 91)
```text
@Override public void onHeaderClick(Date startDate, Date endDate)
```

### `onTransactionClick` (line 99)
```text
@Override public void onTransactionClick(long id)
```

### `onCreateLoader` (line 63)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onModelClick` (line 92)
```text
@Override public void onModelClick(long modelId)
```

### `onModelAddClick` (line 103)
```text
@Override public void onModelAddClick(long modelId)
```

### `onModelEditClick` (line 116)
```text
@Override public void onModelEditClick(long modelId)
```

### `onCreateLoader` (line 64)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onHeaderClick` (line 91)
```text
@Override public void onHeaderClick()
```

### `onTransferClick` (line 96)
```text
@Override public void onTransferClick(long id)
```

### `onCreateLoader` (line 64)
```text
@NonNull @Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onModelClick` (line 98)
```text
@Override public void onModelClick(long modelId)
```

### `onModelAddClick` (line 109)
```text
@Override public void onModelAddClick(long modelId)
```

### `onModelEditClick` (line 122)
```text
@Override public void onModelEditClick(long modelId)
```

## [auto] Types

### `BudgetListFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateLoader` | `method` |
| `onBudgetClick` | `method` |

### `CategoryListFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateLoader` | `method` |
| `onAttach` | `method` |
| `onDetach` | `method` |
| `onCategoryClick` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onCategoryClick` | `method` |

### `DebtListFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateLoader` | `method` |
| `onDebtClick` | `method` |
| `onPayClick` | `method` |
| `onReceiveClick` | `method` |

### `EventListFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateLoader` | `method` |
| `onEventClick` | `method` |

### `RecurrentTransactionListFragment`

| Field | Type |
|-------|------|
| `onCreateLoader` | `method` |
| `onRecurrentTransactionClick` | `method` |

### `RecurrentTransferListFragment`

| Field | Type |
|-------|------|
| `onCreateLoader` | `method` |
| `onRecurrentTransferClick` | `method` |

### `SavingListFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateLoader` | `method` |
| `onSavingClick` | `method` |
| `onWithdrawEverything` | `method` |
| `onWithdraw` | `method` |
| `onDeposit` | `method` |

### `TransactionListFragment`

| Field | Type |
|-------|------|
| `onCreateLoader` | `method` |
| `onHeaderClick` | `method` |
| `onTransactionClick` | `method` |

### `TransactionModelListFragment`

| Field | Type |
|-------|------|
| `onCreateLoader` | `method` |
| `onModelClick` | `method` |
| `onModelAddClick` | `method` |
| `onModelEditClick` | `method` |

### `TransferListFragment`

| Field | Type |
|-------|------|
| `onCreateLoader` | `method` |
| `onHeaderClick` | `method` |
| `onTransferClick` | `method` |

### `TransferModelListFragment`

| Field | Type |
|-------|------|
| `onCreateLoader` | `method` |
| `onModelClick` | `method` |
| `onModelAddClick` | `method` |
| `onModelEditClick` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.fragment.primary;
import android.app.Activity;
import android.content.Intent;
import android.database.Cursor;
import android.net.Uri;
import android.os.Bundle;
import androidx.loader.content.CursorLoader;
import androidx.loader.content.Loader;
import androidx.localbroadcastmanager.content.LocalBroadcastManager;
import androidx.recyclerview.widget.LinearLayoutManager;
// ... +34 more
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