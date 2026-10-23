<!-- AUTO_START | hash: 25821b55 | built: 2026-10-20T15:41 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/picker`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 18

## [auto] Public Functions

### `createPicker` (line 69)
```text
public static AttachmentPicker createPicker(FragmentManager fragmentManager, String tag, ArrayList<Attachment> attachments)
```

### `onCreate` (line 95)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 121)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onAttach` (line 135)
```text
@Override public void onAttach(Context context)
```

### `areAllAttachmentsReady` (line 148)
```text
public boolean areAllAttachmentsReady()
```

### `remove` (line 157)
```text
public void remove(Attachment attachment)
```

### `showPicker` (line 172)
```text
public void showPicker()
```

### `cleanUp` (line 181)
```text
public void cleanUp(boolean rollback)
```

### `getCurrentAttachments` (line 193)
```text
public List<Attachment> getCurrentAttachments()
```

### `onActivityResult` (line 200)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent data)
```

### `addFileFromUri` (line 227)
```text
public void addFileFromUri(@NonNull Uri uri)
```

### `onSaveInstanceState` (line 315)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `onDetach` (line 324)
```text
@Override public void onDetach()
```

### `onAttachmentListChanged` (line 336)
```text
void onAttachmentListChanged(List<Attachment> attachments)
```

### `onReceive` (line 341)
```text
@Override public void onReceive(Context context, Intent intent)
```

### `createPicker` (line 47)
```text
public static BudgetTypePicker createPicker(FragmentManager fragmentManager, String tag, Contract.BudgetType defaultType)
```

### `onAttach` (line 59)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 67)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 91)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 103)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 109)
```text
public boolean isSelected()
```

### `getCurrentType` (line 113)
```text
public Contract.BudgetType getCurrentType()
```

### `showPicker` (line 117)
```text
public void showPicker()
```

### `onDetach` (line 121)
```text
@Override public void onDetach()
```

### `onBudgetTypeSelected` (line 127)
```text
@Override public void onBudgetTypeSelected(Contract.BudgetType budgetType)
```

### `onTypeChanged` (line 135)
```text
void onTypeChanged(String tag, Contract.BudgetType type)
```

### `createPicker` (line 52)
```text
public static CategoryPicker createPicker(FragmentManager fragmentManager, String tag, Category defaultCategory)
```

### `onAttach` (line 64)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 74)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 94)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 110)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 116)
```text
public boolean isSelected()
```

### `setCategory` (line 120)
```text
public void setCategory(Category category)
```

### `getCurrentCategory` (line 125)
```text
public Category getCurrentCategory()
```

### `showPicker` (line 129)
```text
public void showPicker()
```

### `showPicker` (line 133)
```text
public void showPicker(boolean showSubCategories, boolean showSystemCategories)
```

### `showParentPicker` (line 140)
```text
public void showParentPicker(long categoryId, Contract.CategoryType type)
```

### `onActivityResult` (line 144)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent data)
```

### `onDetach` (line 156)
```text
@Override public void onDetach()
```

### `onCategorySelected` (line 162)
```text
@Override public void onCategorySelected(Category category)
```

### `onCategoryChanged` (line 170)
```text
void onCategoryChanged(String tag, Category category)
```

### `createPicker` (line 45)
```text
public static ColorPicker createPicker(FragmentManager fragmentManager, String tag, int color, boolean accentPalette, Controller controller)
```

### `onAttach` (line 66)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 74)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 102)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 118)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `setController` (line 125)
```text
public void setController(Controller controller)
```

### `showPicker` (line 129)
```text
public void showPicker()
```

### `onDetach` (line 133)
```text
@Override public void onDetach()
```

### `onColorSelection` (line 139)
```text
@Override public void onColorSelection(@NonNull ColorChooserDialog dialog, int selectedColor)
```

### `onColorChooserDismissed` (line 145)
```text
@Override public void onColorChooserDismissed(@NonNull ColorChooserDialog dialog)
```

### `onColorChanged` (line 152)
```text
void onColorChanged(String tag, int color, boolean autoFired)
```

### `createPicker` (line 57)
```text
public static CurrencyConverterPicker createPicker(FragmentManager fragmentManager, String tag, CurrencyUnit currencyUnit1, CurrencyUnit currencyUnit2, double defaultRate)
```

### `onAttach` (line 74)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 82)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 111)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 143)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isReady` (line 153)
```text
public boolean isReady()
```

