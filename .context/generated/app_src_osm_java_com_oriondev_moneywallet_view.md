<!-- AUTO_START | hash: 60ea6279 | built: 2026-10-20T15:42 -->
# Context: `app/src/osm/java/com/oriondev/moneywallet/view`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `onCreate` (line 95)
```text
public void onCreate(Bundle savedInstanceState)
```

### `onStart` (line 100)
```text
public void onStart()
```

### `onResume` (line 104)
```text
public void onResume()
```

### `onPause` (line 108)
```text
public void onPause()
```

### `onStop` (line 112)
```text
public void onStop()
```

### `onDestroy` (line 116)
```text
public void onDestroy()
```

### `onSaveInstanceState` (line 120)
```text
public void onSaveInstanceState(Bundle outState)
```

### `onLowMemory` (line 124)
```text
public void onLowMemory()
```

### `loadMapAsync` (line 128)
```text
public void loadMapAsync(OnMapLoadedCallback callback)
```

### `isMapReady` (line 136)
```text
public boolean isMapReady()
```

### `disableMapInteractions` (line 140)
```text
public void disableMapInteractions()
```

### `addPlaces` (line 153)
```text
public void addPlaces(List<Place> places)
```

### `addCoordinates` (line 209)
```text
public void addCoordinates(Coordinates coordinates)
```

### `clear` (line 235)
```text
public void clear()
```

### `setOnInfoClickListener` (line 240)
```text
public void setOnInfoClickListener(OnInfoWindowClickListener callback)
```

### `getCenterCoordinates` (line 244)
```text
public Coordinates getCenterCoordinates()
```

### `setMinZoomLevel` (line 249)
```text
public void setMinZoomLevel()
```

### `onMapReady` (line 255)
```text
void onMapReady()
```

### `onInfoWindowClick` (line 260)
```text
void onInfoWindowClick(long placeId)
```

## [auto] Types

### `MapViewWrapper`

| Field | Type |
|-------|------|
| `onCreate` | `method` |
| `onStart` | `method` |
| `onResume` | `method` |
| `onPause` | `method` |
| `onStop` | `method` |
| `onDestroy` | `method` |
| `onSaveInstanceState` | `method` |
| `onLowMemory` | `method` |
| `loadMapAsync` | `method` |
| `isMapReady` | `method` |
| _(+7 more)_ | |

### `OnMapLoadedCallback`

| Field | Type |
|-------|------|
| `onMapReady` | `method` |

### `OnInfoWindowClickListener`

| Field | Type |
|-------|------|
| `onInfoWindowClick` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.view;
import android.content.Context;
import android.graphics.Color;
import android.graphics.drawable.Drawable;
import android.os.Bundle;
import android.view.MotionEvent;
import android.view.View;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.model.Coordinates;
import com.oriondev.moneywallet.model.Place;
// ... +13 more
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