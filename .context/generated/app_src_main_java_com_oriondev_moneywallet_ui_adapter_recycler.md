<!-- AUTO_START | hash: 9a392a19 | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/adapter/recycler`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 34

## [auto] Public Functions

### `isDataValid` (line 59)
```text
public boolean isDataValid()
```

### `getCursor` (line 63)
```text
public Cursor getCursor()
```

### `getItemCount` (line 67)
```text
@Override public int getItemCount()
```

### `getItemId` (line 75)
```text
@Override public long getItemId(int position)
```

### `setHasStableIds` (line 90)
```text
@Override public void setHasStableIds(boolean hasStableIds)
```

### `onBindViewHolder` (line 95)
```text
@Override public void onBindViewHolder(@NonNull VH holder, int position)
```

### `onBindViewHolder` (line 106)
```text
public abstract void onBindViewHolder(VH holder, Cursor cursor)
```

### `changeCursor` (line 108)
```text
public void changeCursor(Cursor cursor)
```

### `swapCursor` (line 115)
```text
public Cursor swapCursor(Cursor newCursor)
```

### `setFileList` (line 57)
```text
public void setFileList(List<IFile> fileList, boolean canNavigateBack)
```

### `addFileToList` (line 66)
```text
public void addFileToList(IFile file)
```

### `onCreateViewHolder` (line 77)
```text
@NonNull @Override public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 85)
```text
@Override public void onBindViewHolder(@NonNull BackupFileAdapter.ViewHolder holder, int position)
```

### `getItemCount` (line 114)
```text
@Override public int getItemCount()
```

### `compare` (line 119)
```text
@Override public int compare(IFile file1, IFile file2)
```

### `navigateBack` (line 169)
```text
void navigateBack()
```

### `onFileClick` (line 171)
```text
void onFileClick(IFile file)
```

### `onCreateViewHolder` (line 49)
```text
@NonNull @Override public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 57)
```text
@Override public void onBindViewHolder(@NonNull ViewHolder holder, int position)
```

### `getItemCount` (line 64)
```text
@Override public int getItemCount()
```

### `onBackupServiceClick` (line 91)
```text
void onBackupServiceClick(BackupService service)
```

### `onBindViewHolder` (line 85)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 129)
```text
@NonNull @Override public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onBudgetClick` (line 176)
```text
void onBudgetClick(long id)
```

### `onCreateViewHolder` (line 50)
```text
@NonNull @Override public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 58)
```text
@Override public void onBindViewHolder(@NonNull ViewHolder holder, int position)
```

### `getItemCount` (line 79)
```text
@Override public int getItemCount()
```

### `onBudgetTypeSelected` (line 108)
```text
void onBudgetTypeSelected(Contract.BudgetType budgetType)
```

### `isBudgetTypeSelected` (line 110)
```text
boolean isBudgetTypeSelected(Contract.BudgetType budgetType)
```

### `onBindViewHolder` (line 65)
```text
@Override public void onBindViewHolder(CategoryViewHolder holder, Cursor cursor)
```

### `getItemViewType` (line 87)
```text
@Override public int getItemViewType(int position)
```

### `onCreateViewHolder` (line 93)
```text
@NonNull @Override public CategoryViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onCategoryClick` (line 133)
```text
void onCategoryClick(long id)
```

### `onBindViewHolder` (line 66)
```text
@Override public void onBindViewHolder(@NonNull CategoryViewHolder holder, int position)
```

### `onBindViewHolder` (line 73)
```text
@Override public void onBindViewHolder(CategoryViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 80)
```text
@NonNull @Override public CategoryViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `getItemId` (line 88)
```text
@Override public long getItemId(int position)
```

### `swapCursor` (line 96)
```text
@Override public Cursor swapCursor(Cursor newCursor)
```

### `moveItem` (line 108)
```text
public boolean moveItem(int from, int to)
```

### `getSortedCategoryIds` (line 117)
```text
public List<Long> getSortedCategoryIds()
```

### `onCategoryDragStarted` (line 155)
```text
void onCategoryDragStarted(RecyclerView.ViewHolder viewHolder)
```

