<!-- AUTO_START | hash: 7c7495e4 | built: 2026-10-20T15:42 -->
# Context: `app/src/osm/java/com/oriondev/moneywallet/picker`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `createPicker` (line 50)
```text
public static MapPlacePicker createPicker(FragmentManager fragmentManager, String tag, Place defaultPlace)
```

### `onAttach` (line 62)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 70)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 83)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `fireCallbackSafely` (line 89)
```text
public void fireCallbackSafely()
```

### `onSaveInstanceState` (line 99)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 105)
```text
public boolean isSelected()
```

### `setCurrentPlace` (line 109)
```text
public void setCurrentPlace(Place place)
```

### `getCurrentPlace` (line 114)
```text
public Place getCurrentPlace()
```

### `showPicker` (line 118)
```text
public void showPicker()
```

### `onDetach` (line 123)
```text
@Override public void onDetach()
```

### `onActivityResult` (line 129)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent data)
```

### `onMapPlaceChanged` (line 144)
```text
void onMapPlaceChanged(String tag, Place place)
```

## [auto] Types

### `MapPlacePicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `fireCallbackSafely` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `setCurrentPlace` | `method` |
| `getCurrentPlace` | `method` |
| `showPicker` | `method` |
| _(+2 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onMapPlaceChanged` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.picker;
import android.app.Activity;
import android.content.Context;
import android.content.Intent;
import android.os.Bundle;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentManager;
import com.oriondev.moneywallet.model.Place;
// ... +1 more
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