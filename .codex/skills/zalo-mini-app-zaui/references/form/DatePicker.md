# DatePicker

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/DatePicker

Last updated: 28/10/2026

```ts
import { DatePicker } from "zmp-ui";
```

Used to let the user select a date.


## Props

### DatePickerProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| label | string | No | The label of the date picker input. It will be displayed above the input. |
| helperText | string | No | Helper text is a short piece of text below the input fields. The content of these texts usually contains guidance to help users better understand the purpose or describe the format of the data they are encouraged to enter. |
| errorText | string | No | Error text is a short piece of text below the input fields. The content of these texts usually contains warning information about errors in the entered data, as well as guidance on how to fix them.<br>`errorText` will be displayed instead of `helperText` when `status` has the value `error`. |
| status | '' \| 'error' \| 'success' | No | The current state of the date picker input. If it is `error`, the input will have a warning color along with `errorText`; otherwise, the input will have a neutral color along with `helperText`. (default: `''`) |
| placeholder | string | No | The placeholder of the date picker input. Displayed when there is no value. |
| title | string | No | The title of the date picker dialog. |
| disabled | boolean | No | Disable the date picker input. (default: `false`) |
| startDate | Date | No | The start date of the date picker. The user will not be able to select a date before this date. |
| endDate | Date | No | The end date of the date picker. The user will not be able to select a date after this date. |
| startYear | number | No | The start year of the date picker. The user will not be able to select a year before this year. |
| endYear | number | No | The end year of the date picker. The user will not be able to select a year after this year. |
| formatPickedValueDisplay | (date: Date) => string | No | Function used to format the display content of the date picker input based on the currently selected date value.<br>Unlike `dateFormat`, which is a date format string, `formatPickedValueDisplay` is a function that receives the currently selected date value and returns the display string, and this display string may not be a date. |
| dateFormat | string | No | The date format of the date picker input.<br>- Day: `dd`<br>- Month: `mm`, `m`, `MM` (text style), `M` (abbreviated text style)<br>- Year: `yyyy`, `yy` |
| columnsFormat | 'MM-DD-YYYY' \| 'DD-MM-YYYY' \| 'YYYY-MM-DD' | No | Arranges the corresponding appearance position of the day, month, and year columns in the date picker.<br>`DD` corresponds to the day column, `MM` corresponds to the month column, `YYYY` corresponds to the year column. |
| defaultOpen | boolean | No | Open the date picker dialog by default on initialization. (default: `false`) |
| defaultValue | Date | No | The default date pre-selected when initializing the date picker.<br>\_Note: changing the value of `defaultValue` after the date picker is initialized has no effect.\_ |
| value | Date | No | The selected date. Must be used together with `onChange` to update the value for the date picker after the user changes it. |
| onChange | (value: Date, pickedValue: { { [name: string]: OptionValueType } }) => void | No | Callback called when the user changes the value of the date picker. The parameter passed in is the new value of the date picker. |
| onVisibilityChange | (visibilityState: boolean) => void | No | Callback called when the user opens / closes the date picker dialog. |
| mask | boolean | No | Mask is a gray overlay layer covering the components below the date picker dialog, preventing the user from interacting with that content and focusing on the opened dialog. (default: `true`) |
| maskClosable | boolean | No | Automatically close the date picker dialog when the user taps on the mask. The `mask` property must be enabled to use this feature. (default: `true`) |
| action | DatePickerActionType | No | Add an action button to the date picker dialog. |
| inputClass | string | No | Add a CSS class to the date picker input. |
| prefix | ReactNode | No | Add content to the beginning of the date picker input. Commonly used to display an icon. |
| suffix | ReactNode | No | Add content to the end of the date picker input. Commonly used to display an icon. |
| locale | string | No | The display language of the date picker, passed in as a BCP 47 language code, for example: `vi-VN`, `en-US`. |

### DatePickerActionType

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| text | string | No | The text on the button. |
| close | boolean | No | Tapping the button will close the date picker dialog. (default: `false`) |
| onClick | (event: React.MouseEvent) => void | No | Callback called when the button is tapped. |
