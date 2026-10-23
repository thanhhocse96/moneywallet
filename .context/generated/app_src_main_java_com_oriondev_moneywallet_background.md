<!-- AUTO_START | hash: 0706cc2f | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/background`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 8

## [auto] Public Functions

### `loadInBackground` (line 36)
```text
@Override public abstract T loadInBackground()
```

### `deliverResult` (line 40)
```text
@Override public void deliverResult(T genericData)
```

### `loadInBackground` (line 48)
```text
@Override public List<ChangeLog> loadInBackground()
```

### `loadInBackground` (line 58)
```text
@Override public List<IconGroup> loadInBackground()
```

### `loadInBackground` (line 44)
```text
@Override public JSONObject loadInBackground()
```

### `loadInBackground` (line 46)
```text
@Override public List<License> loadInBackground()
```

### `loadInBackground` (line 76)
```text
@Override public OverviewData loadInBackground()
```

### `loadInBackground` (line 80)
```text
@Override @SuppressLint("UseSparseArrays") public PeriodDetailFlowData loadInBackground()
```

### `loadInBackground` (line 67)
```text
@Override public PeriodDetailSummaryData loadInBackground()
```

## [auto] Types

### `AbstractGenericLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |
| `deliverResult` | `method` |

### `ChangeLogLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

### `IconGroupLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

### `JsonResourceLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

### `LicenseLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

### `OverviewDataLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

### `PeriodDetailFlowLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

### `PeriodDetailSummaryLoader`

| Field | Type |
|-------|------|
| `loadInBackground` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.background;
import android.content.Context;
import androidx.loader.content.AsyncTaskLoader;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.model.ChangeLog;
import org.xmlpull.v1.XmlPullParser;
import org.xmlpull.v1.XmlPullParserException;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;
// ... +49 more
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