### `setCurrency1` (line 157)
```text
public void setCurrency1(CurrencyUnit currencyUnit)
```

### `setCurrency2` (line 163)
```text
public void setCurrency2(CurrencyUnit currencyUnit)
```

### `showPicker` (line 170)
```text
public void showPicker(long currentMoney)
```

### `convert` (line 174)
```text
public long convert(long money)
```

### `notifyMoneyChanged` (line 182)
```text
public void notifyMoneyChanged()
```

### `onDetach` (line 186)
```text
@Override public void onDetach()
```

### `onExchangeRateChanged` (line 192)
```text
@Override public void onExchangeRateChanged(double exchangeRate)
```

### `onConversionRateChanged` (line 200)
```text
void onConversionRateChanged(String tag, CurrencyUnit currencyUnit1, CurrencyUnit currencyUnit2, Double conversionRate)
```

### `createPicker` (line 49)
```text
public static CurrencyPicker createPicker(FragmentManager fragmentManager, String tag)
```

### `createPicker` (line 53)
```text
public static CurrencyPicker createPicker(FragmentManager fragmentManager, String tag, CurrencyUnit defaultCurrency)
```

### `onAttach` (line 65)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 73)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 88)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 100)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `setCurrency` (line 106)
```text
public void setCurrency(CurrencyUnit currency)
```

### `isSelected` (line 111)
```text
public boolean isSelected()
```

### `getCurrentCurrency` (line 115)
```text
public CurrencyUnit getCurrentCurrency()
```

### `showPicker` (line 119)
```text
public void showPicker()
```

### `onDetach` (line 125)
```text
@Override public void onDetach()
```

### `onActivityResult` (line 131)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent intent)
```

### `onCurrencyChanged` (line 145)
```text
void onCurrencyChanged(String tag, CurrencyUnit currency)
```

### `createPicker` (line 51)
```text
public static DateTimePicker createPicker(FragmentManager fragmentManager, String tag, Date defaultDate)
```

### `onAttach` (line 67)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 77)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 100)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 112)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 118)
```text
public boolean isSelected()
```

### `getCurrentDateTime` (line 122)
```text
public Date getCurrentDateTime()
```

### `setCurrentDateTime` (line 126)
```text
public void setCurrentDateTime(Date dateTime)
```

### `showDatePicker` (line 140)
```text
public void showDatePicker()
```

### `showTimePicker` (line 154)
```text
public void showTimePicker()
```

### `onDetach` (line 164)
```text
@Override public void onDetach()
```

### `onDateSet` (line 170)
```text
@Override public void onDateSet(DatePickerDialog dialog, int year, int monthOfYear, int dayOfMonth)
```

### `onTimeSet` (line 179)
```text
@Override public void onTimeSet(ViewGroup viewGroup, int hourOfDay, int minute)
```

### `onDateTimeChanged` (line 188)
```text
void onDateTimeChanged(String tag, Date date)
```

### `createPicker` (line 49)
```text
public static EventPicker createPicker(FragmentManager fragmentManager, String tag, Event defaultEvent)
```

### `onAttach` (line 61)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 69)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 87)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 103)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 109)
```text
public boolean isSelected()
```

### `setCurrentEvent` (line 113)
```text
public void setCurrentEvent(Event event)
```

### `getCurrentEvent` (line 118)
```text
public Event getCurrentEvent()
```

### `showPicker` (line 122)
```text
public void showPicker(Date filterDate)
```

### `onDetach` (line 126)
```text
@Override public void onDetach()
```

### `onEventSelected` (line 132)
```text
@Override public void onEventSelected(Event event)
```

### `onEventChanged` (line 140)
```text
void onEventChanged(String tag, Event event)
```

### `createPicker` (line 25)
```text
public static ExportColumnsPicker createPicker(FragmentManager fragmentManager, String tag)
```

### `onAttach` (line 34)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 42)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 61)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 74)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `getCurrentServiceColumns` (line 80)
```text
public String[] getCurrentServiceColumns()
```

### `showPicker` (line 84)
```text
public void showPicker()
```

### `onDetach` (line 88)
```text
@Override public void onDetach()
```

### `onExportColumnsSelected` (line 94)
```text
@Override public void onExportColumnsSelected(Integer[] indices)
```

### `onExportColumnsChanged` (line 102)
```text
void onExportColumnsChanged(String tag, String[] columns)
```

### `createPicker` (line 68)
```text
public static IconPicker createPicker(FragmentManager fragmentManager, String tag)
```

### `createPicker` (line 72)
```text
public static IconPicker createPicker(FragmentManager fragmentManager, String tag, Icon defaultIcon)
```

### `onAttach` (line 84)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 92)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 119)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 131)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `listenOn` (line 138)
```text
public void listenOn(EditText editText)
```

### `getColorIconString` (line 164)
```text
public static String getColorIconString(String source)
```

### `getCurrentIcon` (line 178)
```text
public Icon getCurrentIcon()
```

### `setCurrentIcon` (line 182)
```text
public void setCurrentIcon(Icon icon)
```

### `showPicker` (line 194)
```text
public void showPicker()
```

### `onDetach` (line 272)
```text
@Override public void onDetach()
```

### `onColorSelection` (line 278)
```text
@Override public void onColorSelection(@NonNull ColorChooserDialog dialog, int selectedColor)
```

### `onColorChooserDismissed` (line 288)
```text
@Override public void onColorChooserDismissed(@NonNull ColorChooserDialog dialog)
```

### `onActivityResult` (line 294)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent intent)
```

