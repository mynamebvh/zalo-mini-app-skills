# Box

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/container/Box

Last updated: 28/10/2026

```ts
import { Box } from "zmp-ui";
```

Used as a wrapper around elements to easily add spacing between elements according to the Zalo Mini App spacing system, or to quickly create a flex layout.


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| noSpace | boolean | No | Elements will have `margin: 0` and `padding: 0` (default: `false`) |
| inline | boolean | No | Value `true` if you want the elements to be inline block (default: `false`) |
| m | number | No | The box margin value; accepts a level from 0 to 10, with the corresponding margin value being level x 4px |
| p | number | No | The box padding value; accepts a level from 0 to 10, with the corresponding padding value being level x 4px |
| mt | number | No | The margin top value |
| ml | number | No | The margin left value |
| mb | number | No | The margin bottom value |
| mr | number | No | The margin right value |
| pt | number | No | The padding top value |
| pl | number | No | The padding left value |
| pb | number | No | The padding bottom value |
| pr | number | No | The padding right value |
| mx | number | No | The margin left and margin right value |
| my | number | No | The margin top and margin bottom value |
| px | number | No | The padding left and padding right value |
| py | number | No | The padding top and padding bottom value |
| width | number | No | The width of the box |
| height | number | No | The height of the box |
| verticalAlign | 'baseline' \| 'sub' \| 'super' \| 'top' \| 'text-top' \| 'middle' \| 'bottom' \| 'text-bottom' \| 'initial' \| 'inherit' | No | The vertical-align value |
| textAlign | 'left' \| 'right' \| 'center' \| 'justify' \| 'initial' \| 'inherit' | No | The text-align value |
| flex | boolean | No | Switch the box to a flex layout (default: `false`) |
| flexDirection | 'row' \| 'row-reverse' \| 'column' \| 'column-reverse' | No | The flex-direction value |
| flexWrap | boolean | No | The flex-wrap value (default: `false`) |
| justifyContent | 'flex-start' \| 'flex-end' \| 'center' \| 'space-between' \| 'space-around' \| 'space-evenly' \| 'initial' | No | The justify-content value |
| alignItems | 'flex-start' \| 'flex-end' \| 'stretch' \| 'baseline' \| 'center' \| 'initial' | No | The align-items value |
| alignContent | 'stretch' \| 'center' \| 'flex-start' \| 'flex-end' \| 'space-between' \| 'space-around' \| 'space-evenly' \| 'initial' | No | The align-content value |
| children | React.ReactNode | No | ReactNode |
