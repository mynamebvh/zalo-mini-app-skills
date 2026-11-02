# Cluster

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/container/Cluster

Last updated: 28/10/2026

```ts
import { Cluster } from "zmp-ui";
```

Used to group elements together with control over the margin spacing between them.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| justify | JustifyContentEnum | No | The justify-content value (for horizontal alignment) (default: `flex-start`) |
| align | AlignItemsEnum | No | The align-items value (for vertical alignment) (default: `flex-start`) |
| space | string | No | The space (margin) between each of the clustered elements (default: `var(--s1)`) |
| children | React.ReactNode | No | ReactNode |

## Design guidelines

##### Cluster

Cluster is a component for grouping elements together with control over the margin spacing between them.

![stack_padding_issue](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/cluster/layout-icon_cluster.svg)
