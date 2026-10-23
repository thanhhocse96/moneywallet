<!-- AUTO_START | hash: 59c22bce | built: 2026-10-20T15:42 -->
# Context: `app/src/main/java/com/oriondev/moneywallet/ui/fragment/dialog`

> **[auto-generated — không sửa tay phần này]**  
> Language: `java-kotlin`  
> Source files: 16

## [auto] Public Functions

### `onCreateDialog` (line 72)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 154)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `show` (line 161)
```text
public void show(FragmentManager fragmentManager, String tag, String backendId)
```

### `onActivityResult` (line 189)
```text
@Override public void onActivityResult(int requestCode, int resultCode, Intent data)
```

### `newInstance` (line 41)
```text
public static BudgetTypePickerDialog newInstance()
```

### `onCreateDialog` (line 48)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 64)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 70)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 74)
```text
public void showPicker(FragmentManager fragmentManager, String tag, Contract.BudgetType budgetType)
```

### `onBudgetTypeSelected` (line 79)
```text
@Override public void onBudgetTypeSelected(Contract.BudgetType budgetType)
```

### `isBudgetTypeSelected` (line 85)
```text
@Override public boolean isBudgetTypeSelected(Contract.BudgetType budgetType)
```

### `onBudgetTypeSelected` (line 92)
```text
void onBudgetTypeSelected(Contract.BudgetType budgetType)
```

### `showSafely` (line 48)
```text
public static void showSafely(FragmentManager fragmentManager, String tag)
```

### `onCreateDialog` (line 60)
```text
@NonNull @Override public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onCreateLoader` (line 76)
```text
@Override public Loader<List<ChangeLog>> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 85)
```text
@Override public void onLoadFinished(Loader<List<ChangeLog>> loader, List<ChangeLog> data)
```

### `onLoaderReset` (line 92)
```text
@Override public void onLoaderReset(Loader<List<ChangeLog>> loader)
```

### `newInstance` (line 56)
```text
public static CurrencyConverterDialog newInstance()
```

### `onAttach` (line 69)
```text
@Override public void onAttach(Context context)
```

### `onDetach` (line 77)
```text
@Override public void onDetach()
```

### `onReceive` (line 89)
```text
@Override public void onReceive(Context context, Intent intent)
```

### `onCreateDialog` (line 103)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 160)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 168)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 172)
```text
public void showPicker(FragmentManager fragmentManager, String tag, CurrencyUnit currency1, CurrencyUnit currency2, double exchangeRate)
```

### `onExchangeRateChanged` (line 181)
```text
void onExchangeRateChanged(double exchangeRate)
```

### `newInstance` (line 58)
```text
public static CustomDigitSetupDialog newInstance()
```

### `onCreateDialog` (line 62)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 145)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `newInstance` (line 24)
```text
public static DataFormatPickerDialog newInstance()
```

### `onCreateDialog` (line 32)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 49)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 56)
```text
public void setCallback(DataFormatPickerDialog.Callback callback)
```

### `showPicker` (line 60)
```text
public void showPicker(FragmentManager fragmentManager, String tag, DataFormat[] dataFormats, int index)
```

### `onDataFormatSelected` (line 66)
```text
@Override public void onDataFormatSelected(DataFormat dataFormat)
```

### `isDataFormatSelected` (line 72)
```text
@Override public boolean isDataFormatSelected(DataFormat dataFormat)
```

### `onDataFormatSelected` (line 79)
```text
void onDataFormatSelected(DataFormat dataFormat)
```

### `newInstance` (line 62)
```text
public static EventPickerDialog newInstance()
```

### `onCreateDialog` (line 76)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 116)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 123)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 127)
```text
public void showPicker(FragmentManager fragmentManager, String tag, Event event, Date filterDate)
```

### `onCreateLoader` (line 133)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 158)
```text
@Override public void onLoadFinished(Loader<Cursor> loader, Cursor data)
```

### `onLoaderReset` (line 170)
```text
@Override public void onLoaderReset(Loader<Cursor> loader)
```

### `onEventClick` (line 175)
```text
@Override public void onEventClick(Event event)
```

### `isEventSelected` (line 181)
```text
@Override public boolean isEventSelected(long id)
```

### `onEventSelected` (line 188)
```text
void onEventSelected(Event event)
```

### `newInstance` (line 37)
```text
public static ExportColumnsDialogFragment newInstance()
```

### `onCreateDialog` (line 44)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 76)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 82)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 86)
```text
public void showPicker(FragmentManager fragmentManager, String tag, Integer[] indices)
```

### `getColumnNameFromIndices` (line 91)
```text
public static String[] getColumnNameFromIndices(Context context, Integer[] indices)
```

### `getCursorColumnsFromIndices` (line 102)
```text
public static String[] getCursorColumnsFromIndices(Integer[] indices)
```

### `onExportColumnsSelected` (line 115)
```text
void onExportColumnsSelected(Integer[] indices)
```

### `newInstance` (line 40)
```text
public static GenericProgressDialog newInstance(int title, int content, boolean indeterminate)
```

### `onCreateDialog` (line 51)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `updateProgress` (line 74)
```text
public void updateProgress(int contentRes, int progress)
```

### `showSafely` (line 48)
```text
public static void showSafely(FragmentManager fragmentManager, String tag, Callback callback)
```

### `onCreateDialog` (line 63)
```text
@NonNull @Override public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `setCallback` (line 79)
```text
public void setCallback(Callback callback)
```

