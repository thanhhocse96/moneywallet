<!-- AUTO_START | hash: b9c7a5b6 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/model`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 33

## [auto] Public Functions

### `getId` (line 79)
```text
@Override public long getId()
```

### `setId` (line 84)
```text
public void setId(long id)
```

### `getFile` (line 88)
```text
public String getFile()
```

### `getName` (line 92)
```text
public String getName()
```

### `getType` (line 96)
```text
public String getType()
```

### `getSize` (line 100)
```text
public long getSize()
```

### `getStatus` (line 104)
```text
public Status getStatus()
```

### `setStatus` (line 108)
```text
public void setStatus(Status status, String error)
```

### `createFromParcel` (line 115)
```text
@Override public Attachment createFromParcel(Parcel in)
```

### `newArray` (line 120)
```text
@Override public Attachment[] newArray(int size)
```

### `describeContents` (line 127)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 132)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `equals` (line 148)
```text
@Override public boolean equals(Object object)
```

### `hashCode` (line 153)
```text
@Override public int hashCode()
```

### `getUri` (line 158)
```text
public Uri getUri(Context context)
```

### `getActionViewIntent` (line 165)
```text
public Intent getActionViewIntent(Context context)
```

### `generateFileUID` (line 173)
```text
public static String generateFileUID()
```

### `openAttachment` (line 177)
```text
public static void openAttachment(Context context, Attachment attachment)
```

### `getIconResByType` (line 189)
```text
public static int getIconResByType(String type)
```

### `getIdentifier` (line 40)
```text
public String getIdentifier()
```

### `getIconRes` (line 44)
```text
@DrawableRes public int getIconRes()
```

### `getNameRes` (line 49)
```text
@StringRes public int getNameRes()
```

### `createFromParcel` (line 64)
```text
@Override public Category createFromParcel(Parcel in)
```

### `newArray` (line 69)
```text
@Override public Category[] newArray(int size)
```

### `getId` (line 75)
```text
public long getId()
```

### `getName` (line 79)
```text
public String getName()
```

### `getIcon` (line 83)
```text
public Icon getIcon()
```

### `getType` (line 87)
```text
public Contract.CategoryType getType()
```

### `getTag` (line 91)
```text
public String getTag()
```

### `getDirection` (line 95)
```text
public int getDirection()
```

### `describeContents` (line 121)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 126)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getId` (line 39)
```text
public long getId()
```

### `getName` (line 43)
```text
public String getName()
```

### `getIcon` (line 47)
```text
public Icon getIcon()
```

### `getMoney` (line 51)
```text
public Money getMoney()
```

### `getType` (line 36)
```text
public int getType()
```

### `setType` (line 40)
```text
public void setType(int type)
```

### `getVersionName` (line 44)
```text
public String getVersionName()
```

### `setVersionName` (line 48)
```text
public void setVersionName(String versionName)
```

### `getVersionDate` (line 52)
```text
public String getVersionDate()
```

### `setVersionDate` (line 56)
```text
public void setVersionDate(String versionDate)
```

### `getChangeText` (line 60)
```text
public String getChangeText()
```

### `setChangeText` (line 64)
```text
public void setChangeText(String changeText)
```

### `getChangeType` (line 68)
```text
public int getChangeType()
```

### `setChangeType` (line 72)
```text
public void setChangeType(int changeType)
```

### `versionName` (line 83)
```text
public HeaderBuilder versionName(String versionName)
```

### `versionDate` (line 88)
```text
public HeaderBuilder versionDate(String versionDate)
```

### `build` (line 93)
```text
public ChangeLog build()
```

### `changeText` (line 106)
```text
public ItemBuilder changeText(String changeText)
```

### `build` (line 111)
```text
public ChangeLog build()
```

### `getType` (line 73)
```text
@Override public Type getType()
```

### `apply` (line 84)
```text
@Override public boolean apply(ImageView imageView)
```

### `writeToParcel` (line 91)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getColor` (line 97)
```text
@ColorInt public int getColor()
```

### `getDrawable` (line 102)
```text
@Override public Drawable getDrawable(Context context)
```

### `getDrawable` (line 107)
```text
public Drawable getDrawable()
```

### `createFromParcel` (line 120)
```text
@Override public ColorIcon createFromParcel(Parcel source)
```

### `newArray` (line 125)
```text
@Override public ColorIcon[] newArray(int size)
```

### `getLatitude` (line 45)
```text
public double getLatitude()
```

### `getLongitude` (line 49)
```text
public double getLongitude()
```