### `onCreateViewHolder` (line 47)
```text
@Override public RecyclerView.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `getItemViewType` (line 60)
```text
@Override public int getItemViewType(int position)
```

### `onBindViewHolder` (line 65)
```text
@Override public void onBindViewHolder(RecyclerView.ViewHolder holder, int position)
```

### `setChangeLogs` (line 88)
```text
public void setChangeLogs(List<ChangeLog> changeLogList)
```

### `getItemCount` (line 93)
```text
@Override public int getItemCount()
```

### `onBindViewHolder` (line 65)
```text
@Override public void onBindViewHolder(CurrencyViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 88)
```text
@NonNull @Override public CurrencyViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onCurrencyClick` (line 129)
```text
void onCurrencyClick(String iso)
```

### `onCurrencyFavourite` (line 131)
```text
void onCurrencyFavourite(String iso, boolean newValue)
```

### `onCreateViewHolder` (line 27)
```text
@NonNull @Override public DataFormatSelectorAdapter.ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 35)
```text
@Override public void onBindViewHolder(@NonNull DataFormatSelectorAdapter.ViewHolder holder, int position)
```

### `getItemCount` (line 56)
```text
@Override public int getItemCount()
```

### `onDataFormatSelected` (line 85)
```text
void onDataFormatSelected(DataFormat dataFormat)
```

### `isDataFormatSelected` (line 87)
```text
boolean isDataFormatSelected(DataFormat dataFormat)
```

### `onBindViewHolder` (line 96)
```text
@Override public void onBindViewHolder(RecyclerView.ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 191)
```text
@Override public RecyclerView.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `getItemViewType` (line 205)
```text
@Override public int getItemViewType(int position)
```

### `onDebtClick` (line 275)
```text
void onDebtClick(long id)
```

### `onPayClick` (line 277)
```text
void onPayClick(long id)
```

### `onReceiveClick` (line 279)
```text
void onReceiveClick(long id)
```

### `onBindViewHolder` (line 72)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 91)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onEventClick` (line 127)
```text
void onEventClick(long id)
```

### `onBindViewHolder` (line 68)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 79)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onEventClick` (line 122)
```text
void onEventClick(Event event)
```

### `isEventSelected` (line 124)
```text
boolean isEventSelected(long id)
```

### `onCreateViewHolder` (line 56)
```text
@Override public RecyclerView.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 68)
```text
@Override public void onBindViewHolder(RecyclerView.ViewHolder holder, int position)
```

### `getItemCount` (line 77)
```text
@Override public int getItemCount()
```

### `getItemViewType` (line 82)
```text
@Override public int getItemViewType(int position)
```

### `setIconGroups` (line 87)
```text
public void setIconGroups(List<IconGroup> iconGroups)
```

### `isHeader` (line 101)
```text
public boolean isHeader(int position)
```

### `onIconClick` (line 162)
```text
void onIconClick(Icon icon)
```

### `setLicenses` (line 45)
```text
public void setLicenses(List<License> licenses)
```

### `onCreateViewHolder` (line 50)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 57)
```text
@Override public void onBindViewHolder(ViewHolder holder, int position)
```

### `getItemCount` (line 64)
```text
@Override public int getItemCount()
```

### `onClick` (line 81)
```text
@Override public void onClick(View v)
```

### `onLicenseClick` (line 91)
```text
void onLicenseClick(License license)
```

### `onCreateViewHolder` (line 50)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 55)
```text
@Override public void onBindViewHolder(ViewHolder holder, int position)
```

### `getItemCount` (line 63)
```text
@Override public int getItemCount()
```

### `setData` (line 68)
```text
public void setData(OverviewData data)
```

### `onPeriodClick` (line 100)
```text
void onPeriodClick(PeriodMoney periodMoney)
```

### `onBindViewHolder` (line 62)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 71)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onCategorySelected` (line 111)
```text
void onCategorySelected(Category category)
```

### `isCategorySelected` (line 113)
```text
boolean isCategorySelected(long id)
```

### `onBindViewHolder` (line 60)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 69)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onPersonSelected` (line 108)
```text
void onPersonSelected(Person person)
```

