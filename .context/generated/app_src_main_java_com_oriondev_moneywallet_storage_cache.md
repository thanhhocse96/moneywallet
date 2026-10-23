<!-- AUTO_START | hash: e9b5824b | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/cache`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 3

## [auto] Public Functions

### `setExchangeRate` (line 65)
```text
public void setExchangeRate(String currency, double rate, long timestamp)
```

### `getExchangeRate` (line 78)
```text
public ExchangeRate getExchangeRate(String currency1, String currency2)
```

### `get` (line 39)
```text
public static Typeface get(Context context, String name)
```

### `apply` (line 58)
```text
public static void apply(TextView textView, String name)
```

## [auto] Types

### `ExchangeRateCache`

| Field | Type |
|-------|------|
| `setExchangeRate` | `method` |
| `getExchangeRate` | `method` |

### `TypefaceCache`

| Field | Type |
|-------|------|
| `get` | `method` |
| `apply` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.cache;
import android.content.ContentValues;
import android.content.Context;
import android.database.Cursor;
import android.text.TextUtils;
import com.oriondev.moneywallet.model.ExchangeRate;
import java.util.HashMap;
import java.util.Map;
import android.database.sqlite.SQLiteDatabase;
import android.database.sqlite.SQLiteOpenHelper;
// ... +2 more
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