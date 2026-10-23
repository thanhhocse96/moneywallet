<!-- AUTO_START | hash: 67648f42 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/fragment/single`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 3

## [auto] Public Functions

### `newInstance` (line 64)
```text
public static PeriodDetailFlowFragment newInstance(Date start, Date end, boolean incomes)
```

### `onAttach` (line 90)
```text
@Override public void onAttach(Context context)
```

### `onDetach` (line 96)
```text
@Override public void onDetach()
```

### `onCreateView` (line 102)
```text
@Nullable public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState)
```

### `onViewCreated` (line 130)
```text
@Override public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState)
```

### `onCategoryClick` (line 136)
```text
@Override public void onCategoryClick(long id)
```

### `onCreateLoader` (line 145)
```text
@Override public Loader<PeriodDetailFlowData> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 150)
```text
@Override public void onLoadFinished(Loader<PeriodDetailFlowData> loader, PeriodDetailFlowData data)
```

### `onLoaderReset` (line 171)
```text
@Override public void onLoaderReset(Loader<PeriodDetailFlowData> loader)
```

### `onCurrentWalletChanged` (line 176)
```text
@Override public void onCurrentWalletChanged(long walletId)
```

### `newInstance` (line 65)
```text
public static PeriodDetailSummaryFragment newInstance(Date start, Date end)
```

### `onAttach` (line 89)
```text
@Override public void onAttach(Context context)
```

### `onDetach` (line 95)
```text
@Override public void onDetach()
```

### `onCreateView` (line 101)
```text
@Nullable public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState)
```

### `onViewCreated` (line 128)
```text
@Override public void onViewCreated(@NonNull View view, @Nullable Bundle savedInstanceState)
```

### `onPeriodClick` (line 134)
```text
@Override public void onPeriodClick(PeriodMoney periodMoney)
```

### `onCreateLoader` (line 142)
```text
@Override public Loader<PeriodDetailSummaryData> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 163)
```text
@Override public void onLoadFinished(Loader<PeriodDetailSummaryData> loader, PeriodDetailSummaryData data)
```

### `onLoaderReset` (line 180)
```text
@Override public void onLoaderReset(Loader<PeriodDetailSummaryData> loader)
```

### `onCurrentWalletChanged` (line 185)
```text
@Override public void onCurrentWalletChanged(long walletId)
```

## [auto] Types

### `AboutFragment`

### `PeriodDetailFlowFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onAttach` | `method` |
| `onDetach` | `method` |
| `onCreateView` | `method` |
| `onViewCreated` | `method` |
| `onCategoryClick` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onCurrentWalletChanged` | `method` |

### `PeriodDetailSummaryFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onAttach` | `method` |
| `onDetach` | `method` |
| `onCreateView` | `method` |
| `onViewCreated` | `method` |
| `onPeriodClick` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onCurrentWalletChanged` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.fragment.single;
import android.content.ActivityNotFoundException;
import android.content.Context;
import android.content.Intent;
import android.graphics.PorterDuff;
import android.net.Uri;
import androidx.fragment.app.FragmentManager;
import com.danielstone.materialaboutlibrary.MaterialAboutFragment;
import com.danielstone.materialaboutlibrary.holders.MaterialAboutItemViewHolder;
import com.danielstone.materialaboutlibrary.items.MaterialAboutActionItem;
// ... +52 more
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