# Select

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Select

Last updated: 28/10/2026

```ts
import { Select } from "zmp-ui";
```

Used to allow users to select one or more items from groups of options


## Props

### SelectProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| value | SelectValue \| SelectValue[] | No | An array of `value`s of the selected `Option`s (if `multiple` is enabled) or the `value` of the selected `Option` in single select mode.<br>Must be used together with `onChange` to update the value. |
| defaultValue | SelectValue \| SelectValue[] | No | Similar to `value`, but used to set the default value for `Select`. Changing this value after render has no effect. |
| multiple | boolean | No | Allows selecting multiple options at once. (default: `false`) |
| children | ReactNode | No | The `Option`s used inside `Select`. |
| defaultOpen | boolean | No | Whether the selection dialog is open by default. Changing this value after render has no effect. (default: `false`) |
| disabled | boolean | No | The disabled state of `Select`, as well as the `Option`s inside it. (default: `false`) |
| onChange | (selected: SelectValueType \| SelectValueType[]) => void | No | Callback invoked when the value of `Select` changes. The parameter passed in is the new value of `Select`, which may be an array if `multiple` is enabled.<br>The value of `value` must be updated if it is passed in. |
| onVisibilityChange | (visibilityState: boolean) => void | No | Callback invoked when the selection dialog is opened, specifically after the user clicks the trigger input. |
| label | string \| ReactNode | No | The content displayed on the labels of `Select`. Display locations include: above the trigger input and as the title at the top of the selection dialog. |
| helperText | string | No | Helper text is a short piece of text located below the input fields. The content of these texts usually contains guidance that helps users better understand the purpose or describes the recommended input data format. |
| errorText | string | No | Error text is a short piece of text located below the input fields. The content of these texts usually contains warning information about errors in the entered data, as well as guidance on how to fix them.<br>`errorText` will be displayed instead of `helperText` when `status` has the value `error`. |
| status | InputStatus | No | The validity status of the input. If `error`, the input will have a warning color along with `errorText`; otherwise, the input will have a neutral color along with `helperText`. |
| name | string | No | The identifying name of `Select`. Usually used to distinguish inputs from each other within the same form. |
| placeholder | string | No | The placeholder of the input. Displayed when no option has been selected yet. |
| mask | boolean | No | Mask is a gray overlay layer covering the components below the dialog, preventing the user from interacting with that content and focusing attention on the opened dialog. (default: `true`) |
| maskCloseable | boolean | No | Closes the selection dialog when the user clicks the mask. (default: `true`) |
| closeOnSelect | boolean | No | Automatically closes the selection dialog when the user finishes selecting an option. (default: `false`) |

### OptGroupProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| label | string | No | The label of the group of related options, displayed above the options. |
| children | ReactNode | No | The `Option`s to be grouped together. |

### SelectOptionProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | ReactNode | No |  |
| title | string | No | The content displayed to the user. |
| value | SelectValue | No | The value of the option, used to identify the selected options within the `value` of `Select`. |
| disabled | boolean | No | The disabled state of the option. The user can still see this option, but cannot select it inside `Select`. (default: `false`) |
