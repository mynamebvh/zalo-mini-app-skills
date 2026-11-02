# Radio

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Radio

Last updated: 28/10/2026

```ts
import { Radio } from "zmp-ui";
```

Used to allow users to select a single item from a group of options


## Props

### RadioProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| checked | boolean | No | The checked state of the radio. Must be used together with `onChange` to update the value when the user interacts. (default: `false`) |
| defaultChecked | boolean | No | The default checked state of the radio. (default: `false`) |
| disabled | boolean | No | The disabled state of the radio. (default: `false`) |
| name | string | No | The identifying name of the radio. Used to group radios together in `Radio.Group`. |
| label | string | No | The label of the radio, displayed next to the radio. If a ReactNode needs to be displayed, use `children`. |
| value | RadioValueType | No | The value of the radio, used to identify which radio is selected in `Radio.Group`. |
| size | 'medium' \| 'small' | No | The size of the radio. (default: `'medium'`) |
| children | React.ReactNode | No | Used instead of `label` when more complex content needs to be displayed. Rendered to the right of the radio. |
| onChange | (event: ChangeEvent) => void | No | Callback invoked when the value of the radio changes. If `checked` is used, the value of `checked` must be updated in this callback. |

### RadioGroupProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| defaultValue | RadioValueType | No | The `Radio` whose `value` matches this value will be preselected. Changing this value after render has no effect. |
| value | RadioValueType | No | The current value of the radio group. More specifically, the `value` property of the `Radio` currently selected among the `Radio`s with the same `name`.<br>Must be used together with `onChange` to update the value when the user interacts. |
| disabled | boolean | No | The disabled state of the radio group, as well as the child radios inside it. (default: `false`) |
| name | string | No | The identifying name of the radio group. Used to group radios together. |
| size | 'medium' \| 'small' | No | The size of the radio group. (default: `'medium'`) |
| options | RadioProps[] | No | An array of settings used to create the radios in the group. If other elements besides radios need to be displayed, use `children` instead of `options`. |
| onChange | (value: RadioValueType) => void | No | Callback invoked when the value of the radio group changes. More specifically, when a radio in the group is selected or replaces the previously selected radio. If `value` is used, the value of `value` must be updated in this callback. |
| children | React.ReactNode | No | Used to render the `<Radio>` elements in the group as well as other elements. Do not use together with `options`. |