### `isPersonSelected` (line 110)
```text
boolean isPersonSelected(long id)
```

### `onCreateViewHolder` (line 52)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 57)
```text
@Override public void onBindViewHolder(ViewHolder holder, int position)
```

### `getItemCount` (line 69)
```text
@Override public int getItemCount()
```

### `setData` (line 74)
```text
public void setData(PeriodDetailFlowData data)
```

### `onCategoryClick` (line 107)
```text
void onCategoryClick(long id)
```

### `onCreateViewHolder` (line 50)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 55)
```text
@Override public void onBindViewHolder(ViewHolder holder, int position)
```

### `getItemCount` (line 67)
```text
@Override public int getItemCount()
```

### `setData` (line 72)
```text
public void setData(PeriodDetailSummaryData data)
```

### `onPeriodClick` (line 104)
```text
void onPeriodClick(PeriodMoney periodMoney)
```

### `onBindViewHolder` (line 59)
```text
@Override public void onBindViewHolder(PersonCursorAdapter.ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 66)
```text
@Override public PersonCursorAdapter.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onPersonClick` (line 98)
```text
void onPersonClick(long id)
```

### `onBindViewHolder` (line 62)
```text
@Override public void onBindViewHolder(PlaceCursorAdapter.ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 75)
```text
@Override public PlaceCursorAdapter.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onPlaceClick` (line 109)
```text
void onPlaceClick(long id)
```

### `onBindViewHolder` (line 67)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 82)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onPlaceSelected` (line 126)
```text
void onPlaceSelected(Place place)
```

### `isPlaceSelected` (line 128)
```text
boolean isPlaceSelected(long id)
```

### `onBindViewHolder` (line 79)
```text
@Override public void onBindViewHolder(RecurrentTransactionViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 100)
```text
@NonNull @Override public RecurrentTransactionViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onRecurrentTransactionClick` (line 139)
```text
void onRecurrentTransactionClick(long id)
```

### `onBindViewHolder` (line 78)
```text
@Override public void onBindViewHolder(RecurrentTransferViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 97)
```text
@NonNull @Override public RecurrentTransferViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onRecurrentTransferClick` (line 136)
```text
void onRecurrentTransferClick(long id)
```

### `onBindViewHolder` (line 77)
```text
@Override public void onBindViewHolder(SavingCursorAdapter.ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 109)
```text
@Override public SavingCursorAdapter.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onSavingClick` (line 173)
```text
void onSavingClick(long id)
```

### `onWithdrawEverything` (line 175)
```text
void onWithdrawEverything(long id)
```

### `onWithdraw` (line 177)
```text
void onWithdraw(long id)
```

### `onDeposit` (line 179)
```text
void onDeposit(long id)
```

### `addCategory` (line 49)
```text
public void addCategory(int id, @DrawableRes int icon, @StringRes int primaryText, @StringRes int secondaryText)
```

### `onCreateViewHolder` (line 53)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 60)
```text
@Override public void onBindViewHolder(ViewHolder holder, int position)
```

### `getItemCount` (line 68)
```text
@Override public int getItemCount()
```

### `onClick` (line 87)
```text
@Override public void onClick(View view)
```

### `onSettingCategoryClick` (line 113)
```text
void onSettingCategoryClick(int id)
```

### `onBindViewHolder` (line 91)
```text
@Override public void onBindViewHolder(RecyclerView.ViewHolder viewHolder, Cursor cursor)
```

### `onCreateViewHolder` (line 124)
```text
@Override public RecyclerView.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `getItemViewType` (line 138)
```text
@Override public int getItemViewType(int position)
```

### `onClick` (line 159)
```text
@Override public void onClick(View v)
```

### `onHeaderClick` (line 203)
```text
void onHeaderClick(Date startDate, Date endDate)
```

### `onTransactionClick` (line 205)
```text
void onTransactionClick(long id)
```

