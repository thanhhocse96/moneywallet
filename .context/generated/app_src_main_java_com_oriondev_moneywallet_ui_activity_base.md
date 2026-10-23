<!-- AUTO_START | hash: e0752957 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/activity/base`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 8

## [auto] Public Functions

### `onBackPressed` (line 59)
```text
@Override public void onBackPressed()
```

### `setToolbar` (line 66)
```text
@Override public void setToolbar(Toolbar toolbar)
```

### `onMenuItemClick` (line 152)
```text
@Override public boolean onMenuItemClick(MenuItem item)
```

### `onLoadFinished` (line 70)
```text
@Override public void onLoadFinished(@NonNull Loader<Cursor> loader, Cursor cursor)
```

### `onLoaderReset` (line 80)
```text
@Override public void onLoaderReset(@NonNull Loader<Cursor> loader)
```

### `onRefresh` (line 85)
```text
@Override public void onRefresh()
```

### `onPageScrolled` (line 70)
```text
@Override public void onPageScrolled(int position, float positionOffset, int positionOffsetPixels)
```

### `onPageSelected` (line 75)
```text
@Override public void onPageSelected(int position)
```

### `onPageScrollStateChanged` (line 80)
```text
@Override public void onPageScrollStateChanged(int state)
```

### `onDestroy` (line 85)
```text
@Override public void onDestroy()
```

### `onThemeChanged` (line 97)
```text
@Override public void onThemeChanged(ITheme theme)
```

## [auto] Types

### `BaseActivity`

### `MultiPanelActivity`

| Field | Type |
|-------|------|
| `onBackPressed` | `method` |
| `setToolbar` | `method` |

### `SinglePanelActivity`

| Field | Type |
|-------|------|
| `onMenuItemClick` | `method` |

### `SinglePanelAppBarActivity`

### `SinglePanelScrollActivity`

### `SinglePanelSimpleListActivity`

| Field | Type |
|-------|------|
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onRefresh` | `method` |

### `SinglePanelViewPagerActivity`

| Field | Type |
|-------|------|
| `onPageScrolled` | `method` |
| `onPageSelected` | `method` |
| `onPageScrollStateChanged` | `method` |
| `onDestroy` | `method` |

### `ThemedActivity`

| Field | Type |
|-------|------|
| `onThemeChanged` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.activity.base;
import android.content.Intent;
import com.oriondev.moneywallet.model.LockMode;
import com.oriondev.moneywallet.storage.preference.PreferenceManager;
import com.oriondev.moneywallet.ui.activity.LockActivity;
import android.os.Bundle;
import androidx.fragment.app.FragmentManager;
import androidx.appcompat.widget.Toolbar;
import android.view.View;
import com.oriondev.moneywallet.R;
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