### `createFromParcel` (line 55)
```text
@Override public Coordinates createFromParcel(Parcel in)
```

### `newArray` (line 60)
```text
@Override public Coordinates[] newArray(int size)
```

### `describeContents` (line 67)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 72)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `createFromParcel` (line 61)
```text
@Override public CurrencyUnit createFromParcel(Parcel in)
```

### `newArray` (line 66)
```text
@Override public CurrencyUnit[] newArray(int size)
```

### `getIso` (line 73)
```text
public String getIso()
```

### `getName` (line 77)
```text
public String getName()
```

### `getSymbol` (line 81)
```text
public String getSymbol()
```

### `getDecimals` (line 85)
```text
public int getDecimals()
```

### `hasDecimals` (line 89)
```text
public boolean hasDecimals()
```

### `describeContents` (line 93)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 98)
```text
@Override public void writeToParcel(Parcel parcel, int flags)
```

### `equals` (line 106)
```text
@Override public boolean equals(Object obj)
```

### `getCurrencyFlag` (line 111)
```text
@DrawableRes public static int getCurrencyFlag(Context context, String iso)
```

### `getCurrencyDrawable` (line 117)
```text
public static Drawable getCurrencyDrawable(String iso)
```

### `createFromParcel` (line 55)
```text
@Override public Event createFromParcel(Parcel in)
```

### `newArray` (line 60)
```text
@Override public Event[] newArray(int size)
```

### `getId` (line 66)
```text
@Override public long getId()
```

### `getName` (line 71)
```text
public String getName()
```

### `describeContents` (line 75)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 80)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getCurrency1` (line 41)
```text
public CurrencyUnit getCurrency1()
```

### `getCurrency2` (line 45)
```text
public CurrencyUnit getCurrency2()
```

### `getRate` (line 49)
```text
public double getRate()
```

### `getTimestamp` (line 53)
```text
public long getTimestamp()
```

### `getType` (line 35)
```text
public int getType()
```

### `fromType` (line 39)
```text
public static Group fromType(int type)
```

### `getName` (line 29)
```text
String getName()
```

### `getExtension` (line 31)
```text
String getExtension()
```

### `isDirectory` (line 33)
```text
boolean isDirectory()
```

### `getSize` (line 35)
```text
long getSize()
```

### `encodeToString` (line 37)
```text
String encodeToString()
```

### `toString` (line 47)
```text
@Override public String toString()
```

### `get` (line 52)
```text
public static Type get(String type)
```

### `getType` (line 69)
```text
public abstract Type getType()
```

### `getDrawable` (line 73)
```text
public abstract Drawable getDrawable(Context context)
```

### `apply` (line 75)
```text
public abstract boolean apply(ImageView imageView)
```

### `toString` (line 77)
```text
public final String toString()
```

### `getType` (line 89)
```text
public static Type getType(JSONObject jsonObject) throws JSONException
```

### `getDrawableId` (line 93)
```text
public static int getDrawableId(Context context, String resource)
```

### `describeContents` (line 97)
```text
@Override public int describeContents()
```

### `getGroupName` (line 37)
```text
public String getGroupName()
```

### `getGroupIcons` (line 41)
```text
public List<Icon> getGroupIcons()
```

### `size` (line 45)
```text
public int size()
```

### `getId` (line 28)
```text
long getId()
```

### `getName` (line 43)
```text
public String getName()
```

### `getAuthor` (line 47)
```text
public String getAuthor()
```

### `getUrl` (line 51)
```text
public String getUrl()
```

### `getVersion` (line 55)
```text
public String getVersion()
```

### `getCopyright` (line 59)
```text
public String getCopyright()
```

### `getType` (line 63)
```text
public Type getType()
```

### `getTypeName` (line 67)
```text
public String getTypeName()
```

### `createFromParcel` (line 49)
```text
@Override public LocalFile createFromParcel(Parcel in)
```

### `newArray` (line 54)
```text
@Override public LocalFile[] newArray(int size)
```

### `getName` (line 60)
```text
@Override public String getName()
```

### `getExtension` (line 65)
```text
@Override public String getExtension()
```

### `isDirectory` (line 71)
```text
@Override public boolean isDirectory()
```

### `getSize` (line 76)
```text
@Override public long getSize()
```

### `encodeToString` (line 81)
```text
@Override public String encodeToString()
```

### `getFile` (line 86)
```text
public File getFile()
```

### `getLocalPath` (line 90)
```text
public String getLocalPath()
```

