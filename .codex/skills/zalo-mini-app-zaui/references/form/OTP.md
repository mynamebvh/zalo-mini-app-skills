# OTP

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/OTP

Last updated: 28/10/2026

```ts
import { Input } from "zmp-ui";
const { OTP } = Input;
```

Used to enter an OTP code.


## Props

### InputProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| value | InputHTMLAttributes['value'] | No | The value of the input.<br>Must be used together with `onChange` to update the value. |
| onChange | InputHTMLAttributes['onChange'] | No | Callback called when the value of the input changes. The value of `value` must be updated if it is passed in. |
| type | InputType | No | The input type. |
| status | InputStatus | No | The validity state of the input. If it is `error`, the input will have a warning color along with `errorText`; otherwise, the input will have a neutral color along with `helperText`. |
| onPressEnter | KeyboardEventHandler | No | Callback called when the user presses Enter or inserts a new line in the input. |
| size | InputSize | No | The size of the input. Takes one of the values `small`, `medium`, or `large`. (default: `'medium'`) |

### OTPProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| value | string | No | The value of the OTP. Must be used together with `onChange` to update the value. |
| defaultValue | string | No | The default value of the OTP. Changing the value of `defaultValue` after the component has been rendered has no effect. |
| otpLength | number | No | The length of the OTP, which is also the number of OTP input cells. Defaults to 4 cells. (default: `4`) |
| show | boolean | No | Show or hide the entered OTP code. By default, the OTP code is displayed as asterisks (\*). (default: `false`) |
