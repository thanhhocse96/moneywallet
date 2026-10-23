<!-- AUTO_START | hash: 690cf724 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/service`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 7

## [auto] Public Functions

### `buildIntent` (line 45)
```text
public static Intent buildIntent(Activity activity)
```

### `startInForeground` (line 121)
```text
public static void startInForeground(Context context, Intent intent)
```

### `enqueueWork` (line 50)
```text
public static void enqueueWork(Context context, Intent intent)
```

### `isLegacyEditionDetected` (line 46)
```text
public static boolean isLegacyEditionDetected(Context context)
```

## [auto] Types

### `AbstractCurrencyRateDownloadIntentService`

| Field | Type |
|-------|------|
| `ildIntent` | `method` |

### `MissingApiKey`

### `AttachmentHandlerIntentService`

### `BackendHandlerIntentService`

### `BackupHandlerIntentService`

| Field | Type |
|-------|------|
| `startInForeground` | `method` |

### `ImportExportIntentService`

### `RecurrenceHandlerIntentService`

| Field | Type |
|-------|------|
| `enqueueWork` | `method` |

### `UpgradeLegacyEditionIntentService`

| Field | Type |
|-------|------|
| `isLegacyEditionDetected` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.service;
import android.app.Activity;
import android.app.IntentService;
import android.content.Intent;
import androidx.annotation.Nullable;
import androidx.core.app.NotificationCompat;
import androidx.core.app.NotificationManagerCompat;
import androidx.localbroadcastmanager.content.LocalBroadcastManager;
import com.oriondev.moneywallet.R;
import com.oriondev.moneywallet.service.openexchangerates.OpenExchangeRatesCurrencyRateDownloadIntentService;
// ... +71 more
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