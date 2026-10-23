<!-- AUTO_START | hash: 0b5aac21 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/view/text`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 6

## [auto] Public Functions

### `setMode` (line 346)
```text
public void setMode(Mode mode)
```

### `getMode` (line 353)
```text
public Mode getMode()
```

### `setFloatingLabelColorNormal` (line 357)
```text
public void setFloatingLabelColorNormal(int floatingLabelColorNormal)
```

### `setFloatingLabelColorFocused` (line 361)
```text
public void setFloatingLabelColorFocused(int floatingLabelColorFocused)
```

### `setBottomLineColorNormal` (line 365)
```text
public void setBottomLineColorNormal(int bottomLineColorNormal)
```

### `setBottomLineColorFocused` (line 370)
```text
public void setBottomLineColorFocused(int bottomLineColorFocused)
```

### `setBottomLineColorError` (line 374)
```text
public void setBottomLineColorError(int bottomLineColorError)
```

### `setLeftIconColorNormal` (line 378)
```text
public void setLeftIconColorNormal(int iconColorNormal)
```

### `setLeftIconColorFocused` (line 385)
```text
public void setLeftIconColorFocused(int iconColorFocused)
```

### `setLeftDrawable` (line 392)
```text
public void setLeftDrawable(@DrawableRes int drawable)
```

### `setLeftDrawable` (line 396)
```text
public void setLeftDrawable(Drawable drawable)
```

### `setTextViewMode` (line 402)
```text
public void setTextViewMode(boolean textViewMode)
```

### `getTextAsString` (line 408)
```text
public String getTextAsString()
```

### `setOnCancelButtonClickListener` (line 412)
```text
public void setOnCancelButtonClickListener(CancelButtonListener cancelButtonClickListener)
```

### `showError` (line 467)
```text
public void showError(@StringRes int errorMessage)
```

### `showError` (line 471)
```text
public void showError(String errorMessage)
```

### `addValidator` (line 477)
```text
public void addValidator(Validator validator)
```

### `removeValidator` (line 481)
```text
public void removeValidator(Validator validator)
```

### `removeAllValidators` (line 485)
```text
public void removeAllValidators()
```

### `getValidatorCount` (line 489)
```text
public int getValidatorCount()
```

### `validate` (line 493)
```text
public boolean validate()
```

### `onAnimationUpdate` (line 520)
```text
@Override public void onAnimationUpdate(ValueAnimator animation)
```

### `onTouch` (line 525)
```text
@Override public boolean onTouch(View v, MotionEvent event)
```

### `onCancelButtonClick` (line 555)
```text
boolean onCancelButtonClick(@NonNull MaterialEditText materialEditText)
```

### `setMode` (line 221)
```text
public void setMode(Mode mode)
```

### `getMode` (line 228)
```text
public Mode getMode()
```

### `setFloatingLabelColor` (line 232)
```text
public void setFloatingLabelColor(int color)
```

### `setBottomLineColor` (line 236)
```text
public void setBottomLineColor(int color)
```

### `setLeftIconColor` (line 240)
```text
public void setLeftIconColor(int iconColor)
```

### `setLeftDrawable` (line 247)
```text
public void setLeftDrawable(@DrawableRes int drawable)
```

### `setLeftDrawable` (line 251)
```text
public void setLeftDrawable(Drawable drawable)
```

### `getMode` (line 35)
```text
public Mode getMode()
```

### `getMode` (line 39)
```text
public static Mode getMode(int value)
```

### `getErrorMessage` (line 53)
```text
@NonNull @Override public String getErrorMessage()
```

### `isValid` (line 59)
```text
@Override public boolean isValid(@NonNull CharSequence charSequence)
```

### `autoValidate` (line 64)
```text
@Override public boolean autoValidate()
```

### `getErrorMessage` (line 29)
```text
@NonNull String getErrorMessage()
```

### `isValid` (line 32)
```text
boolean isValid(@NonNull CharSequence charSequence)
```

### `autoValidate` (line 34)
```text
boolean autoValidate()
```

## [auto] Types

### `MaterialEditText`

| Field | Type |
|-------|------|
| `setMode` | `method` |
| `getMode` | `method` |
| `setFloatingLabelColorNormal` | `method` |
| `setFloatingLabelColorFocused` | `method` |
| `setBottomLineColorNormal` | `method` |
| `setBottomLineColorFocused` | `method` |
| `setBottomLineColorError` | `method` |
| `setLeftIconColorNormal` | `method` |
| `setLeftIconColorFocused` | `method` |
| `setLeftDrawable` | `method` |
| _(+13 more)_ | |

### `CancelButtonListener`

| Field | Type |
|-------|------|
| `onCancelButtonClick` | `method` |

### `MaterialTextView`

| Field | Type |
|-------|------|
| `setMode` | `method` |
| `getMode` | `method` |
| `setFloatingLabelColor` | `method` |
| `setBottomLineColor` | `method` |
| `setLeftIconColor` | `method` |
| `setLeftDrawable` | `method` |
| `setLeftDrawable` | `method` |

### `Mode`

### `NonEmptyTextValidator`

| Field | Type |
|-------|------|
| `getErrorMessage` | `method` |
| `isValid` | `method` |
| `autoValidate` | `method` |

### `Validator`

| Field | Type |
|-------|------|
| `getErrorMessage` | `method` |
| `isValid` | `method` |
| `autoValidate` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.view.text;
import android.animation.ValueAnimator;
import android.content.Context;
import android.content.res.TypedArray;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.graphics.PorterDuff;
import android.graphics.Rect;
import android.graphics.drawable.Drawable;
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