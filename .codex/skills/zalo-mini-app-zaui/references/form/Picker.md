# Picker

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Picker

Last updated: 28/10/2026

```ts
import { Picker } from "zmp-ui";
```

Used to create an interface that lets the user select an option on each data column


## Props

### PickerProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| label | string | No | The label of the input used as the element that triggers the picker dialog. Displayed above the input. |
| helperText | string | No | Helper text is a short piece of text below the input fields. The content of these texts usually contains guidance to help users better understand the purpose or describe the format of the data they are encouraged to enter. |
| errorText | string | No | Error text is a short piece of text below the input fields. The content of these texts usually contains warning information about errors in the entered data, as well as guidance on how to fix them.<br>`errorText` will be displayed instead of `helperText` when `status` has the value `error`. |
| status | InputStatus | No | The current state of the date picker input. If it is `error`, the input will have a warning color along with `errorText`; otherwise, the input will have a neutral color along with `helperText`. |
| placeholder | string | No | The placeholder of the picker's input. Displayed when there is no value. |
| title | string | No | The title displayed at the top of the picker dialog. |
| data | PickerDataType[] | No | An array containing the settings for the columns to display in the picker panel. Each element in the array corresponds to a column in the picker panel, in order from left to right. |
| disabled | boolean | No | Disable the picker as well as the input used to trigger the picker. (default: `false`) |
| defaultValue | { { [name: string]: OptionValueType } } | No | The default value of the picker. Changing the value of `defaultValue` after the picker has been rendered has no effect.<br>Passed in as an object containing the `value` of the options to be pre-selected, with the key being the name of the corresponding column. |
| value | { { [name: string]: OptionValueType } } | No | The current value of the picker. Must be used together with `onChange` to update the selected value.<br>Passed in as an object containing the `value` of the options the user has selected, with the key being the name of the corresponding column. |
| defaultOpen | boolean | No | Show the picker dialog by default when rendering. (default: `false`) |
| onChange | (value: { { [name: string]: PickerColumnOption } }) => void | No | Callback called when the value of the columns changes. The `value` must be updated if it is passed in to ensure the selection is displayed correctly. |
| onVisibilityChange | (visibilityState: boolean) => void | No | Callback called when the visibility state of the picker dialog changes |
| inputClass | string | No | The CSS class of the input used to trigger the picker |
| mask | boolean | No | Mask is a gray overlay layer covering the components below the picker dialog, preventing the user from interacting with that content and focusing on the opened dialog. (default: `false`) |
| maskClosable | boolean | No | Allow closing the picker dialog when clicking on the mask. (default: `false`) |
| formatPickedValueDisplay | (value: { { [name: string]: PickerColumnOption } }) => string | No | Function used to format the display value of the picker. Receives an object containing the selected settings of the columns, and must return a string to display on the picker's input. |
| action | PickerActionType | No | The settings for the confirm button, displayed below the picker dialog. |
| prefix | ReactNode | No | The element on the left of the picker's input. |
| suffix | ReactNode | No | The element on the right of the picker's input. |
| name | string | No | The identifier name of the picker, used with the form to distinguish inputs from each other. |

### PickerColumnProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| prefixCls | string | No | The prefix of the column's CSS classes |
| options | PickerColumnOption[] | No | An array of the options inside the column. |
| name | string | No | The identifier name of the column, used to distinguish columns from each other. |
| value | PickerColumnOption | No | The current option. The value passed in must be directly in the `options` array. Must be used together with `onChange` to update the selected value. |
| defaultValue | PickerColumnOption | No | The default value of the selected option. Similar to `value`, the value passed in must be directly in the `options` array. |
| onChange | (value: PickerColumnOption, name: string) => void | No | Callback called when the selection changes. The `value` must be updated if it is passed in to ensure the selection is displayed correctly. |

### PickerColumnOption

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| key | string | No | The key that distinguishes between options |
| value | OptionValueType | No | The value of the option, used to determine the selected option |
| displayName | string | No | The display name of the option to the user |
| selected | boolean | No | The initially selected state (default: `false`) |

### PickerActionType

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| text | string | No | The text on the button |
| onClick | (event: React.MouseEvent) => void | No | Callback called when the action is clicked |
| close | boolean | No | This action specifies closing the picker when clicked (default: `false`) |