### `onIconChanged` (line 308)
```text
void onIconChanged(String tag, Icon icon)
```

### `createPicker` (line 45)
```text
public static ImportExportFormatPicker createPicker(FragmentManager fragmentManager, String tag)
```

### `onAttach` (line 54)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 62)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 81)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 93)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 99)
```text
public boolean isSelected()
```

### `setCurrentFormat` (line 103)
```text
public void setCurrentFormat(DataFormat dataFormat)
```

### `getCurrentFormat` (line 108)
```text
public DataFormat getCurrentFormat()
```

### `showPicker` (line 112)
```text
public void showPicker(DataFormat[] dataFormats)
```

### `onDetach` (line 122)
```text
@Override public void onDetach()
```

### `onDataFormatSelected` (line 128)
```text
@Override public void onDataFormatSelected(DataFormat dataFormat)
```

### `onFormatChanged` (line 136)
```text
void onFormatChanged(String tag, DataFormat format)
```

### `createPicker` (line 60)
```text
public static LocalFilePicker createPicker(FragmentManager fragmentManager, String tag, int mode)
```

### `onAttach` (line 72)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 80)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 97)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 109)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 116)
```text
public boolean isSelected()
```

### `getCurrentFile` (line 120)
```text
public LocalFile getCurrentFile()
```

### `showPicker` (line 124)
```text
public void showPicker()
```

### `onDetach` (line 155)
```text
@Override public void onDetach()
```

### `onActivityResult` (line 161)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent intent)
```

### `onRequestPermissionsResult` (line 173)
```text
@Override public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults)
```

### `onLocalFileChanged` (line 185)
```text
void onLocalFileChanged(String tag, int mode, LocalFile localFile)
```

### `createPicker` (line 52)
```text
public static MoneyPicker createPicker(FragmentManager fragmentManager, String tag, CurrencyUnit currency, long money)
```

### `onAttach` (line 65)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 73)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 91)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 103)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `setCurrency` (line 110)
```text
public void setCurrency(CurrencyUnit currency)
```

### `setMoney` (line 115)
```text
public void setMoney(long money)
```

### `setCurrencyAndMoney` (line 120)
```text
public void setCurrencyAndMoney(CurrencyUnit currency, long money)
```

### `getCurrentCurrency` (line 126)
```text
public CurrencyUnit getCurrentCurrency()
```

### `getCurrentMoney` (line 130)
```text
public long getCurrentMoney()
```

### `showPicker` (line 134)
```text
public void showPicker()
```

### `onActivityResult` (line 163)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent data)
```

### `onDetach` (line 175)
```text
@Override public void onDetach()
```

### `onMoneyChanged` (line 183)
```text
void onMoneyChanged(String tag, CurrencyUnit currency, long money)
```

### `createPicker` (line 51)
```text
public static OverviewSettingPicker createPicker(FragmentManager fragmentManager, String tag)
```

### `onAttach` (line 60)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 70)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 134)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 140)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `getCurrentSettings` (line 152)
```text
public OverviewSetting getCurrentSettings()
```

### `showPicker` (line 160)
```text
public void showPicker()
```

