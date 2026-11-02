# Search

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Search

Last updated: 28/10/2026

```ts
import { Input } from "zmp-ui";
const { Search } = Input;
```

Used to enter search content


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

### SearchProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| onSearch | (value: string, event: React.ChangeEvent \| React.MouseEvent \| React.KeyboardEvent) => void | No | Callback invoked when the user performs a search. Actions considered as performing a search include:<br>- Clicking the magnifying glass icon (Search Icon)<br>- Pressing Enter/Return or a newline in the input |
| loading | boolean | No | The loading state of the input. When enabled, the input displays a loading icon at the start of the input instead of the magnifying glass icon (Search Icon). (default: `false`) |