### `onBindViewHolder` (line 75)
```text
@Override public void onBindViewHolder(TransactionModelViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 96)
```text
@Override public TransactionModelViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onModelClick` (line 145)
```text
void onModelClick(long id)
```

### `onModelAddClick` (line 147)
```text
void onModelAddClick(long id)
```

### `onModelEditClick` (line 149)
```text
void onModelEditClick(long id)
```

### `onBindViewHolder` (line 97)
```text
@Override public void onBindViewHolder(RecyclerView.ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 126)
```text
@Override public RecyclerView.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `getItemViewType` (line 140)
```text
@Override public int getItemViewType(int position)
```

### `onClick` (line 157)
```text
@Override public void onClick(View v)
```

### `onHeaderClick` (line 196)
```text
void onHeaderClick()
```

### `onTransferClick` (line 198)
```text
void onTransferClick(long id)
```

### `onBindViewHolder` (line 76)
```text
@Override public void onBindViewHolder(TransferModelViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 96)
```text
@NonNull @Override public TransferModelViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `onModelClick` (line 150)
```text
void onModelClick(long id)
```

### `onModelAddClick` (line 152)
```text
void onModelAddClick(long id)
```

### `onModelEditClick` (line 154)
```text
void onModelEditClick(long id)
```

### `onCreateViewHolder` (line 72)
```text
@Override public WalletViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onBindViewHolder` (line 79)
```text
@Override public void onBindViewHolder(WalletViewHolder holder, Cursor cursor)
```

### `onWalletClick` (line 115)
```text
void onWalletClick(long id)
```

### `onBindViewHolder` (line 71)
```text
@Override public void onBindViewHolder(ViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 85)
```text
@Override public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType)
```

### `onClick` (line 108)
```text
@Override public void onClick(View v)
```

### `onWalletClick` (line 129)
```text
void onWalletClick(Wallet wallet)
```

### `isWalletSelected` (line 131)
```text
boolean isWalletSelected(long id)
```

### `onBindViewHolder` (line 66)
```text
@Override public void onBindViewHolder(@NonNull WalletViewHolder holder, int position)
```

### `onBindViewHolder` (line 73)
```text
@Override public void onBindViewHolder(WalletViewHolder holder, Cursor cursor)
```

### `onCreateViewHolder` (line 80)
```text
@NonNull @Override public WalletViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType)
```

### `getItemId` (line 88)
```text
@Override public long getItemId(int position)
```

### `swapCursor` (line 96)
```text
@Override public Cursor swapCursor(Cursor newCursor)
```

### `moveItem` (line 108)
```text
public boolean moveItem(int from, int to)
```

### `getSortedCategoryIds` (line 117)
```text
public List<Long> getSortedCategoryIds()
```

### `onWalletDragStarted` (line 155)
```text
void onWalletDragStarted(RecyclerView.ViewHolder viewHolder)
```

## [auto] Types

### `AbstractCursorAdapter`

| Field | Type |
|-------|------|
| `isDataValid` | `method` |
| `getCursor` | `method` |
| `getItemCount` | `method` |
| `getItemId` | `method` |
| `setHasStableIds` | `method` |
| `onBindViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `changeCursor` | `method` |
| `swapCursor` | `method` |

### `BackupFileAdapter`

| Field | Type |
|-------|------|
| `setFileList` | `method` |
| `addFileToList` | `method` |
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |
| `compare` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `navigateBack` | `method` |
| `onFileClick` | `method` |

### `BackupServiceAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onBackupServiceClick` | `method` |

### `BudgetCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onBudgetClick` | `method` |

### `BudgetTypeSelectorAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onBudgetTypeSelected` | `method` |
| `isBudgetTypeSelected` | `method` |

### `CategoryCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `getItemViewType` | `method` |
| `onCreateViewHolder` | `method` |

### `CategoryActionListener`

| Field | Type |
|-------|------|
| `onCategoryClick` | `method` |

### `CategorySortCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |
| `getItemId` | `method` |
| `swapCursor` | `method` |
| `moveItem` | `method` |
| `getSortedCategoryIds` | `method` |

### `CategorySortListener`

| Field | Type |
|-------|------|
| `onCategoryDragStarted` | `method` |

### `ChangeLogAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `getItemViewType` | `method` |
| `onBindViewHolder` | `method` |
| `setChangeLogs` | `method` |
| `getItemCount` | `method` |

