<!-- AUTO_START | hash: c90a88e6 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/view/chart`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 3

## [auto] Public Functions

### `setHoleEnabled` (line 139)
```text
public void setHoleEnabled(boolean enabled)
```

### `setLineColor` (line 147)
```text
public void setLineColor(int color)
```

### `setHoleColor` (line 151)
```text
public void setHoleColor(int color)
```

### `setShadowColor` (line 155)
```text
public void setShadowColor(int color)
```

### `setChartData` (line 159)
```text
public void setChartData(PieData pieData)
```

### `onDraw` (line 289)
```text
@Override public void onDraw(Canvas c)
```

### `get` (line 40)
```text
public PieSlice get(int index)
```

### `add` (line 44)
```text
public boolean add(PieSlice slice)
```

### `remove` (line 48)
```text
public PieSlice remove(int index)
```

### `getAllSlices` (line 52)
```text
public List<PieSlice> getAllSlices()
```

### `size` (line 56)
```text
public int size()
```

### `setIconAngle` (line 49)
```text
public void setIconAngle(float angle)
```

### `increaseIconAngle` (line 53)
```text
public void increaseIconAngle(float degrees)
```

### `decreaseIconAngle` (line 57)
```text
public void decreaseIconAngle(float degrees)
```

### `setValue` (line 61)
```text
public void setValue(long value)
```

### `getValue` (line 65)
```text
public long getValue()
```

### `getName` (line 69)
```text
public String getName()
```

### `getIcon` (line 73)
```text
public Drawable getIcon()
```

### `getIconAngle` (line 77)
```text
public float getIconAngle()
```

### `isExtra` (line 81)
```text
public boolean isExtra()
```

### `getStartAngle` (line 85)
```text
public float getStartAngle()
```

### `setStartAngle` (line 89)
```text
public void setStartAngle(float startAngle)
```

### `getSweepAngle` (line 93)
```text
public float getSweepAngle()
```

### `setSweepAngle` (line 97)
```text
public void setSweepAngle(float sweepAngle)
```

## [auto] Types

### `PieChart`

| Field | Type |
|-------|------|
| `setHoleEnabled` | `method` |
| `setLineColor` | `method` |
| `setHoleColor` | `method` |
| `setShadowColor` | `method` |
| `setChartData` | `method` |
| `onDraw` | `method` |

### `PieData`

| Field | Type |
|-------|------|
| `get` | `method` |
| `add` | `method` |
| `remove` | `method` |
| `getAllSlices` | `method` |
| `size` | `method` |

### `PieSlice`

| Field | Type |
|-------|------|
| `setIconAngle` | `method` |
| `increaseIconAngle` | `method` |
| `decreaseIconAngle` | `method` |
| `setValue` | `method` |
| `getValue` | `method` |
| `getName` | `method` |
| `getIcon` | `method` |
| `getIconAngle` | `method` |
| `isExtra` | `method` |
| `getStartAngle` | `method` |
| _(+3 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.view.chart;
import android.content.Context;
import android.content.res.TypedArray;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.graphics.RectF;
import android.graphics.drawable.Drawable;
import android.os.Build;
// ... +7 more
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