### `onDetach` (line 164)
```text
@Override public void onDetach()
```

### `onOverviewSettingChanged` (line 170)
```text
@Override public void onOverviewSettingChanged(OverviewSetting overviewSetting)
```

### `onOverviewSettingChanged` (line 178)
```text
void onOverviewSettingChanged(String tag, OverviewSetting overviewSetting)
```

### `createPicker` (line 47)
```text
public static PersonPicker createPicker(FragmentManager fragmentManager, String tag, Person[] defaultPeople)
```

### `onAttach` (line 59)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 67)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 85)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 101)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 107)
```text
public boolean isSelected()
```

### `setPeople` (line 111)
```text
public void setPeople(Person[] people)
```

### `getCurrentPeople` (line 116)
```text
public Person[] getCurrentPeople()
```

### `showPicker` (line 120)
```text
public void showPicker()
```

### `onDetach` (line 124)
```text
@Override public void onDetach()
```

### `onPeopleSelected` (line 130)
```text
@Override public void onPeopleSelected(Person[] people)
```

### `onPeopleChanged` (line 138)
```text
void onPeopleChanged(String tag, Person[] people)
```

### `createPicker` (line 48)
```text
public static PlacePicker createPicker(FragmentManager fragmentManager, String tag, Place defaultPlace)
```

### `onAttach` (line 60)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 68)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 86)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 102)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 108)
```text
public boolean isSelected()
```

### `setCurrentPlace` (line 112)
```text
public void setCurrentPlace(Place place)
```

### `getCurrentPlace` (line 117)
```text
public Place getCurrentPlace()
```

### `showPicker` (line 121)
```text
public void showPicker()
```

### `onDetach` (line 125)
```text
@Override public void onDetach()
```

### `onPlaceSelected` (line 131)
```text
@Override public void onPlaceSelected(Place place)
```

### `onPlaceChanged` (line 139)
```text
void onPlaceChanged(String tag, Place place)
```

### `createPicker` (line 48)
```text
public static RecurrencePicker createPicker(FragmentManager fragmentManager, String tag, RecurrenceSetting recurrenceSetting)
```

### `onAttach` (line 60)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 70)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 90)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 96)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `getCurrentSettings` (line 108)
```text
public RecurrenceSetting getCurrentSettings()
```

### `showPicker` (line 116)
```text
public void showPicker()
```

### `onDetach` (line 120)
```text
@Override public void onDetach()
```

### `onRecurrenceSettingChanged` (line 126)
```text
@Override public void onRecurrenceSettingChanged(RecurrenceSetting recurrenceSetting)
```

### `onRecurrenceSettingChanged` (line 134)
```text
void onRecurrenceSettingChanged(String tag, RecurrenceSetting recurrenceSetting)
```

### `createPicker` (line 53)
```text
public static WalletPicker createPicker(FragmentManager fragmentManager, String tag, Wallet defaultWallet)
```

### `createPicker` (line 66)
```text
public static WalletPicker createPicker(FragmentManager fragmentManager, String tag, Wallet[] defaultWallets)
```

### `onAttach` (line 79)
```text
@Override public void onAttach(Context context)
```

### `onCreate` (line 90)
```text
@Override public void onCreate(@Nullable Bundle savedInstanceState)
```

### `onActivityCreated` (line 131)
```text
@Override public void onActivityCreated(@Nullable Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 153)
```text
@Override public void onSaveInstanceState(@NonNull Bundle outState)
```

### `isSelected` (line 164)
```text
public boolean isSelected()
```

### `getCurrentWallet` (line 168)
```text
public Wallet getCurrentWallet()
```

### `getCurrentWallets` (line 172)
```text
public Wallet[] getCurrentWallets()
```

### `showSingleWalletPicker` (line 176)
```text
public void showSingleWalletPicker()
```

### `showMultiWalletPicker` (line 180)
```text
public void showMultiWalletPicker()
```

### `onDetach` (line 184)
```text
@Override public void onDetach()
```

### `onWalletSelected` (line 191)
```text
@Override public void onWalletSelected(Wallet wallet)
```

### `onWalletsSelected` (line 197)
```text
@Override public void onWalletsSelected(Wallet[] wallets)
```

### `onWalletChanged` (line 205)
```text
void onWalletChanged(String tag, Wallet wallet)
```

### `onWalletListChanged` (line 210)
```text
void onWalletListChanged(String tag, Wallet[] wallets)
```

## [auto] Types

### `AttachmentPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onAttach` | `method` |
| `areAllAttachmentsReady` | `method` |
| `remove` | `method` |
| `showPicker` | `method` |
| `cleanUp` | `method` |
| `getCurrentAttachments` | `method` |
| `onActivityResult` | `method` |
| _(+3 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onAttachmentListChanged` | `method` |

