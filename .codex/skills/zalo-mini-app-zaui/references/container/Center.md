# Center

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/container/Center

Last updated: 28/10/2026

```ts
import { Center } from "zmp-ui";
```

Used to horizontally center an element.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| max | string | No | The maximum width of the centered element (default: `var(--measure)`) |
| andText | boolean | No | Center align the text too (default: `false`) |
| gutters | string | No | The minimum space on either side of the content (default: `null`) |
| intrinsic | boolean | No | Center child elements based on their content width (default: `false`) |
| children | React.ReactNode | No | ReactNode |

## Design guidelines

##### Center

Center is a component for horizontally centering an element.

![box_padding_margin](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/center/layout-icon_center.svg)
