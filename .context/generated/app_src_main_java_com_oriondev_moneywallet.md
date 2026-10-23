<!-- AUTO_START | hash: 3e1d103a | built: 2026-10-20T15:43 -->
# Context: `app/src/main/java/com/oriondev/moneywallet`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 1

## [auto] Public Functions

### `onCreate` (line 43)
```text
@Override public void onCreate()
```

## [auto] Types

### `App`

| Field | Type |
|-------|------|
| `onCreate` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet;
import android.app.Application;
import android.content.Context;
import androidx.multidex.MultiDex;
import com.oriondev.moneywallet.broadcast.AutoBackupBroadcastReceiver;
import com.oriondev.moneywallet.broadcast.DailyBroadcastReceiver;
import com.oriondev.moneywallet.broadcast.RecurrenceBroadcastReceiver;
import com.oriondev.moneywallet.storage.preference.BackendManager;
import com.oriondev.moneywallet.storage.preference.PreferenceManager;
import com.oriondev.moneywallet.ui.notification.NotificationContract;
// ... +3 more
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