<!-- AUTO_START | hash: 26b6a064 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/storage/preference`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 3

## [auto] Public Functions

### `initialize` (line 46)
```text
public static void initialize(Context context)
```

### `setAutoBackupEnabled` (line 50)
```text
public static void setAutoBackupEnabled(String backendId, boolean enabled)
```

### `setAutoBackupOnWiFiOnly` (line 69)
```text
public static void setAutoBackupOnWiFiOnly(String backendId, boolean wifiOnly)
```

### `setAutoBackupWhenDataIsChangedOnly` (line 73)
```text
public static void setAutoBackupWhenDataIsChangedOnly(String backendId, boolean dataChangedOnly)
```

### `setAutoBackupHoursOffset` (line 77)
```text
public static void setAutoBackupHoursOffset(String backendId, int offset)
```

### `setAutoBackupFolder` (line 81)
```text
public static void setAutoBackupFolder(String backendId, String folder)
```

### `setAutoBackupPassword` (line 85)
```text
public static void setAutoBackupPassword(String backendId, String password)
```

### `setAutoBackupLastTime` (line 89)
```text
public static void setAutoBackupLastTime(String backendId, long timestamp)
```

### `getAutoBackupEnabledServices` (line 93)
```text
public static Set<String> getAutoBackupEnabledServices()
```

### `isAutoBackupEnabled` (line 97)
```text
public static boolean isAutoBackupEnabled(String backendId)
```

### `isAutoBackupOnWiFiOnly` (line 101)
```text
public static boolean isAutoBackupOnWiFiOnly(String backendId)
```

### `isAutoBackupWhenDataIsChangedOnly` (line 105)
```text
public static boolean isAutoBackupWhenDataIsChangedOnly(String backendId)
```

### `getAutoBackupHoursOffset` (line 109)
```text
public static int getAutoBackupHoursOffset(String backendId)
```

### `getAutoBackupFolder` (line 113)
```text
public static String getAutoBackupFolder(String backendId)
```

### `getAutoBackupPassword` (line 117)
```text
public static String getAutoBackupPassword(String backendId)
```

### `getAutoBackupLastTime` (line 121)
```text
public static long getAutoBackupLastTime(String backendId)
```

### `onCurrentWalletChanged` (line 27)
```text
void onCurrentWalletChanged(long walletId)
```

### `initialize` (line 102)
```text
public static void initialize(Context context)
```

### `setCurrentWallet` (line 106)
```text
public static void setCurrentWallet(Context context, long walletId)
```

### `setCurrentLockMode` (line 113)
```text
public static void setCurrentLockMode(LockMode lockMode)
```

### `setCurrentLockCode` (line 117)
```text
public static void setCurrentLockCode(String code)
```

### `setLastLockTime` (line 121)
```text
public static void setLastLockTime(long time)
```

### `setCurrencyEnabled` (line 125)
```text
public static void setCurrencyEnabled(boolean enabled)
```

### `setGroupDigitsEnabled` (line 129)
```text
public static void setGroupDigitsEnabled(boolean enabled)
```

### `setRoundDecimalsEnabled` (line 133)
```text
public static void setRoundDecimalsEnabled(boolean enabled)
```

### `setShowPlusMinusSymbolEnabled` (line 137)
```text
public static void setShowPlusMinusSymbolEnabled(boolean enabled)
```

### `setCurrentDateFormatIndex` (line 141)
```text
public static void setCurrentDateFormatIndex(int index)
```

### `setCurrentFirstDayOfWeek` (line 145)
```text
public static void setCurrentFirstDayOfWeek(int day)
```

### `setCurrentFirstDayOfMonth` (line 149)
```text
public static void setCurrentFirstDayOfMonth(int day)
```

### `setCurrentGroupType` (line 153)
```text
public static void setCurrentGroupType(Group groupType)
```

### `setCurrentIncomeColor` (line 157)
```text
public static void setCurrentIncomeColor(int color)
```

### `setCurrentExpenseColor` (line 161)
```text
public static void setCurrentExpenseColor(int color)
```

### `setDateFormat` (line 165)
```text
public static void setDateFormat(int index)
```

### `setCurrentDailyReminder` (line 169)
```text
public static void setCurrentDailyReminder(Context context, int hour)
```

### `setCurrentExchangeRateService` (line 182)
```text
public static void setCurrentExchangeRateService(int exchangeRateService)
```

### `setLastExchangeRateUpdateTimestamp` (line 186)
```text
public static void setLastExchangeRateUpdateTimestamp(long timestamp)
```

### `setIsFirstStartDone` (line 190)
```text
public static void setIsFirstStartDone(boolean done)
```

### `setServiceApiKey` (line 194)
```text
public static void setServiceApiKey(int service, String key)
```

### `setCurrencyConverterLastCurrency1` (line 198)
```text
public static void setCurrencyConverterLastCurrency1(String iso)
```

### `setCurrencyConverterLastCurrency2` (line 202)
```text
public static void setCurrencyConverterLastCurrency2(String iso)
```

### `setLastTimeDataIsChanged` (line 206)
```text
public static void setLastTimeDataIsChanged(long timestamp)
```

### `getCurrentWallet` (line 210)
```text
public static long getCurrentWallet()
```

### `getCurrentLockMode` (line 214)
```text
public static LockMode getCurrentLockMode()
```

### `getCurrentLockCode` (line 218)
```text
public static String getCurrentLockCode()
```

### `getLastLockTime` (line 222)
```text
public static long getLastLockTime()
```

### `isCurrencyEnabled` (line 226)
```text
public static boolean isCurrencyEnabled()
```

### `isGroupDigitEnabled` (line 230)
```text
public static boolean isGroupDigitEnabled()
```

### `isRoundDecimalsEnabled` (line 234)
```text
public static boolean isRoundDecimalsEnabled()
```

### `isShowPlusMinusSymbolEnabled` (line 238)
```text
public static boolean isShowPlusMinusSymbolEnabled()
```

### `getCurrentDateFormatIndex` (line 242)
```text
public static int getCurrentDateFormatIndex()
```

### `getFirstDayOfWeek` (line 247)
```text
public static int getFirstDayOfWeek()
```

### `getFirstDayOfMonth` (line 252)
```text
public static int getFirstDayOfMonth()
```

### `getCurrentGroupType` (line 256)
```text
public static Group getCurrentGroupType()
```

### `getCurrentIncomeColor` (line 264)
```text
public static int getCurrentIncomeColor()
```

### `getCurrentExpenseColor` (line 268)
```text
public static int getCurrentExpenseColor()
```

### `getCurrentDailyReminder` (line 272)
```text
public static int getCurrentDailyReminder()
```

### `getCurrentExchangeRateService` (line 276)
```text
public static int getCurrentExchangeRateService()
```

### `hasCurrentExchangeRateServiceDefaultApiKey` (line 280)
```text
public static boolean hasCurrentExchangeRateServiceDefaultApiKey()
```

### `getCurrentExchangeRateServiceCustomApiKey` (line 289)
```text
public static String getCurrentExchangeRateServiceCustomApiKey()
```

### `getLastExchangeRateUpdateTimestamp` (line 293)
```text
public static long getLastExchangeRateUpdateTimestamp()
```

### `isFirstStartDone` (line 297)
```text
public static boolean isFirstStartDone()
```

### `getServiceApiKey` (line 301)
```text
public static String getServiceApiKey(int service)
```

### `getCurrencyConverterLastCurrency1` (line 305)
```text
public static String getCurrencyConverterLastCurrency1()
```

### `getCurrencyConverterLastCurrency2` (line 309)
```text
public static String getCurrencyConverterLastCurrency2()
```

### `getLastTimeDataIsChanged` (line 313)
```text
public static long getLastTimeDataIsChanged()
```

### `registerCurrentWalletObserver` (line 324)
```text
public static BroadcastReceiver registerCurrentWalletObserver(Context context, final CurrentWalletController controller)
```

### `unregisterCurrentWalletObserver` (line 342)
```text
public static void unregisterCurrentWalletObserver(Context context, BroadcastReceiver broadcastReceiver)
```

## [auto] Types

### `BackendManager`

| Field | Type |
|-------|------|
| `initialize` | `method` |
| `setAutoBackupEnabled` | `method` |
| `setAutoBackupOnWiFiOnly` | `method` |
| `setAutoBackupWhenDataIsChangedOnly` | `method` |
| `setAutoBackupHoursOffset` | `method` |
| `setAutoBackupFolder` | `method` |
| `setAutoBackupPassword` | `method` |
| `setAutoBackupLastTime` | `method` |
| `getAutoBackupEnabledServices` | `method` |
| `isAutoBackupEnabled` | `method` |
| _(+6 more)_ | |

### `CurrentWalletController`

| Field | Type |
|-------|------|
| `onCurrentWalletChanged` | `method` |

### `PreferenceManager`

| Field | Type |
|-------|------|
| `initialize` | `method` |
| `setCurrentWallet` | `method` |
| `setCurrentLockMode` | `method` |
| `setCurrentLockCode` | `method` |
| `setLastLockTime` | `method` |
| `setCurrencyEnabled` | `method` |
| `setGroupDigitsEnabled` | `method` |
| `setRoundDecimalsEnabled` | `method` |
| `setShowPlusMinusSymbolEnabled` | `method` |
| `setCurrentDateFormatIndex` | `method` |
| _(+40 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.storage.preference;
import android.content.Context;
import android.content.SharedPreferences;
import java.util.HashSet;
import java.util.Set;
import android.content.BroadcastReceiver;
import android.content.Intent;
import android.content.IntentFilter;
import android.graphics.Color;
import androidx.localbroadcastmanager.content.LocalBroadcastManager;
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