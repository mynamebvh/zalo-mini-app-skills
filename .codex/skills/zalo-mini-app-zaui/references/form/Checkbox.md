# Checkbox

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Checkbox

Last updated: 28/10/2026

```ts
import { Checkbox } from "zmp-ui";
```

Used to select one or more items in a group of choices.


## Props

### CheckboxProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| checked | boolean | No | The checked state of the checkbox.<br>Must be used together with `onChange` to update the value. (default: `false`) |
| onChange | Function | No | Callback called when the state of the checkbox changes. The value of `checked` must be updated if it is passed in. |
| defaultChecked | boolean | No | The default state of the checkbox.<br>\_Note: Changing `defaultChecked` after the checkbox has been rendered has no effect.\_ (default: `false`) |
| disabled | boolean | No | Disable the checkbox. (default: `false`) |
| name | string | No | The name of the checkbox. Used to group checkboxes together. Checkboxes with the same `name` are considered a group. |
| label | string | No | The label of the checkbox, displayed after the checkbox. If you need to display a ReactNode, use `children` instead of `label`. |
| value | string \| number | No | The value of the checkbox.<br>Unlike `checked`, which is the checked state of the checkbox, `value` is used to determine the value of the `CheckboxGroup` when the checkboxes inside it are selected. If the checkbox is selected, its value is added to the `value` array of the `CheckboxGroup`; otherwise, it is removed from the array. |
| size | 'medium' \| 'small' | No | The size of the checkbox. |
| indeterminate | boolean | No | If enabled, the checkbox will additionally have an indeterminate state. The indeterminate state is an intermediate state between `checked` and `unchecked`. (default: `false`) |
| children | React.ReactNode | No | The content displayed instead of `label`, after the checkbox. |

### CheckboxGroupProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| defaultValue | (string \| number)[] | No | The default value of the checkbox group. Checkboxes inside the group whose `value` property is in this array will be pre-selected.<br>\_Note: Changing `defaultValue` after the checkbox group has been rendered has no effect.\_ |
| value | (string \| number)[] | No | The value of the checkbox group. Checkboxes inside the group whose `value` property is in this array will be selected.<br>Must be used together with `onChange` to update the value. |
| onChange | (checkedValue: (string \| number)[]) => void | No | Callback called when the state of the checkbox group changes. The value of `value` must be updated if it is passed in. |
| disabled | boolean | No | Disable the checkbox group. |
| name | string | No | The name of the checkbox group. Used to group checkboxes together. Checkboxes with the same `name` are considered a group. |
| size | 'medium' \| 'small' | No | The size of the checkboxes in the group. |
| options | CheckboxProps[] | No | Instead of rendering `<Checkbox>` inside `<Checkbox.Group>`, you can use `options` to manage the choices of this group.<br>All properties of `CheckboxProps` can be used in `options`. |
| children | React.ReactNode | No |  |
