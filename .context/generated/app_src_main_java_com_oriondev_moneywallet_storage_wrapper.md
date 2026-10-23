<!-- AUTO_START | hash: 6ba434ae | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/wrapper`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 5

## [auto] Public Functions

### `getCount` (line 97)
```text
@Override public int getCount()
```

### `onMove` (line 102)
```text
@Override public boolean onMove(int oldPosition, int newPosition)
```

### `getColumnNames` (line 116)
```text
@Override public String[] getColumnNames()
```

### `getString` (line 123)
```text
@Override public String getString(int i)
```

### `getShort` (line 133)
```text
@Override public short getShort(int i)
```

### `getInt` (line 143)
```text
@Override public int getInt(int i)
```

### `getLong` (line 153)
```text
@Override public long getLong(int i)
```

### `getFloat` (line 163)
```text
@Override public float getFloat(int i)
```

### `getDouble` (line 173)
```text
@Override public double getDouble(int i)
```

### `isNull` (line 183)
```text
@Override public boolean isNull(int i)
```

### `deactivate` (line 193)
```text
@Override public void deactivate()
```

### `close` (line 199)
```text
@Override public void close()
```

### `registerContentObserver` (line 205)
```text
@Override public void registerContentObserver(ContentObserver observer)
```

### `unregisterContentObserver` (line 210)
```text
@Override public void unregisterContentObserver(ContentObserver observer)
```

### `registerDataSetObserver` (line 215)
```text
@Override public void registerDataSetObserver(DataSetObserver observer)
```

### `unregisterDataSetObserver` (line 220)
```text
@Override public void unregisterDataSetObserver(DataSetObserver observer)
```

### `requery` (line 225)
```text
@Override public boolean requery()
```

### `getInt` (line 122)
```text
@Override public int getInt(int index)
```

## [auto] Types

### `AbstractHeaderCursor`

| Field | Type |
|-------|------|
| `getCount` | `method` |
| `onMove` | `method` |
| `getColumnNames` | `method` |
| `getString` | `method` |
| `getShort` | `method` |
| `getInt` | `method` |
| `getLong` | `method` |
| `getFloat` | `method` |
| `getDouble` | `method` |
| `isNull` | `method` |
| _(+7 more)_ | |

### `DebtHeaderCursor`

| Field | Type |
|-------|------|
| `getInt` | `method` |

### `TransactionHeaderCursor`

### `TransferHeaderCursor`

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.wrapper;
import android.database.AbstractCursor;
import android.database.ContentObserver;
import android.database.Cursor;
import android.database.DataSetObserver;
import android.util.SparseArray;
import com.oriondev.moneywallet.model.Pair;
import java.util.ArrayList;
import java.util.List;
import androidx.annotation.NonNull;
// ... +7 more
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