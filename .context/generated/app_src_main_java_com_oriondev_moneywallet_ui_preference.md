<!-- AUTO_START | hash: 3747de59 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/preference`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 6

## [auto] Public Functions

### `onBindViewHolder` (line 57)
```text
@Override public void onBindViewHolder(PreferenceViewHolder holder)
```

### `setColor` (line 66)
```text
public void setColor(int newColor)
```

### `setContent` (line 74)
```text
public void setContent(String content)
```

### `setContent` (line 78)
```text
public void setContent(int content)
```

### `setInput` (line 82)
```text
public void setInput(String hint, boolean allowEmptyInput, int inputType)
```

### `setCurrentValue` (line 88)
```text
public void setCurrentValue(String value)
```

### `setInput` (line 92)
```text
public void setInput(int hint, boolean allowEmptyInput, int inputType)
```

### `setEntries` (line 69)
```text
public void setEntries(String[] entries)
```

### `setEntries` (line 73)
```text
public void setEntries(int array)
```

### `setEntryValues` (line 77)
```text
public void setEntryValues(String[] entryValues)
```

### `setValue` (line 81)
```text
public void setValue(int valueIndex)
```

### `getValue` (line 85)
```text
public String getValue()
```

### `setValue` (line 89)
```text
public void setValue(String value)
```

## [auto] Types

### `ColorPreference`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `setColor` | `method` |

### `ThemedInputPreference`

| Field | Type |
|-------|------|
| `setContent` | `method` |
| `setContent` | `method` |
| `setInput` | `method` |
| `setCurrentValue` | `method` |
| `setInput` | `method` |

### `ThemedListPreference`

| Field | Type |
|-------|------|
| `setEntries` | `method` |
| `setEntries` | `method` |
| `setEntryValues` | `method` |
| `setValue` | `method` |
| `getValue` | `method` |
| `setValue` | `method` |

### `ThemedPreference`

### `ThemedPreferenceCategory`

### `ThemedSwitchPreference`

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.preference;
import android.content.Context;
import android.graphics.Color;
import androidx.preference.PreferenceViewHolder;
import android.util.AttributeSet;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.ui.view.CircleView;
import androidx.annotation.NonNull;
import androidx.preference.Preference;
import android.text.TextUtils;
// ... +5 more
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