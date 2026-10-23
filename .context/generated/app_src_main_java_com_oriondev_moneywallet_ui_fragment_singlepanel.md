<!-- AUTO_START | hash: 1df6b088 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/fragment/singlepanel`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `onAttach` (line 68)
```text
@Override public void onAttach(Context context)
```

### `onDetach` (line 74)
```text
@Override public void onDetach()
```

### `onMenuItemClick` (line 112)
```text
@Override public boolean onMenuItemClick(MenuItem item)
```

### `onOverviewSettingChanged` (line 120)
```text
@Override public void onOverviewSettingChanged(String tag, OverviewSetting overviewSetting)
```

### `onCreateLoader` (line 125)
```text
@NonNull @Override public Loader<OverviewData> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 132)
```text
@Override public void onLoadFinished(@NonNull Loader<OverviewData> loader, OverviewData data)
```

### `onLoaderReset` (line 138)
```text
@Override public void onLoaderReset(@NonNull Loader<OverviewData> loader)
```

### `onPeriodClick` (line 143)
```text
@Override public void onPeriodClick(PeriodMoney periodMoney)
```

### `onCurrentWalletChanged` (line 151)
```text
@Override public void onCurrentWalletChanged(long walletId)
```

## [auto] Types

### `OverviewSinglePanelFragment`

| Field | Type |
|-------|------|
| `onAttach` | `method` |
| `onDetach` | `method` |
| `onMenuItemClick` | `method` |
| `onOverviewSettingChanged` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onPeriodClick` | `method` |
| `onCurrentWalletChanged` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.fragment.singlepanel;
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import android.os.Bundle;
import androidx.annotation.MenuRes;
import androidx.annotation.NonNull;
import androidx.fragment.app.FragmentManager;
import androidx.loader.app.LoaderManager;
import androidx.loader.content.Loader;
// ... +19 more
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