# Slider

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Slider

Last updated: 28/10/2026

```ts
import { Slider } from "zmp-ui";
```

Used to allow users to select a value, or a range of values, within a limit


## Props

### SliderProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| min | number | No | The starting value of the slider. (default: `0`) |
| max | number | No | The ending value of the slider. (default: `100`) |
| step | number | No | The step increment of the slider. Can be an integer or a decimal number. (default: `1`) |
| minRange | number | No | The minimum distance between the 2 selected values of the slider. Only effective when used with a range slider (`value` is an array of 2 elements). |
| name | string | No | The identifying name of the slider in the form. |
| label | string | No | The label of the slider, displayed above the slider. |
| showValue | boolean | No | Displays the current value of the slider in the top right corner, aligned with `label`.<br>Can be used together with `renderValue` if an additional calculation mechanism or custom content for the displayed value is needed. (default: `false`) |
| marks | boolean \| number[] | No | The points to be marked on the slider. Setting `true` marks every `step` on the slider. If only a few arbitrary values need to be marked, pass in an array of the values to be marked. (default: `false`) |
| renderValue | (value: number \| Tuple \| undefined) => React.ReactNode | No | Function used to format the displayed value when `showValue` is enabled. This function receives the selected value(s) of the slider and returns a ReactNode to display. |
| prefix | React.ReactNode | No | The element displayed on the left side of the slider. |
| suffix | React.ReactNode | No | The element displayed on the right side of the slider. |
| value | number \| Tuple | No | The current selected value of the slider (for a single-thumb slider) and the array containing the 2 selected values (for a two-thumb slider, also called a range slider).<br>Must be used together with `onChange` to update the value when the user changes it. |
| defaultValue | number \| Tuple | No | Similar to `value`, but this value is only used to initialize the slider's value when it is first rendered. Changing this value after render has no effect. |
| onChange | (value: number \| Tuple) => void | No | Callback invoked when the value of the slider changes. The parameter passed in is the new value or pair of values of the slider. |

### SliderMarkProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| position | number | No | The position of the point to be marked on the slider, in percentage units. |
| filled | boolean | No | Whether the mark is within the selected range. (default: `false`) |

### SliderTrackProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| offset | number | No | The offset of the slider, in percentage units. |
| width | number | No | The thickness of the slider bar, in percentage units. |
| marks | SliderMarks | No | The points to be marked on the slider. Setting `true` marks every `step` on the slider. If only a few arbitrary values need to be marked, pass in an array of the values to be marked. |
| onMouseEnter | React.MouseEventHandler | No |  |
| onMouseLeave | React.MouseEventHandler | No |  |
| children | React.ReactNode | No |  |

### SliderThumbProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| position | number | No | The position of the thumb on the slider, in percentage units. |
