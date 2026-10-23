<!-- AUTO_START | hash: 8d563719 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/broadcast`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 7

## [auto] Public Functions

### `scheduleAutoBackupTask` (line 44)
```text
public static void scheduleAutoBackupTask(Context context)
```

### `onReceive` (line 89)
```text
@Override public void onReceive(Context context, Intent intent)
```

### `onReceive` (line 33)
```text
@Override public void onReceive(Context context, Intent intent)
```

### `scheduleDailyNotification` (line 44)
```text
public static void scheduleDailyNotification(Context context)
```

### `scheduleDailyNotification` (line 51)
```text
public static void scheduleDailyNotification(Context context, int hour)
```

### `cancelDailyNotification` (line 67)
```text
public static void cancelDailyNotification(Context context)
```

### `onReceive` (line 80)
```text
@Override public void onReceive(Context context, Intent intent)
```

### `onReceive` (line 40)
```text
@Override public void onReceive(Context context, Intent intent)
```

### `scheduleRecurrenceTask` (line 45)
```text
public static void scheduleRecurrenceTask(Context context)
```

### `onReceive` (line 138)
```text
@Override public void onReceive(Context context, Intent intent)
```

## [auto] Types

### `AutoBackupBroadcastReceiver`

| Field | Type |
|-------|------|
| `scheduleAutoBackupTask` | `method` |
| `onReceive` | `method` |

### `BootBroadcastReceiver`

| Field | Type |
|-------|------|
| `onReceive` | `method` |

### `DailyBroadcastReceiver`

| Field | Type |
|-------|------|
| `scheduleDailyNotification` | `method` |
| `scheduleDailyNotification` | `method` |
| `cancelDailyNotification` | `method` |
| `onReceive` | `method` |

### `LocalAction`

### `Message`

### `NotificationBroadcastReceiver`

| Field | Type |
|-------|------|
| `onReceive` | `method` |

### `RecurrenceBroadcastReceiver`

| Field | Type |
|-------|------|
| `scheduleRecurrenceTask` | `method` |
| `onReceive` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.broadcast;
import android.app.AlarmManager;
import android.app.PendingIntent;
import android.app.Service;
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import com.oriondev.moneywallet.api.BackendServiceFactory;
import com.oriondev.moneywallet.model.IFile;
import com.oriondev.moneywallet.service.BackupHandlerIntentService;
// ... +21 more
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