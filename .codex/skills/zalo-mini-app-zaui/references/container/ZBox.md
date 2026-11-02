# ZBox

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/container/ZBox

Last updated: 28/10/2026

```ts
import { ZBox } from "zmp-ui";
```

Used to manage layouts that can be considered fixed for each element. These are styles that are not specified, inherited, or derived from the composite layouts for a specific element.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| padding | string | No | The amount by with the Box is padded on all sides (default: `var(--s1)`) |
| borderWidth | string | No | The width of the (solid) border. If empty or 0, the transparent outline is instated for high contrast mode. (default: `var(--border-thin)`) |
| invert | boolean | No | Whether to apply an inverted theme. Only recommended for greyscale designs. (default: `false`) |
| children | React.ReactNode | No | ReactNode |

## Design guidelines

##### ZBox

We should treat all displayed elements as a box. All layouts provided by ZaUI have the job of arranging boxes together to form a complete application interface. For example, Stack simply adds vertical spacing between boxes. Stack should only be responsible for adding vertical margin; if it performs other functions, it will cause unnecessary errors in the remaining layouts.

In the ZaUI layout system, ZBox plays the role of managing styles that can be considered fixed for each element. These are styles that are not specified, inherited, or derived from the composite layouts for a specific element.

![stack_padding_issue](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/zbox/box_composition.svg)

ZBox provides the following properties:

###### `padding`

Padding adds equal spacing on all sides of the ZBox, because adding it to only one or a few sides would no longer make it a box. Usually, if you need to add spacing between elements, you should use `margin`. `Margin` extends outward beyond the element's border.

![box_padding_margin](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/zbox/box_padding_margin.svg)

###### `borderWidth`

Like `padding`, `border` should also be added to all sides of the box. If in some cases you need to use `border` to separate distinct elements, it should be applied contextually, through the parent element, just like `margin` in Stack. Otherwise, the borders will touch each other and double up.

![box_padding_margin](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/zbox/box_boxes.svg)