### `describeContents` (line 94)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 99)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getValue` (line 40)
```text
public int getValue()
```

### `getValueAsString` (line 44)
```text
public String getValueAsString()
```

### `get` (line 48)
```text
public static LockMode get(int value)
```

### `empty` (line 36)
```text
public static Money empty()
```

### `addMoney` (line 49)
```text
public void addMoney(String currency, long money)
```

### `addMoney` (line 57)
```text
public void addMoney(Money money)
```

### `removeMoney` (line 65)
```text
public void removeMoney(String currency, long money)
```

### `removeMoney` (line 73)
```text
public void removeMoney(Money money)
```

### `getMoney` (line 81)
```text
public long getMoney(String currency)
```

### `getCurrencyMoneys` (line 86)
```text
public Map<String, Long> getCurrencyMoneys()
```

### `getCurrencies` (line 90)
```text
public Set<String> getCurrencies()
```

### `getNumberOfCurrencies` (line 94)
```text
public int getNumberOfCurrencies()
```

### `toString` (line 98)
```text
@Override public String toString()
```

### `parse` (line 110)
```text
public static Money parse(String string)
```

### `getBarData` (line 45)
```text
public BarData getBarData()
```

### `getLineData` (line 49)
```text
public LineData getLineData()
```

### `getRadarData` (line 53)
```text
public RadarData getRadarData()
```

### `getPeriodMoney` (line 57)
```text
public PeriodMoney getPeriodMoney(int index)
```

### `getPeriodCount` (line 61)
```text
public int getPeriodCount()
```

### `createFromParcel` (line 70)
```text
@Override public OverviewSetting createFromParcel(Parcel in)
```

### `newArray` (line 75)
```text
@Override public OverviewSetting[] newArray(int size)
```

### `getStartDate` (line 82)
```text
public Date getStartDate()
```

### `getEndDate` (line 86)
```text
public Date getEndDate()
```

### `getGroupType` (line 90)
```text
public Group getGroupType()
```

### `getType` (line 94)
```text
public Type getType()
```

### `getCashFlow` (line 98)
```text
public CashFlow getCashFlow()
```

### `getCategoryId` (line 102)
```text
public long getCategoryId()
```

### `describeContents` (line 106)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 111)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getL` (line 35)
```text
public L getL()
```

### `getR` (line 39)
```text
public R getR()
```

### `getTotalMoney` (line 42)
```text
public Money getTotalMoney()
```

### `getChartData` (line 46)
```text
public PieData getChartData(int index)
```

### `getChartCount` (line 50)
```text
public int getChartCount()
```

### `getCategory` (line 54)
```text
public CategoryMoney getCategory(int index)
```

### `getCategoryCount` (line 58)
```text
public int getCategoryCount()
```

### `getNetIncomes` (line 43)
```text
public Money getNetIncomes()
```

### `getChartData` (line 47)
```text
public BarData getChartData(int index)
```

### `getChartCurrency` (line 51)
```text
public CurrencyUnit getChartCurrency(int index)
```

### `getChartCount` (line 55)
```text
public int getChartCount()
```

### `getPeriodMoney` (line 59)
```text
public PeriodMoney getPeriodMoney(int index)
```

### `getPeriodCount` (line 63)
```text
public int getPeriodCount()
```

### `addIncome` (line 45)
```text
public void addIncome(String currency, long money)
```

### `addExpense` (line 50)
```text
public void addExpense(String currency, long money)
```

### `getStartDate` (line 55)
```text
public Date getStartDate()
```

### `getEndDate` (line 59)
```text
public Date getEndDate()
```

### `getIncomes` (line 63)
```text
public Money getIncomes()
```

### `getExpenses` (line 67)
```text
public Money getExpenses()
```

### `getNetIncomes` (line 71)
```text
public Money getNetIncomes()
```

### `isTimeRange` (line 75)
```text
public boolean isTimeRange()
```

### `createFromParcel` (line 47)
```text
@Override public Person createFromParcel(Parcel in)
```

### `newArray` (line 52)
```text
@Override public Person[] newArray(int size)
```

### `getId` (line 58)
```text
@Override public long getId()
```

### `getName` (line 63)
```text
public String getName()
```

### `getIcon` (line 67)
```text
public Icon getIcon()
```

### `describeContents` (line 71)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 76)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getId` (line 56)
```text
public long getId()
```

### `getName` (line 60)
```text
public String getName()
```

### `getAddress` (line 64)
```text
public String getAddress()
```

### `hasCoordinates` (line 68)
```text
public boolean hasCoordinates()
```

