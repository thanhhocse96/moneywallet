<!-- AUTO_START | hash: 862ca66c | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/view`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 9

## [auto] Public Functions

### `getRecyclerView` (line 65)
```text
public RecyclerView getRecyclerView()
```

### `getProgressWheel` (line 69)
```text
public ProgressWheel getProgressWheel()
```

### `getTextView` (line 73)
```text
public TextView getTextView()
```

### `setLayoutManager` (line 77)
```text
public void setLayoutManager(RecyclerView.LayoutManager layoutManager)
```

### `setAdapter` (line 81)
```text
public void setAdapter(RecyclerView.Adapter adapter)
```

### `setEmptyText` (line 85)
```text
public void setEmptyText(@StringRes int resId)
```

### `setErrorText` (line 89)
```text
public void setErrorText(@StringRes int resId)
```

### `setState` (line 93)
```text
public void setState(State state)
```

### `setController` (line 71)
```text
public void setController(Controller controller)
```

### `setAllowRemove` (line 75)
```text
public void setAllowRemove(boolean allowRemove)
```

### `setAttachments` (line 79)
```text
public void setAttachments(List<Attachment> attachments)
```

### `onAttachmentClick` (line 146)
```text
void onAttachmentClick(Attachment attachment)
```

### `onAttachmentDelete` (line 148)
```text
void onAttachmentDelete(Attachment attachment)
```

### `setLast` (line 65)
```text
public void setLast(boolean last)
```

### `setLineColor` (line 69)
```text
public void setLineColor(int color)
```

### `onDraw` (line 74)
```text
@Override public void onDraw(Canvas c)
```

### `setColor` (line 56)
```text
public void setColor(int color)
```

### `setRadius` (line 61)
```text
public void setRadius(float radius)
```

### `setReachedBarColor` (line 74)
```text
public void setReachedBarColor(int color)
```

### `setUnreachedBarColor` (line 79)
```text
public void setUnreachedBarColor(int color)
```

### `setMaxValue` (line 84)
```text
public void setMaxValue(long maxValue)
```

### `setProgressValue` (line 89)
```text
public void setProgressValue(long progressValue)
```

### `getRecurrenceRule` (line 94)
```text
public RecurrenceRule getRecurrenceRule()
```

## [auto] Types

### `AdvancedRecyclerView`

| Field | Type |
|-------|------|
| `getRecyclerView` | `method` |
| `getProgressWheel` | `method` |
| `getTextView` | `method` |
| `setLayoutManager` | `method` |
| `setAdapter` | `method` |
| `setEmptyText` | `method` |
| `setErrorText` | `method` |
| `setState` | `method` |

### `State`

### `AttachmentView`

| Field | Type |
|-------|------|
| `setController` | `method` |
| `setAllowRemove` | `method` |
| `setAttachments` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onAttachmentClick` | `method` |
| `onAttachmentDelete` | `method` |

### `CardButton`

### `CategoryChildIndicator`

| Field | Type |
|-------|------|
| `setLast` | `method` |
| `setLineColor` | `method` |
| `onDraw` | `method` |

### `CircleView`

| Field | Type |
|-------|------|
| `setColor` | `method` |
| `setRadius` | `method` |

### `ForegroundCardView`

### `MaterialProgressBar`

| Field | Type |
|-------|------|
| `setReachedBarColor` | `method` |
| `setUnreachedBarColor` | `method` |
| `setMaxValue` | `method` |
| `setProgressValue` | `method` |

### `RecurrenceView`

| Field | Type |
|-------|------|
| `getRecurrenceRule` | `method` |

### `SquaredImageView`

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.view;
import android.content.Context;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.annotation.StringRes;
import androidx.swiperefreshlayout.widget.SwipeRefreshLayout;
import androidx.recyclerview.widget.RecyclerView;
import android.util.AttributeSet;
import android.view.View;
import android.widget.TextView;
// ... +22 more
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