### `onCreateLoader` (line 83)
```text
@Override public Loader<List<License>> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 92)
```text
@Override public void onLoadFinished(Loader<List<License>> loader, List<License> data)
```

### `onLoaderReset` (line 99)
```text
@Override public void onLoaderReset(Loader<List<License>> loader)
```

### `onLicenseClick` (line 106)
```text
@Override public void onLicenseClick(License license)
```

### `onLicenseClick` (line 115)
```text
void onLicenseClick(License license)
```

### `newInstance` (line 62)
```text
public static OverviewSettingDialog newInstance()
```

### `onCreateDialog` (line 81)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 225)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 303)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 307)
```text
public void showPicker(FragmentManager fragmentManager, String tag, OverviewSetting overviewSetting)
```

### `onDateTimeChanged` (line 312)
```text
@Override public void onDateTimeChanged(String tag, Date date)
```

### `onCategoryChanged` (line 324)
```text
@Override public void onCategoryChanged(String tag, Category category)
```

### `onOverviewSettingChanged` (line 333)
```text
void onOverviewSettingChanged(OverviewSetting overviewSetting)
```

### `newInstance` (line 60)
```text
public static ParentCategoryPickerDialog newInstance()
```

### `onCreateDialog` (line 75)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 116)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 124)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 128)
```text
public void showPicker(FragmentManager fragmentManager, String tag, Category category, long callerId, Contract.CategoryType type)
```

### `onCategorySelected` (line 135)
```text
@Override public void onCategorySelected(Category category)
```

### `isCategorySelected` (line 141)
```text
@Override public boolean isCategorySelected(long id)
```

### `onCreateLoader` (line 146)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 166)
```text
@Override public void onLoadFinished(Loader<Cursor> loader, Cursor data)
```

### `onLoaderReset` (line 178)
```text
@Override public void onLoaderReset(Loader<Cursor> loader)
```

### `onCategorySelected` (line 185)
```text
void onCategorySelected(Category category)
```

### `newInstance` (line 59)
```text
public static PeoplePickerDialog newInstance()
```

### `onCreateDialog` (line 72)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 132)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 142)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 146)
```text
public void showPicker(FragmentManager fragmentManager, String tag, Person[] people)
```

### `onCreateLoader` (line 156)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 172)
```text
@Override public void onLoadFinished(Loader<Cursor> loader, Cursor cursor)
```

### `onLoaderReset` (line 184)
```text
@Override public void onLoaderReset(Loader<Cursor> loader)
```

### `onPersonSelected` (line 189)
```text
@Override public void onPersonSelected(Person person)
```

### `isPersonSelected` (line 199)
```text
@Override public boolean isPersonSelected(long id)
```

### `onPeopleSelected` (line 206)
```text
void onPeopleSelected(Person[] people)
```

### `newInstance` (line 58)
```text
public static PlacePickerDialog newInstance()
```

### `onCreateDialog` (line 71)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 110)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 116)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 120)
```text
public void showPicker(FragmentManager fragmentManager, String tag, Place place)
```

### `onCreateLoader` (line 125)
```text
@Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 144)
```text
@Override public void onLoadFinished(Loader<Cursor> loader, Cursor data)
```

### `onLoaderReset` (line 156)
```text
@Override public void onLoaderReset(Loader<Cursor> loader)
```

### `onPlaceSelected` (line 161)
```text
@Override public void onPlaceSelected(Place place)
```

### `isPlaceSelected` (line 167)
```text
@Override public boolean isPlaceSelected(long id)
```

### `onPlaceSelected` (line 174)
```text
void onPlaceSelected(Place place)
```

### `newInstance` (line 57)
```text
public static RecurrencePickerDialog newInstance()
```

### `onCreateDialog` (line 87)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 231)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `getCurrentRecurrenceSetting` (line 364)
```text
public RecurrenceSetting getCurrentRecurrenceSetting()
```

### `setCallback` (line 385)
```text
public void setCallback(Callback callback)
```

### `showPicker` (line 389)
```text
public void showPicker(FragmentManager fragmentManager, String tag, RecurrenceSetting recurrenceSetting)
```

### `onDateTimeChanged` (line 394)
```text
@Override public void onDateTimeChanged(String tag, Date date)
```

### `onCheckedChanged` (line 408)
```text
@Override public void onCheckedChanged(CompoundButton buttonView, boolean isChecked)
```