### `getCoordinates` (line 72)
```text
public Coordinates getCoordinates()
```

### `createFromParcel` (line 94)
```text
@Override public Place createFromParcel(Parcel in)
```

### `newArray` (line 99)
```text
@Override public Place[] newArray(int size)
```

### `describeContents` (line 105)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 110)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `build` (line 75)
```text
public static RecurrenceSetting build(Date startDate, String rule) throws InvalidRecurrenceRuleException
```

### `getType` (line 94)
```text
public int getType()
```

### `getStartDate` (line 109)
```text
public Date getStartDate()
```

### `getOffsetValue` (line 113)
```text
public int getOffsetValue()
```

### `getWeekDays` (line 117)
```text
public boolean[] getWeekDays()
```

### `getMonthDay` (line 155)
```text
public int getMonthDay()
```

### `getEndType` (line 159)
```text
public int getEndType()
```

### `getEndDate` (line 169)
```text
public Date getEndDate()
```

### `getOccurrenceValue` (line 174)
```text
public int getOccurrenceValue()
```

### `getRule` (line 179)
```text
public String getRule()
```

### `createFromParcel` (line 185)
```text
@Override public RecurrenceSetting createFromParcel(Parcel in)
```

### `newArray` (line 190)
```text
@Override public RecurrenceSetting[] newArray(int size)
```

### `describeContents` (line 197)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 202)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `getUserReadableString` (line 208)
```text
public String getUserReadableString(Context context)
```

### `getNextOccurrence` (line 268)
```text
public Date getNextOccurrence(Date lastOccurrence)
```

### `setOffset` (line 293)
```text
public void setOffset(int offset)
```

### `setRepeatWeekDay` (line 297)
```text
public void setRepeatWeekDay(boolean[] weekDays)
```

### `setRepeatSameMonthDay` (line 309)
```text
public void setRepeatSameMonthDay()
```

### `setEndFor` (line 320)
```text
public void setEndFor(int occurrences)
```

### `setEndUntil` (line 324)
```text
public void setEndUntil(Date endDate)
```

### `build` (line 328)
```text
public RecurrenceSetting build()
```

### `createFromParcel` (line 28)
```text
@Override public SAFFile createFromParcel(Parcel in)
```

### `newArray` (line 33)
```text
@Override public SAFFile[] newArray(int size)
```

### `getName` (line 65)
```text
@Override public String getName()
```

### `getExtension` (line 70)
```text
@Override public String getExtension()
```

### `isDirectory` (line 76)
```text
@Override public boolean isDirectory()
```

### `getSize` (line 81)
```text
@Override public long getSize()
```

### `encodeToString` (line 86)
```text
@Override public String encodeToString()
```

### `describeContents` (line 100)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 105)
```text
@Override public void writeToParcel(Parcel dest, int i)
```

### `getUri` (line 113)
```text
public Uri getUri()
```

### `getType` (line 53)
```text
@Override public Type getType()
```

### `getDrawable` (line 63)
```text
@Override public Drawable getDrawable(Context context)
```

### `apply` (line 72)
```text
@Override public boolean apply(ImageView imageView)
```

### `getResource` (line 86)
```text
@DrawableRes public int getResource(Context context)
```

### `writeToParcel` (line 91)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `createFromParcel` (line 98)
```text
@Override public VectorIcon createFromParcel(Parcel source)
```

### `newArray` (line 103)
```text
@Override public VectorIcon[] newArray(int size)
```

### `getId` (line 46)
```text
@Override public long getId()
```

### `getName` (line 51)
```text
public String getName()
```

### `getCurrency` (line 55)
```text
public CurrencyUnit getCurrency()
```

### `createFromParcel` (line 69)
```text
@Override public Wallet createFromParcel(Parcel in)
```

### `newArray` (line 74)
```text
@Override public Wallet[] newArray(int size)
```

### `describeContents` (line 80)
```text
@Override public int describeContents()
```

### `writeToParcel` (line 85)
```text
@Override public void writeToParcel(Parcel dest, int flags)
```

### `withIdentifier` (line 44)
```text
@Override public WalletAccount withIdentifier(long identifier)
```

### `withName` (line 50)
```text
@Override public WalletAccount withName(String name)
```

### `withEmail` (line 56)
```text
@Override public WalletAccount withEmail(String email)
```

### `getEmail` (line 61)
```text
@Override public StringHolder getEmail()
```

### `withIcon` (line 66)
```text
public WalletAccount withIcon(Context context, Icon icon)
```

