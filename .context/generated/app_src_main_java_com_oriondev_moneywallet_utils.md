<!-- AUTO_START | hash: ecb86060 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/utils`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 10

## [auto] Public Functions

### `initialize` (line 58)
```text
public static void initialize(Context context)
```

### `invalidateCache` (line 81)
```text
public static void invalidateCache(Context context)
```

### `getCurrency` (line 160)
```text
public static CurrencyUnit getCurrency(String iso)
```

### `getCurrencies` (line 166)
```text
public static Collection<CurrencyUnit> getCurrencies()
```

### `getExchangeRate` (line 172)
```text
public static ExchangeRate getExchangeRate(CurrencyUnit currency1, CurrencyUnit currency2)
```

### `getDefaultCurrency` (line 181)
```text
public static CurrencyUnit getDefaultCurrency()
```

### `getExchangeRateCache` (line 189)
```text
public static ExchangeRateCache getExchangeRateCache()
```

### `applyDate` (line 62)
```text
public static void applyDate(TextView textView, Date date)
```

### `applyTime` (line 66)
```text
public static void applyTime(TextView textView, Date date)
```

### `getDateFromToday` (line 70)
```text
public static String getDateFromToday(Date date)
```

### `applyDateFromToday` (line 75)
```text
public static void applyDateFromToday(TextView textView, Date date, @StringRes int header)
```

### `applyDateTime` (line 83)
```text
public static void applyDateTime(TextView textView, Date date)
```

### `getFormattedDate` (line 87)
```text
public static String getFormattedDate(Date date)
```

### `getFormattedDate` (line 91)
```text
public static String getFormattedDate(Date date, int index)
```

### `getFormattedTime` (line 95)
```text
public static String getFormattedTime(Date date)
```

### `getFormattedTime` (line 99)
```text
public static String getFormattedTime(Date date, int index)
```

### `getFormattedDateTime` (line 103)
```text
public static String getFormattedDateTime(Date date)
```

### `getFormattedDateTime` (line 107)
```text
public static String getFormattedDateTime(Date date, int index)
```

### `getDateRange` (line 111)
```text
public static String getDateRange(Context context, Date start, Date end)
```

### `applyDateRange` (line 118)
```text
public static void applyDateRange(TextView textView, Date start, Date end)
```

### `getTimeRange` (line 123)
```text
public static String getTimeRange(Context context, Date start, Date end)
```

### `applyTimeRange` (line 130)
```text
public static void applyTimeRange(TextView textView, Date start, Date end)
```

### `getDateFromSQLDateString` (line 41)
```text
public static Date getDateFromSQLDateString(String date)
```

### `getDateFromSQLDateTimeString` (line 50)
```text
public static Date getDateFromSQLDateTimeString(String dateTime)
```

### `getDateTimeString` (line 59)
```text
public static String getDateTimeString(Date date, String pattern)
```

### `getSQLDateString` (line 64)
```text
public static String getSQLDateString(Date date)
```

### `getSQLDateTimeString` (line 69)
```text
public static String getSQLDateTimeString(Date date)
```

### `getSQLDateTimeString` (line 74)
```text
public static String getSQLDateTimeString(long millis)
```

### `getFilenameDateTimeString` (line 79)
```text
public static String getFilenameDateTimeString(Date date)
```

### `setTime` (line 84)
```text
public static Date setTime(Date date, int hour, int minute, int second, int millis)
```

### `setTime` (line 90)
```text
public static Date setTime(Calendar calendar, int hour, int minute, int second, int millis)
```

### `setDayOfMonth` (line 98)
```text
public static Date setDayOfMonth(Calendar calendar, int day)
```

### `setMonth` (line 103)
```text
public static Date setMonth(Calendar calendar, int month)
```

### `setDayAndMonth` (line 108)
```text
public static Date setDayAndMonth(Calendar calendar, int day, int month)
```

### `getFirstDateOfWeek` (line 114)
```text
public static Date getFirstDateOfWeek(Calendar calendar)
```

### `getFirstDateOfWeek` (line 118)
```text
public static Date getFirstDateOfWeek(Calendar calendar, int firstDayOfWeek)
```

### `getDate` (line 128)
```text
public static Date getDate(int year, int month, int day)
```

### `addDays` (line 134)
```text
public static Date addDays(Calendar calendar, int days)
```

### `addMonths` (line 139)
```text
public static Date addMonths(Calendar calendar, int months)
```

### `addMonthAndDay` (line 144)
```text
public static Date addMonthAndDay(Calendar calendar, int months, int days)
```

### `isBeforeToday` (line 150)
```text
public static boolean isBeforeToday(Date date)
```

### `isBeforeNow` (line 156)
```text
public static boolean isBeforeNow(Date date)
```

### `isAfter` (line 160)
```text
public static boolean isAfter(Date date1, Date date2)
```

### `isAfterEqual` (line 164)
```text
public static boolean isAfterEqual(Date date1, Date date2)
```

### `isBefore` (line 168)
```text
public static boolean isBefore(Date date1, Date date2)
```

### `isBeforeEqual` (line 172)
```text
public static boolean isBeforeEqual(Date date1, Date date2)
```

### `isTheSameDay` (line 176)
```text
public static boolean isTheSameDay(Date start, Date end)
```

### `isTheSameDayAndHour` (line 184)
```text
public static boolean isTheSameDayAndHour(Date start, Date end)
```

### `getDaysBetween` (line 193)
```text
public static int getDaysBetween(Date start, Date end)
```

### `getCalendar` (line 197)
```text
public static Calendar getCalendar(Date date)
```

### `getFixedDateTime` (line 203)
```text
public static DateTime getFixedDateTime(Date date)
```

### `getFixedDate` (line 213)
```text
public static Date getFixedDate(DateTime dateTime)
```

### `setValue` (line 65)
```text
public void setValue(CurrencyUnit currency, long money)
```

### `onSaveInstanceState` (line 77)
```text
public void onSaveInstanceState(Bundle outState)
```

### `clear` (line 83)
```text
public void clear()
```

### `cancel` (line 90)
```text
public void cancel()
```

### `appendOperation` (line 104)
```text
public void appendOperation(Operation operation)
```

### `appendPoint` (line 111)
```text
public void appendPoint()
```

### `appendNumber` (line 123)
```text
public void appendNumber(String digit)
```

### `isPendingOperation` (line 135)
```text
public boolean isPendingOperation()
```

### `execute` (line 139)
```text
public boolean execute(boolean fireCallback)
```

### `getResult` (line 177)
```text
public long getResult()
```

### `onUpdateDisplay` (line 236)
```text
void onUpdateDisplay(String text)
```

### `parse` (line 39)
```text
public static Icon parse(String icon)
```

### `parseAndLoad` (line 57)
```text
public static void parseAndLoad(String encoded, ImageView imageView)
```

### `parseAndLoad` (line 61)
```text
public static void parseAndLoad(String encoded, Icon fallback, ImageView imageView)
```

### `loadInto` (line 65)
```text
public static void loadInto(Icon icon, ImageView imageView)
```

### `loadInto` (line 69)
```text
public static void loadInto(Icon icon, Icon fallback, ImageView imageView)
```

### `initialize` (line 27)
```text
public static void initialize()
```

### `getInstance` (line 79)
```text
public static MoneyFormatter getInstance()
```

### `normalize` (line 83)
```text
public static long normalize(long money, int decimals, int finalDecimals)
```

### `normalize` (line 88)
```text
public static long normalize(long money, int decimalOffset)
```

### `setCurrencyEnabled` (line 105)
```text
public void setCurrencyEnabled(boolean enabled)
```

### `setGroupDigitEnabled` (line 109)
```text
public void setGroupDigitEnabled(boolean enabled)
```

### `setRoundDecimalsEnabled` (line 113)
```text
public void setRoundDecimalsEnabled(boolean enabled)
```

### `setShowSymbolEnabled` (line 117)
```text
public void setShowSymbolEnabled(boolean enabled)
```

### `isCurrencyEnabled` (line 121)
```text
public boolean isCurrencyEnabled()
```

### `isGroupDigitEnabled` (line 125)
```text
public boolean isGroupDigitEnabled()
```

### `isRoundDecimalsEnabled` (line 129)
```text
public boolean isRoundDecimalsEnabled()
```

### `isShowSymbolEnabled` (line 133)
```text
public boolean isShowSymbolEnabled()
```

### `getNotTintedString` (line 137)
```text
public String getNotTintedString(Money money)
```

### `getNotTintedString` (line 156)
```text
public String getNotTintedString(CurrencyUnit currencyUnit, long money)
```

### `getNotTintedString` (line 160)
```text
public String getNotTintedString(CurrencyUnit currencyUnit, long money, CurrencyMode currencyMode)
```

### `getTintedString` (line 195)
```text
public SpannableStringBuilder getTintedString(Money money)
```

### `getTintedString` (line 199)
```text
public SpannableStringBuilder getTintedString(Money money, TintMode tintMode)
```

### `getTintedString` (line 222)
```text
public SpannableString getTintedString(CurrencyUnit currencyUnit, long money)
```

### `getTintedString` (line 226)
```text
public SpannableString getTintedString(CurrencyUnit currencyUnit, long money, CurrencyMode currencyMode)
```

### `applyNotTinted` (line 254)
```text
public void applyNotTinted(TextView textView, Money money)
```

### `applyNotTinted` (line 258)
```text
public void applyNotTinted(TextView textView, CurrencyUnit currencyUnit, long money)
```

### `applyTinted` (line 262)
```text
public void applyTinted(TextView textView, Money money)
```

### `applyTinted` (line 266)
```text
public void applyTinted(TextView textView, CurrencyUnit currencyUnit, long money)
```

### `applyTintedIncome` (line 270)
```text
public void applyTintedIncome(TextView textView, Money money)
```

### `applyTintedIncome` (line 274)
```text
public void applyTintedIncome(TextView textView, CurrencyUnit currencyUnit, long money)
```

### `applyTintedExpense` (line 278)
```text
public void applyTintedExpense(TextView textView, Money money)
```

### `applyTintedExpense` (line 282)
```text
public void applyTintedExpense(TextView textView, CurrencyUnit currencyUnit, long money)
```

### `read` (line 56)
```text
@Override public int read() throws IOException
```

### `read` (line 64)
```text
@Override public int read(@NonNull byte b[]) throws IOException
```

### `read` (line 69)
```text
@Override public int read(@NonNull byte b[], int off, int len) throws IOException
```

### `skip` (line 77)
```text
@Override public long skip(long n) throws IOException
```

### `available` (line 85)
```text
@Override public int available() throws IOException
```

### `close` (line 90)
```text
@Override public void close() throws IOException
```

### `onUploadProgressUpdate` (line 105)
```text
void onUploadProgressUpdate(int percentage)
```

### `write` (line 56)
```text
@Override public void write(int b) throws IOException
```

### `write` (line 63)
```text
@Override public void write(@NonNull byte b[]) throws IOException
```

### `write` (line 68)
```text
@Override public void write(@NonNull byte b[], int off, int len) throws IOException
```

### `flush` (line 75)
```text
@Override public void flush() throws IOException
```

### `close` (line 80)
```text
@Override public void close() throws IOException
```

### `onDownloadProgressUpdate` (line 95)
```text
void onDownloadProgressUpdate(int percentage)
```

### `getHexColor` (line 61)
```text
public static String getHexColor(int color)
```

### `isColorLight` (line 65)
```text
public static boolean isColorLight(int color)
```

### `getBestColor` (line 72)
```text
public static int getBestColor(int color)
```

### `readableFileSize` (line 79)
```text
public static String readableFileSize(long size)
```

### `isAtLeastLollipop` (line 86)
```text
public static boolean isAtLeastLollipop()
```

### `setBackgroundCompat` (line 90)
```text
public static void setBackgroundCompat(View view, Drawable drawable)
```

### `getFileIcon` (line 100)
```text
public static int getFileIcon(String extension)
```

### `getRandomMDColor` (line 126)
```text
public static int getRandomMDColor(int index)
```

### `getRandomMDColor` (line 130)
```text
public static int getRandomMDColor()
```

### `findViewGroupByIds` (line 134)
```text
public static ViewGroup findViewGroupByIds(Activity activity, @IdRes int... resIds)
```

### `findViewGroupByIds` (line 140)
```text
public static ViewGroup findViewGroupByIds(View root, @IdRes int... resIds)
```

### `wrapAsArrayList` (line 150)
```text
public static ArrayList<IFile> wrapAsArrayList(List<IFile> list)
```

## [auto] Types

### `CurrencyManager`

| Field | Type |
|-------|------|
| `initialize` | `method` |
| `invalidateCache` | `method` |
| `getCurrency` | `method` |
| `getCurrencies` | `method` |
| `getExchangeRate` | `method` |
| `getDefaultCurrency` | `method` |
| `getExchangeRateCache` | `method` |

### `DateFormatter`

| Field | Type |
|-------|------|
| `applyDate` | `method` |
| `applyTime` | `method` |
| `getDateFromToday` | `method` |
| `applyDateFromToday` | `method` |
| `applyDateTime` | `method` |
| `getFormattedDate` | `method` |
| `getFormattedDate` | `method` |
| `getFormattedTime` | `method` |
| `getFormattedTime` | `method` |
| `getFormattedDateTime` | `method` |
| _(+5 more)_ | |

### `DateUtils`

| Field | Type |
|-------|------|
| `getDateFromSQLDateString` | `method` |
| `getDateFromSQLDateTimeString` | `method` |
| `getDateTimeString` | `method` |
| `getSQLDateString` | `method` |
| `getSQLDateTimeString` | `method` |
| `getSQLDateTimeString` | `method` |
| `getFilenameDateTimeString` | `method` |
| `setTime` | `method` |
| `setTime` | `method` |
| `setDayOfMonth` | `method` |
| _(+20 more)_ | |

### `EquationSolver`

| Field | Type |
|-------|------|
| `setValue` | `method` |
| `onSaveInstanceState` | `method` |
| `clear` | `method` |
| `cancel` | `method` |
| `appendOperation` | `method` |
| `appendPoint` | `method` |
| `appendNumber` | `method` |
| `isPendingOperation` | `method` |
| `execute` | `method` |
| `getResult` | `method` |

### `Operation`

### `Controller`

| Field | Type |
|-------|------|
| `onUpdateDisplay` | `method` |

### `IconLoader`

| Field | Type |
|-------|------|
| `arse` | `method` |
| `arseAndLoad` | `method` |
| `arseAndLoad` | `method` |
| `loadInto` | `method` |
| `loadInto` | `method` |

### `Logger`

| Field | Type |
|-------|------|
| `initialize` | `method` |

### `MoneyFormatter`

| Field | Type |
|-------|------|
| `getInstance` | `method` |
| `normalize` | `method` |
| `normalize` | `method` |
| `setCurrencyEnabled` | `method` |
| `setGroupDigitEnabled` | `method` |
| `setRoundDecimalsEnabled` | `method` |
| `setShowSymbolEnabled` | `method` |
| `isCurrencyEnabled` | `method` |
| `isGroupDigitEnabled` | `method` |
| `isRoundDecimalsEnabled` | `method` |
| _(+16 more)_ | |

### `CurrencyMode`

### `TintMode`

### `FlowMode`

### `ProgressInputStream`

| Field | Type |
|-------|------|
| `read` | `method` |
| `read` | `method` |
| `read` | `method` |
| `skip` | `method` |
| `available` | `method` |
| `close` | `method` |

### `UploadProgressListener`

| Field | Type |
|-------|------|
| `onUploadProgressUpdate` | `method` |

### `ProgressOutputStream`

| Field | Type |
|-------|------|
| `write` | `method` |
| `write` | `method` |
| `write` | `method` |
| `flush` | `method` |
| `close` | `method` |

### `DownloadProgressListener`

| Field | Type |
|-------|------|
| `onDownloadProgressUpdate` | `method` |

### `Utils`

| Field | Type |
|-------|------|
| `getHexColor` | `method` |
| `isColorLight` | `method` |
| `getBestColor` | `method` |
| `readableFileSize` | `method` |
| `isAtLeastLollipop` | `method` |
| `setBackgroundCompat` | `method` |
| `getFileIcon` | `method` |
| `getRandomMDColor` | `method` |
| `getRandomMDColor` | `method` |
| `findViewGroupByIds` | `method` |
| _(+2 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.utils;
import android.content.ContentResolver;
import android.content.ContentValues;
import android.content.Context;
import android.database.Cursor;
import com.oriondev.moneywallet.model.CurrencyUnit;
import com.oriondev.moneywallet.model.ExchangeRate;
import com.oriondev.moneywallet.storage.cache.ExchangeRateCache;
import com.oriondev.moneywallet.storage.database.Contract;
import com.oriondev.moneywallet.storage.database.DataContentProvider;
// ... +56 more
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