### `onRecurrenceSettingChanged` (line 420)
```text
void onRecurrenceSettingChanged(RecurrenceSetting recurrenceSetting)
```

### `newInstance` (line 60)
```text
public static WalletPickerDialog newInstance()
```

### `onCreateDialog` (line 74)
```text
@Override @NonNull public Dialog onCreateDialog(Bundle savedInstanceState)
```

### `onSaveInstanceState` (line 148)
```text
@Override public void onSaveInstanceState(Bundle outState)
```

### `setCallback` (line 159)
```text
public void setCallback(Callback callback)
```

### `showSinglePicker` (line 163)
```text
public void showSinglePicker(FragmentManager fragmentManager, String tag, Wallet wallet)
```

### `showMultiPicker` (line 172)
```text
public void showMultiPicker(FragmentManager fragmentManager, String tag, Wallet[] wallets)
```

### `onCreateLoader` (line 183)
```text
@NonNull @Override public Loader<Cursor> onCreateLoader(int id, Bundle args)
```

### `onLoadFinished` (line 205)
```text
@Override public void onLoadFinished(@NonNull Loader<Cursor> loader, Cursor cursor)
```

### `onLoaderReset` (line 217)
```text
@Override public void onLoaderReset(@NonNull Loader<Cursor> loader)
```

### `onWalletClick` (line 222)
```text
@Override public void onWalletClick(Wallet wallet)
```

### `isWalletSelected` (line 237)
```text
@Override public boolean isWalletSelected(long id)
```

### `onWalletSelected` (line 244)
```text
void onWalletSelected(Wallet wallet)
```

### `onWalletsSelected` (line 246)
```text
void onWalletsSelected(Wallet[] wallets)
```

## [auto] Types

### `AutoBackupSettingDialog`

| Field | Type |
|-------|------|
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `show` | `method` |
| `onActivityResult` | `method` |

### `BudgetTypePickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onBudgetTypeSelected` | `method` |
| `isBudgetTypeSelected` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onBudgetTypeSelected` | `method` |

### `ChangeLogDialog`

| Field | Type |
|-------|------|
| `showSafely` | `method` |
| `onCreateDialog` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |

### `CurrencyConverterDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onAttach` | `method` |
| `onDetach` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onExchangeRateChanged` | `method` |

### `CustomDigitSetupDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |

### `DataFormatPickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onDataFormatSelected` | `method` |
| `isDataFormatSelected` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onDataFormatSelected` | `method` |

### `EventPickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onEventClick` | `method` |
| `isEventSelected` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onEventSelected` | `method` |

### `ExportColumnsDialogFragment`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `getColumnNameFromIndices` | `method` |
| `getCursorColumnsFromIndices` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onExportColumnsSelected` | `method` |

### `GenericProgressDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `dateProgress` | `method` |

### `LicenseDialog`

| Field | Type |
|-------|------|
| `showSafely` | `method` |
| `onCreateDialog` | `method` |
| `setCallback` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onLicenseClick` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onLicenseClick` | `method` |

### `OverviewSettingDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onDateTimeChanged` | `method` |
| `onCategoryChanged` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onOverviewSettingChanged` | `method` |

### `ParentCategoryPickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onCategorySelected` | `method` |
| `isCategorySelected` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onCategorySelected` | `method` |

### `PeoplePickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onPersonSelected` | `method` |
| `isPersonSelected` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onPeopleSelected` | `method` |

### `PlacePickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onPlaceSelected` | `method` |
| `isPlaceSelected` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onPlaceSelected` | `method` |

### `RecurrencePickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `getCurrentRecurrenceSetting` | `method` |
| `setCallback` | `method` |
| `showPicker` | `method` |
| `onDateTimeChanged` | `method` |

### `Callback`

| Field | Type |
|-------|------|
| `onRecurrenceSettingChanged` | `method` |

### `WalletPickerDialog`

| Field | Type |
|-------|------|
| `newInstance` | `method` |
| `onCreateDialog` | `method` |
| `onSaveInstanceState` | `method` |
| `setCallback` | `method` |
| `showSinglePicker` | `method` |
| `showMultiPicker` | `method` |
| `onCreateLoader` | `method` |
| `onLoadFinished` | `method` |
| `onLoaderReset` | `method` |
| `onWalletClick` | `method` |
| _(+1 more)_ | |

### `Callback`

| Field | Type |
|-------|------|
| `onWalletSelected` | `method` |
| `onWalletsSelected` | `method` |

## [auto] Key Imports

```
package com.oriondev.moneywallet.ui.fragment.dialog;
import android.app.Activity;
import android.app.Dialog;
import android.content.Intent;
import android.os.Bundle;
import androidx.annotation.NonNull;
import androidx.fragment.app.DialogFragment;
import androidx.fragment.app.FragmentManager;
import androidx.appcompat.widget.SwitchCompat;
import android.view.View;
// ... +75 more
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