### `withIcon` (line 76)
```text
@Override public WalletAccount withIcon(Drawable icon)
```

### `withIcon` (line 82)
```text
@Override public WalletAccount withIcon(@DrawableRes int iconRes)
```

### `withIcon` (line 88)
```text
@Override public WalletAccount withIcon(Bitmap iconBitmap)
```

### `withIcon` (line 94)
```text
@Override public WalletAccount withIcon(IIcon icon)
```

### `withIcon` (line 100)
```text
@Override public WalletAccount withIcon(String url)
```

### `withIcon` (line 106)
```text
@Override public WalletAccount withIcon(Uri uri)
```

### `withId` (line 112)
```text
public WalletAccount withId(long id)
```

### `getId` (line 117)
```text
public long getId()
```

### `withMoney` (line 121)
```text
public WalletAccount withMoney(String currency, long money)
```

### `withMoney` (line 126)
```text
public WalletAccount withMoney(Money money)
```

## [auto] Types

### `Attachment`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `setId` | `method` |
| `getFile` | `method` |
| `getName` | `method` |
| `getType` | `method` |
| `getSize` | `method` |
| `getStatus` | `method` |
| `setStatus` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |
| _(+7 more)_ | |

### `Status`

### `BackupService`

| Field | Type |
|-------|------|
| `getIdentifier` | `method` |
| `getIconRes` | `method` |
| `getNameRes` | `method` |

