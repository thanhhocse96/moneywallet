<!-- AUTO_START | hash: 9a46c562 | built: 2026-10-20T15:41 -->
# Context: `app/src/gmap/java/com/oriondev/moneywallet/picker`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `createPicker` (line 53)
```text
public static MapPlacePicker createPicker(FragmentManager fragmentManager, String tag, Place defaultPlace)
```

### `onAttach` (line 65)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 73)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 86)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `fireCallbackSafely` (line 92)
```text
public void fireCallbackSafely()
```

### `onSaveInstanceState` (line 102)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 108)
```text
public boolean isSelected()
```

### `setCurrentPlace` (line 112)
```text
public void setCurrentPlace(Place place)
```

### `getCurrentPlace` (line 117)
```text
public Place getCurrentPlace()
```

### `showPicker` (line 121)
```text
public void showPicker()
```

### `onDetach` (line 134)
```text
@Override public void onDetach()
```

### `onActivityResult` (line 140)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent data)
```

### `onMapPlaceChanged` (line 159)
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
import com.google.android.gms.common.GooglePlayServicesNotAvailableException;
// ... +4 more
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