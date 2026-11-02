# TextArea

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/TextArea

Last updated: 28/10/2026

```ts
import { Input } from "zmp-ui";
const { TextArea } = Input;
```

Used to enter long or multi-line content


## Props

### InputProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| value | InputHTMLAttributes['value'] | No | The value of the input.<br>Must be used together with `onChange` to update the value. |
| onChange | InputHTMLAttributes['onChange'] | No | Callback invoked when the value of the input changes. The value of `value` must be updated if it is passed in. |
| type | InputType | No | The input type. |
| status | InputStatus | No | The validity status of the input. If `error`, the input will have a warning color along with `errorText`; otherwise, the input will have a neutral color along with `helperText`. |
| onPressEnter | KeyboardEventHandler | No | Callback invoked when the user presses Enter or a newline in the input. |
| size | InputSize | No | The size of the input. Takes one of the values `small`, `medium`, or `large`. (default: `'medium'`) |

### TextAreaProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| value | InputHTMLAttributes['value'] | No | The value of the textarea.<br>Must be used together with `onChange` to update the value. |
| onChange | InputHTMLAttributes['onChange'] | No | Callback invoked when the value of the textarea changes. The value of `value` must be updated if it is passed in. |
| status | InputStatus | No | The validity status of the textarea. If `error`, the textarea will have a warning color along with `errorText`; otherwise, the textarea will have a neutral color along with `helperText`. |
| onPressEnter | KeyboardEventHandler | No | Callback invoked when the user presses Enter or a newline in the textarea. |
| size | InputSize | No | The size of the textarea. Takes one of the values `small`, `medium`, or `large`. (default: `'medium'`) |
| showCount | boolean \| ShowCountProps | No | Shows the number of characters entered in the textarea in the bottom right corner (character counter). An object with a `formatter` property can be passed in to override the counter's behavior. (default: `false`) |
| autoHeight | boolean | No | When `autoHeight` is `true`, the textarea automatically adjusts its height according to the current value. When `autoHeight` is `false`, the textarea has a fixed height. |