### `CurrencyCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `CurrencyActionListener`

| Field | Type |
|-------|------|
| `onCurrencyClick` | `method` |
| `onCurrencyFavourite` | `method` |

### `DataFormatSelectorAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onDataFormatSelected` | `method` |
| `isDataFormatSelected` | `method` |

### `DebtCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |
| `getItemViewType` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onDebtClick` | `method` |
| `onPayClick` | `method` |
| `onReceiveClick` | `method` |

### `EventCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onEventClick` | `method` |

### `EventSelectorCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onEventClick` | `method` |
| `isEventSelected` | `method` |

### `IconAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |
| `getItemViewType` | `method` |
| `setIconGroups` | `method` |
| `isHeader` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onIconClick` | `method` |

### `LicenseAdapter`

| Field | Type |
|-------|------|
| `setLicenses` | `method` |
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |

### `ViewHolder`

| Field | Type |
|-------|------|
| `onClick` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onLicenseClick` | `method` |

### `OverviewItemAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |
| `setData` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onPeriodClick` | `method` |

### `ParentCategorySelectorCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onCategorySelected` | `method` |
| `isCategorySelected` | `method` |

### `PeopleSelectorCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onPersonSelected` | `method` |
| `isPersonSelected` | `method` |

### `PeriodDetailFlowAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |
| `setData` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onCategoryClick` | `method` |

### `PeriodDetailSummaryAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |
| `setData` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onPeriodClick` | `method` |

### `PersonCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onPersonClick` | `method` |

### `PlaceCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onPlaceClick` | `method` |

### `PlaceSelectorCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onPlaceSelected` | `method` |
| `isPlaceSelected` | `method` |

### `RecurrentTransactionCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onRecurrentTransactionClick` | `method` |

### `RecurrentTransferCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onRecurrentTransferClick` | `method` |

### `SavingCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onSavingClick` | `method` |
| `onWithdrawEverything` | `method` |
| `onWithdraw` | `method` |
| `onDeposit` | `method` |

### `SettingCategoryAdapter`

| Field | Type |
|-------|------|
| `addCategory` | `method` |
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `getItemCount` | `method` |

### `ViewHolder`

| Field | Type |
|-------|------|
| `onClick` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onSettingCategoryClick` | `method` |

### `TransactionCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |
| `getItemViewType` | `method` |

### `HeaderViewHolder`

| Field | Type |
|-------|------|
| `onClick` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onHeaderClick` | `method` |
| `onTransactionClick` | `method` |

### `TransactionModelCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onModelClick` | `method` |
| `onModelAddClick` | `method` |
| `onModelEditClick` | `method` |

### `TransferCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |
| `getItemViewType` | `method` |

### `HeaderViewHolder`

| Field | Type |
|-------|------|
| `onClick` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onHeaderClick` | `method` |
| `onTransferClick` | `method` |

### `TransferModelCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ActionListener`

| Field | Type |
|-------|------|
| `onModelClick` | `method` |
| `onModelAddClick` | `method` |
| `onModelEditClick` | `method` |

### `WalletCursorAdapter`

| Field | Type |
|-------|------|
| `onCreateViewHolder` | `method` |
| `onBindViewHolder` | `method` |

### `WalletActionListener`

| Field | Type |
|-------|------|
| `onWalletClick` | `method` |

### `WalletSelectorCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |

### `ViewHolder`

| Field | Type |
|-------|------|
| `onClick` | `method` |

### `Controller`

| Field | Type |
|-------|------|
| `onWalletClick` | `method` |
| `isWalletSelected` | `method` |

### `WalletSortCursorAdapter`

| Field | Type |
|-------|------|
| `onBindViewHolder` | `method` |
| `onBindViewHolder` | `method` |
| `onCreateViewHolder` | `method` |
| `getItemId` | `method` |
| `swapCursor` | `method` |
| `moveItem` | `method` |
| `getSortedCategoryIds` | `method` |

### `WalletSortListener`

| Field | Type |
|-------|------|
| `onWalletDragStarted` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.adapter.recycler;
import android.database.Cursor;
import android.database.DataSetObserver;
import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
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