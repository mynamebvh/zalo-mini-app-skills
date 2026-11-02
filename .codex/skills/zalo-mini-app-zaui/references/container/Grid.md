# Grid

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/container/Grid

Last updated: 28/10/2026

```ts
import { Grid } from "zmp-ui";
```

Used to create a grid layout.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| columnCount | number | No | Specifying the columns in a grid (default: `1`) |
| min | string | No | A CSS length value representing x in minmax(min(x, 100%), 1fr) (default: `250px`) |
| rowSpace | string | No | The space between grid row (default: `var(--s1)`) |
| columnSpace | string | No | The space between grid column (default: `var(--s1)`) |
| children | React.ReactNode | No | ReactNode |

## Design guidelines

##### Grid

Grid is a component used to create a grid layout

![stack_padding_issue](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/grid/layout-icon_grid.svg)
