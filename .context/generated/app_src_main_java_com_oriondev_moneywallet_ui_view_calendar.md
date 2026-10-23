<!-- AUTO_START | hash: e5156161 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/view/calendar`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 4

## [auto] Public Functions

### `setColor` (line 80)
```text
public void setColor(@ColorInt int color)
```

### `setColorRes` (line 85)
```text
public void setColorRes(@ColorRes int colorRes)
```

### `setCircleSize` (line 89)
```text
public void setCircleSize(int size)
```

### `setCircleSizeDp` (line 94)
```text
public void setCircleSizeDp(int sizeInDp)
```

### `setSelectedMonth` (line 83)
```text
public void setSelectedMonth(int year, int month)
```

### `setSelectedMonth` (line 87)
```text
public void setSelectedMonth(int year, int month, boolean callListener)
```

### `setSelectedMonth` (line 91)
```text
public void setSelectedMonth(int year, int month, boolean callListener, boolean centerOnPosition)
```

### `getSelectedYear` (line 95)
```text
public int getSelectedYear()
```

### `getSelectedMonth` (line 99)
```text
public int getSelectedMonth()
```

### `centerOnPosition` (line 139)
```text
public void centerOnPosition(int position)
```

### `centerOnDate` (line 152)
```text
public void centerOnDate(int year, int month)
```

### `centerOnSelection` (line 156)
```text
public void centerOnSelection()
```

### `getSelectedPosition` (line 181)
```text
public int getSelectedPosition()
```

### `setOnMonthSelectedListener` (line 197)
```text
public void setOnMonthSelectedListener(OnMonthSelectedListener onMonthSelectedListener)
```

### `getOnMonthSelectedListener` (line 201)
```text
public OnMonthSelectedListener getOnMonthSelectedListener()
```

### `getMonthCount` (line 205)
```text
public int getMonthCount()
```

### `setDefaultColor` (line 212)
```text
public void setDefaultColor(int defaultColor)
```

### `setColorSelected` (line 219)
```text
public void setColorSelected(int colorSelected)
```

### `setColorBeforeSelection` (line 226)
```text
public void setColorBeforeSelection(int colorBeforeSelection)
```

### `getDefaultColor` (line 230)
```text
public int getDefaultColor()
```

### `getColorBeforeSelection` (line 234)
```text
public int getColorBeforeSelection()
```

### `getColorSelected` (line 238)
```text
public int getColorSelected()
```

### `setYearDigitCount` (line 242)
```text
public void setYearDigitCount(int yearDigitCount)
```

### `getYearDigitCount` (line 249)
```text
public int getYearDigitCount()
```

### `setYearOnNewLine` (line 253)
```text
public void setYearOnNewLine(boolean yearOnNewLine)
```

### `isYearOnNewLine` (line 257)
```text
public boolean isYearOnNewLine()
```

### `setFirstDate` (line 261)
```text
public void setFirstDate(int startYear, int startMonth)
```

### `setLastDate` (line 283)
```text
public void setLastDate(int endYear, int endMonth)
```

### `onMonthSelected` (line 361)
```text
void onMonthSelected(int year, int month, int index)
```

### `getLabel` (line 366)
```text
CharSequence getLabel(Calendar calendar, int index)
```

### `onDateSelected` (line 27)
```text
void onDateSelected(int year, int month, int day, int index)
```

### `centerOnPosition` (line 122)
```text
public void centerOnPosition(int position)
```

### `centerOnSelection` (line 135)
```text
public void centerOnSelection()
```

### `setSelectedPosition` (line 139)
```text
public void setSelectedPosition(int position)
```

### `setSelectedDate` (line 146)
```text
public void setSelectedDate(int year, int month, int day)
```

### `getSelectedYear` (line 174)
```text
public int getSelectedYear()
```

### `getSelectedMonth` (line 178)
```text
public int getSelectedMonth()
```

### `getSelectedDay` (line 182)
```text
public int getSelectedDay()
```

### `getSelectedPosition` (line 186)
```text
public int getSelectedPosition()
```

### `setOnDateSelectedListener` (line 190)
```text
public void setOnDateSelectedListener(OnDateSelectedListener onDateSelectedListener)
```

### `setDateLabelAdapter` (line 194)
```text
public void setDateLabelAdapter(@Nullable MonthView.DateLabelAdapter dateLabelAdapter)
```

### `setDayLabelColor` (line 198)
```text
public void setDayLabelColor(int lblDayColor)
```

### `setDateLabelColor` (line 202)
```text
public void setDateLabelColor(int lblDateColor)
```

### `setDateLabelSelectedColor` (line 206)
```text
public void setDateLabelSelectedColor(int lblDateSelectedColor)
```

### `getLblDateColor` (line 210)
```text
public int getLblDateColor()
```

### `setLblDateColor` (line 214)
```text
public void setLblDateColor(int lblDateColor)
```

### `getLblDateSelectedColor` (line 218)
```text
public int getLblDateSelectedColor()
```

### `setLblDateSelectedColor` (line 222)
```text
public void setLblDateSelectedColor(int lblDateSelectedColor)
```

### `getLblDayColor` (line 226)
```text
public int getLblDayColor()
```

### `setLblDayColor` (line 230)
```text
public void setLblDayColor(int lblDayColor)
```

### `getStartYear` (line 234)
```text
public int getStartYear()
```

### `getStartDay` (line 238)
```text
public int getStartDay()
```

### `getStartMonth` (line 242)
```text
public int getStartMonth()
```

### `setFirstDate` (line 246)
```text
public void setFirstDate(int startYear, int startMonth, int startDay)
```

### `setLastDate` (line 260)
```text
public void setLastDate(int endYear, int endMonth, int endDay)
```

## [auto] Types

### `DotView`

| Field | Type |
|-------|------|
| `setColor` | `method` |
| `setColorRes` | `method` |
| `setCircleSize` | `method` |
| `setCircleSizeDp` | `method` |

### `MonthView`

| Field | Type |
|-------|------|
| `setSelectedMonth` | `method` |
| `setSelectedMonth` | `method` |
| `setSelectedMonth` | `method` |
| `getSelectedYear` | `method` |
| `getSelectedMonth` | `method` |
| `centerOnPosition` | `method` |
| `centerOnDate` | `method` |
| `centerOnSelection` | `method` |
| `getSelectedPosition` | `method` |
| `setOnMonthSelectedListener` | `method` |
| _(+14 more)_ | |

### `OnMonthSelectedListener`

| Field | Type |
|-------|------|
| `onMonthSelected` | `method` |

### `DateLabelAdapter`

| Field | Type |
|-------|------|
| `getLabel` | `method` |

### `OnDateSelectedListener`

| Field | Type |
|-------|------|
| `onDateSelected` | `method` |

### `TimelineView`

| Field | Type |
|-------|------|
| `centerOnPosition` | `method` |
| `centerOnSelection` | `method` |
| `setSelectedPosition` | `method` |
| `setSelectedDate` | `method` |
| `getSelectedYear` | `method` |
| `getSelectedMonth` | `method` |
| `getSelectedDay` | `method` |
| `getSelectedPosition` | `method` |
| `setOnDateSelectedListener` | `method` |
| `setDateLabelAdapter` | `method` |
| _(+14 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.view.calendar;
import android.annotation.TargetApi;
import android.content.Context;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.os.Build;
import androidx.annotation.ColorInt;
import androidx.annotation.ColorRes;
import androidx.core.content.ContextCompat;
// ... +15 more
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