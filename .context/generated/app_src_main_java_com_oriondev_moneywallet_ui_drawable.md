<!-- AUTO_START | hash: f144e0cd | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/drawable`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 2

## [auto] Public Functions

### `draw` (line 46)
```text
@Override public void draw(@NonNull Canvas canvas)
```

### `setAlpha` (line 59)
```text
@Override public void setAlpha(int alpha)
```

### `setColorFilter` (line 64)
```text
@Override public void setColorFilter(@Nullable ColorFilter colorFilter)
```

### `getOpacity` (line 69)
```text
@Override public int getOpacity()
```

### `draw` (line 90)
```text
@Override public void draw(Canvas canvas)
```

### `setAlpha` (line 123)
```text
@Override public void setAlpha(int alpha)
```

### `setColorFilter` (line 128)
```text
@Override public void setColorFilter(ColorFilter cf)
```

### `getOpacity` (line 133)
```text
@Override public int getOpacity()
```

### `getIntrinsicWidth` (line 138)
```text
@Override public int getIntrinsicWidth()
```

### `getIntrinsicHeight` (line 143)
```text
@Override public int getIntrinsicHeight()
```

### `builder` (line 148)
```text
public static IShapeBuilder builder()
```

### `width` (line 192)
```text
public IConfigBuilder width(int width)
```

### `height` (line 197)
```text
public IConfigBuilder height(int height)
```

### `textColor` (line 202)
```text
public IConfigBuilder textColor(int color)
```

### `withBorder` (line 207)
```text
public IConfigBuilder withBorder(int thickness)
```

### `useFont` (line 212)
```text
public IConfigBuilder useFont(Typeface font)
```

### `fontSize` (line 217)
```text
public IConfigBuilder fontSize(int size)
```

### `bold` (line 222)
```text
public IConfigBuilder bold()
```

### `toUpperCase` (line 227)
```text
public IConfigBuilder toUpperCase()
```

### `beginConfig` (line 232)
```text
@Override public IConfigBuilder beginConfig()
```

### `endConfig` (line 237)
```text
@Override public IShapeBuilder endConfig()
```

### `rect` (line 242)
```text
@Override public IBuilder rect()
```

### `round` (line 248)
```text
@Override public IBuilder round()
```

### `roundRect` (line 254)
```text
@Override public IBuilder roundRect(int radius)
```

### `buildRect` (line 262)
```text
@Override public TextDrawable buildRect(String text, int color)
```

### `buildRoundRect` (line 268)
```text
@Override public TextDrawable buildRoundRect(String text, int color, int radius)
```

### `buildRound` (line 274)
```text
@Override public TextDrawable buildRound(String text, int color)
```

### `build` (line 280)
```text
@Override public TextDrawable build(String text, int color)
```

### `width` (line 290)
```text
IConfigBuilder width(int width)
```

### `height` (line 292)
```text
IConfigBuilder height(int height)
```

### `textColor` (line 294)
```text
IConfigBuilder textColor(int color)
```

### `withBorder` (line 296)
```text
IConfigBuilder withBorder(int thickness)
```

### `useFont` (line 298)
```text
IConfigBuilder useFont(Typeface font)
```

### `fontSize` (line 300)
```text
IConfigBuilder fontSize(int size)
```

### `bold` (line 302)
```text
IConfigBuilder bold()
```

### `toUpperCase` (line 304)
```text
IConfigBuilder toUpperCase()
```

### `endConfig` (line 306)
```text
IShapeBuilder endConfig()
```

### `build` (line 311)
```text
TextDrawable build(String text, int color)
```

### `beginConfig` (line 316)
```text
IConfigBuilder beginConfig()
```

### `rect` (line 318)
```text
IBuilder rect()
```

### `round` (line 320)
```text
IBuilder round()
```

### `roundRect` (line 322)
```text
IBuilder roundRect(int radius)
```

### `buildRect` (line 324)
```text
TextDrawable buildRect(String text, int color)
```

### `buildRoundRect` (line 326)
```text
TextDrawable buildRoundRect(String text, int color, int radius)
```

### `buildRound` (line 328)
```text
TextDrawable buildRound(String text, int color)
```

## [auto] Types

### `DoubleIconDrawable`

| Field | Type |
|-------|------|
| `draw` | `method` |
| `setAlpha` | `method` |
| `setColorFilter` | `method` |
| `getOpacity` | `method` |

### `TextDrawable`

| Field | Type |
|-------|------|
| `draw` | `method` |
| `setAlpha` | `method` |
| `setColorFilter` | `method` |
| `getOpacity` | `method` |
| `getIntrinsicWidth` | `method` |
| `getIntrinsicHeight` | `method` |
| `ilder` | `method` |

### `Builder`

| Field | Type |
|-------|------|
| `width` | `method` |
| `height` | `method` |
| `textColor` | `method` |
| `withBorder` | `method` |
| `seFont` | `method` |
| `fontSize` | `method` |
| `old` | `method` |
| `toUpperCase` | `method` |
| `eginConfig` | `method` |
| `endConfig` | `method` |
| _(+7 more)_ | |

### `IConfigBuilder`

| Field | Type |
|-------|------|
| `width` | `method` |
| `height` | `method` |
| `textColor` | `method` |
| `withBorder` | `method` |
| `seFont` | `method` |
| `fontSize` | `method` |
| `old` | `method` |
| `toUpperCase` | `method` |
| `endConfig` | `method` |

### `IBuilder`

| Field | Type |
|-------|------|
| `ild` | `method` |

### `IShapeBuilder`

| Field | Type |
|-------|------|
| `eginConfig` | `method` |
| `rect` | `method` |
| `round` | `method` |
| `roundRect` | `method` |
| `ildRect` | `method` |
| `ildRoundRect` | `method` |
| `ildRound` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.drawable;
import android.content.Context;
import android.graphics.Canvas;
import android.graphics.ColorFilter;
import android.graphics.PixelFormat;
import android.graphics.drawable.Drawable;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import com.oriondev.moneywallet.model.Icon;
import com.oriondev.moneywallet.utils.IconLoader;
// ... +9 more
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