### `BudgetTypePicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `getCurrentType` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| `onBudgetTypeSelected` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onTypeChanged` | `method` |

### `CategoryPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `setCategory` | `method` |
| `getCurrentCategory` | `method` |
| `showPicker` | `method` |
| `showPicker` | `method` |
| _(+4 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onCategoryChanged` | `method` |

### `ColorPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `setController` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| `onColorSelection` | `method` |
| `onColorChooserDismissed` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onColorChanged` | `method` |

### `CurrencyConverterPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isReady` | `method` |
| `setCurrency1` | `method` |
| `setCurrency2` | `method` |
| `showPicker` | `method` |
| `convert` | `method` |
| _(+3 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onConversionRateChanged` | `method` |

### `CurrencyPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `setCurrency` | `method` |
| `isSelected` | `method` |
| `getCurrentCurrency` | `method` |
| `showPicker` | `method` |
| _(+2 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onCurrencyChanged` | `method` |

### `DateTimePicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `getCurrentDateTime` | `method` |
| `setCurrentDateTime` | `method` |
| `showDatePicker` | `method` |
| `showTimePicker` | `method` |
| _(+3 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onDateTimeChanged` | `method` |

### `EventPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `setCurrentEvent` | `method` |
| `getCurrentEvent` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| _(+1 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onEventChanged` | `method` |

### `ExportColumnsPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `getCurrentServiceColumns` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| `onExportColumnsSelected` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onExportColumnsChanged` | `method` |

### `IconPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `listenOn` | `method` |
| `getColorIconString` | `method` |
| `getCurrentIcon` | `method` |
| `setCurrentIcon` | `method` |
| _(+5 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onIconChanged` | `method` |

### `ImportExportFormatPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `setCurrentFormat` | `method` |
| `getCurrentFormat` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| _(+1 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onFormatChanged` | `method` |

### `LocalFilePicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `getCurrentFile` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| `onActivityResult` | `method` |
| _(+1 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onLocalFileChanged` | `method` |

### `MoneyPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `setCurrency` | `method` |
| `setMoney` | `method` |
| `setCurrencyAndMoney` | `method` |
| `getCurrentCurrency` | `method` |
| `getCurrentMoney` | `method` |
| _(+3 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onMoneyChanged` | `method` |

### `OverviewSettingPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `getCurrentSettings` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| `onOverviewSettingChanged` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onOverviewSettingChanged` | `method` |

### `PersonPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `setPeople` | `method` |
| `getCurrentPeople` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| _(+1 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onPeopleChanged` | `method` |

### `PlacePicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `setCurrentPlace` | `method` |
| `getCurrentPlace` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| _(+1 more)_ | |

### `Controller`

| Field | Type |
|-------|------|
| `onPlaceChanged` | `method` |

### `RecurrencePicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `getCurrentSettings` | `method` |
| `showPicker` | `method` |
| `onDetach` | `method` |
| `onRecurrenceSettingChanged` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onRecurrenceSettingChanged` | `method` |

### `WalletPicker`

| Field | Type |
|-------|------|
| `createPicker` | `method` |
| `createPicker` | `method` |
| `onAttach` | `method` |
| `onCreate` | `method` |
| `onActivityCreated` | `method` |
| `onSaveInstanceState` | `method` |
| `isSelected` | `method` |
| `getCurrentWallet` | `method` |
| `getCurrentWallets` | `method` |
| `showSingleWalletPicker` | `method` |
| _(+4 more)_ | |

### `SingleWalletController`

| Field | Type |
|-------|------|
| `onWalletChanged` | `method` |

### `MultiWalletController`

| Field | Type |
|-------|------|
| `onWalletListChanged` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.picker;
import android.Manifest;
import android.app.Activity;
import android.content.BroadcastReceiver;
import android.content.ClipData;
import android.content.ContentResolver;
import android.content.Context;
import android.content.Intent;
import android.content.IntentFilter;
import android.content.pm.PackageManager;
// ... +77 more
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