### `Category`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getIcon` | `method` |
| `getType` | `method` |
| `getTag` | `method` |
| `getDirection` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `CategoryMoney`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getIcon` | `method` |
| `getMoney` | `method` |

### `ChangeLog`

| Field | Type |
|-------|------|
| `getType` | `method` |
| `setType` | `method` |
| `getVersionName` | `method` |
| `setVersionName` | `method` |
| `getVersionDate` | `method` |
| `setVersionDate` | `method` |
| `getChangeText` | `method` |
| `setChangeText` | `method` |
| `getChangeType` | `method` |
| `setChangeType` | `method` |

### `HeaderBuilder`

| Field | Type |
|-------|------|
| `versionName` | `method` |
| `versionDate` | `method` |
| `ild` | `method` |

### `ItemBuilder`

| Field | Type |
|-------|------|
| `changeText` | `method` |
| `ild` | `method` |

### `ColorIcon`

| Field | Type |
|-------|------|
| `getType` | `method` |
| `apply` | `method` |
| `writeToParcel` | `method` |
| `getColor` | `method` |
| `getDrawable` | `method` |
| `getDrawable` | `method` |

### `Coordinates`

| Field | Type |
|-------|------|
| `getLatitude` | `method` |
| `getLongitude` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `CurrencyUnit`

| Field | Type |
|-------|------|
| `getIso` | `method` |
| `getName` | `method` |
| `getSymbol` | `method` |
| `getDecimals` | `method` |
| `hasDecimals` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |
| `equals` | `method` |
| `getCurrencyFlag` | `method` |
| `getCurrencyDrawable` | `method` |

### `DataFormat`

### `Event`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `ExchangeRate`

| Field | Type |
|-------|------|
| `getCurrency1` | `method` |
| `getCurrency2` | `method` |
| `getRate` | `method` |
| `getTimestamp` | `method` |

### `Group`

### `IFile`

| Field | Type |
|-------|------|
| `getName` | `method` |
| `getExtension` | `method` |
| `isDirectory` | `method` |
| `getSize` | `method` |
| `encodeToString` | `method` |

### `Icon`

| Field | Type |
|-------|------|
| `getType` | `method` |
| `getDrawable` | `method` |
| `apply` | `method` |
| `toString` | `method` |
| `getType` | `method` |
| `getDrawableId` | `method` |
| `describeContents` | `method` |

### `Type`

### `IconGroup`

| Field | Type |
|-------|------|
| `getGroupName` | `method` |
| `getGroupIcons` | `method` |
| `size` | `method` |

### `Identifiable`

| Field | Type |
|-------|------|
| `getId` | `method` |

### `License`

| Field | Type |
|-------|------|
| `getName` | `method` |
| `getAuthor` | `method` |
| `getUrl` | `method` |
| `getVersion` | `method` |
| `getCopyright` | `method` |
| `getType` | `method` |
| `getTypeName` | `method` |

### `Type`

### `LocalFile`

| Field | Type |
|-------|------|
| `getName` | `method` |
| `getExtension` | `method` |
| `isDirectory` | `method` |
| `getSize` | `method` |
| `encodeToString` | `method` |
| `getFile` | `method` |
| `getLocalPath` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `LockMode`

### `Money`

| Field | Type |
|-------|------|
| `empty` | `method` |
| `addMoney` | `method` |
| `addMoney` | `method` |
| `removeMoney` | `method` |
| `removeMoney` | `method` |
| `getMoney` | `method` |
| `getCurrencyMoneys` | `method` |
| `getCurrencies` | `method` |
| `getNumberOfCurrencies` | `method` |
| `toString` | `method` |
| _(+1 more)_ | |

### `OverviewData`

| Field | Type |
|-------|------|
| `getBarData` | `method` |
| `getLineData` | `method` |
| `getRadarData` | `method` |
| `getPeriodMoney` | `method` |
| `getPeriodCount` | `method` |

### `OverviewSetting`

| Field | Type |
|-------|------|
| `getStartDate` | `method` |
| `getEndDate` | `method` |
| `getGroupType` | `method` |
| `getType` | `method` |
| `getCashFlow` | `method` |
| `getCategoryId` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `Type`

### `CashFlow`

### `Pair`

| Field | Type |
|-------|------|
| `getL` | `method` |
| `getR` | `method` |

### `PeriodDetailFlowData`

| Field | Type |
|-------|------|
| `getTotalMoney` | `method` |
| `getChartData` | `method` |
| `getChartCount` | `method` |
| `getCategory` | `method` |
| `getCategoryCount` | `method` |

### `PeriodDetailSummaryData`

| Field | Type |
|-------|------|
| `getNetIncomes` | `method` |
| `getChartData` | `method` |
| `getChartCurrency` | `method` |
| `getChartCount` | `method` |
| `getPeriodMoney` | `method` |
| `getPeriodCount` | `method` |

### `PeriodMoney`

| Field | Type |
|-------|------|
| `addIncome` | `method` |
| `addExpense` | `method` |
| `getStartDate` | `method` |
| `getEndDate` | `method` |
| `getIncomes` | `method` |
| `getExpenses` | `method` |
| `getNetIncomes` | `method` |
| `isTimeRange` | `method` |

### `Person`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getIcon` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `Place`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getAddress` | `method` |
| `hasCoordinates` | `method` |
| `getCoordinates` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `RecurrenceSetting`

| Field | Type |
|-------|------|
| `ild` | `method` |
| `getType` | `method` |
| `getStartDate` | `method` |
| `getOffsetValue` | `method` |
| `getWeekDays` | `method` |
| `getMonthDay` | `method` |
| `getEndType` | `method` |
| `getEndDate` | `method` |
| `getOccurrenceValue` | `method` |
| `getRule` | `method` |
| _(+4 more)_ | |

### `Builder`

| Field | Type |
|-------|------|
| `setOffset` | `method` |
| `setRepeatWeekDay` | `method` |
| `setRepeatSameMonthDay` | `method` |
| `setEndFor` | `method` |
| `setEndUntil` | `method` |
| `ild` | `method` |

### `SAFFile`

| Field | Type |
|-------|------|
| `getName` | `method` |
| `getExtension` | `method` |
| `isDirectory` | `method` |
| `getSize` | `method` |
| `encodeToString` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |
| `getUri` | `method` |

### `VectorIcon`

| Field | Type |
|-------|------|
| `getType` | `method` |
| `getDrawable` | `method` |
| `apply` | `method` |
| `getResource` | `method` |
| `writeToParcel` | `method` |

### `Wallet`

| Field | Type |
|-------|------|
| `getId` | `method` |
| `getName` | `method` |
| `getCurrency` | `method` |
| `describeContents` | `method` |
| `writeToParcel` | `method` |

### `WalletAccount`

| Field | Type |
|-------|------|
| `withIdentifier` | `method` |
| `withName` | `method` |
| `withEmail` | `method` |
| `getEmail` | `method` |
| `withIcon` | `method` |
| `withIcon` | `method` |
| `withIcon` | `method` |
| `withIcon` | `method` |
| `withIcon` | `method` |
| `withIcon` | `method` |
| _(+5 more)_ | |

## [auto] Key Imports

```
package com.oriondev.moneywallet.model;
import android.content.ActivityNotFoundException;
import android.content.Context;
import android.content.Intent;
import android.net.Uri;
import android.os.Parcel;
import android.os.Parcelable;
import androidx.core.content.FileProvider;
import android.text.TextUtils;
import com.oriondev.moneywallet.R;
// ... +47 more
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