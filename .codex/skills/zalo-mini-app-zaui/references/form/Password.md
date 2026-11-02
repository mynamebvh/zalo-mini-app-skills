# Password

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Password

Last updated: 28/10/2026

```ts
import { Input } from "zmp-ui";
const { Password } = Input;
```

Used to enter a password


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

### PasswordProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| visibilityToggle | boolean | No | When enabled, an eye-shaped icon (Visibility Toggle) will be displayed on the right side of the input to allow the user to show or hide the password they have entered when tapping it. (default: `false`) |
| iconRender | (visible: boolean) => React.ReactNode | No | Custom icon to display on the Visibility Toggle instead of the default icon. Must be used together with `visibilityToggle`.<br>The value is passed in as a function, with the first parameter being a boolean variable representing the shown or hidden state of the password, and returns a ReactNode. |
