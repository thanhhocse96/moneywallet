<!-- AUTO_START | hash: 636ed97d | built: 2026-10-20T15:41 -->
# Context: `app/src/gmap/java/com/oriondev/moneywallet/view`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `onCreate` (line 61)
```text
public void onCreate(Bundle savedInstanceState)
```

### `onStart` (line 65)
```text
public void onStart()
```

### `onResume` (line 69)
```text
public void onResume()
```

### `onPause` (line 73)
```text
public void onPause()
```

### `onStop` (line 77)
```text
public void onStop()
```

### `onDestroy` (line 81)
```text
public void onDestroy()
```

### `onSaveInstanceState` (line 85)
```text
public void onSaveInstanceState(Bundle outState)
```

### `onLowMemory` (line 89)
```text
public void onLowMemory()
```

### `loadMapAsync` (line 93)
```text
public void loadMapAsync(OnMapLoadedCallback callback)
```

### `isMapReady` (line 98)
```text
public boolean isMapReady()
```

### `onMapReady` (line 102)
```text
@Override public void onMapReady(GoogleMap googleMap)
```

### `disableMapInteractions` (line 110)
```text
public void disableMapInteractions()
```

### `addPlaces` (line 114)
```text
public void addPlaces(List<Place> places)
```

### `addCoordinates` (line 146)
```text
public void addCoordinates(Coordinates coordinates)
```

### `clear` (line 154)
```text
public void clear()
```

### `setOnInfoClickListener` (line 159)
```text
public void setOnInfoClickListener(OnInfoWindowClickListener callback)
```

### `onInfoWindowClick` (line 166)
```text
@Override public void onInfoWindowClick(Marker marker)
```

### `onMapReady` (line 179)
```text
void onMapReady()
```

### `onInfoWindowClick` (line 184)
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
import android.os.Bundle;
import android.view.View;
import com.google.android.gms.maps.CameraUpdateFactory;
import com.google.android.gms.maps.GoogleMap;
import com.google.android.gms.maps.MapView;
import com.google.android.gms.maps.OnMapReadyCallback;
import com.google.android.gms.maps.model.LatLng;
import com.google.android.gms.maps.model.Marker;
import com.google.android.gms.maps.model.MarkerOptions;
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