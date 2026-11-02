# Stack

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/container/Stack

Last updated: 28/10/2026

```ts
import { Stack } from "zmp-ui";
```

Helps make it easier to arrange elements vertically in the app's interface.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| space | string | No | A CSS `margin` value (default: `var(--s1)`) |
| recursive | boolean | No | Whether the spaces apply recursively (i.e. regardless of nesting level) (default: `false`) |
| splitAfter | number | No | The element after which to \_split\_ the stack with an auto margin (default: `null`) |
| children | React.ReactNode | No | ReactNode |

## Design guidelines

##### Stack

###### Problem

In interface design, we often need to separate elements from other elements by a certain distance, and `margin` is used for this purpose. However, when designing elements independently, we don't know what content surrounds them, and the spacing requirements will have to change. Usually, we design directly for the elements, but margin is a property of the relationship between adjacent elements. This can create problems such as excess gaps in the following case:

![stack_padding_issue](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/stack/stack_padding_issue.svg)

###### Solution

Stack was created to make it easier to arrange elements vertically in the app's interface. With Stack, you can flexibly specify the spacing between consecutive elements, split the stack into multiple parts if needed, and apply the properties recursively to all nested elements.

![stack_padding_issue](https://docs.zaloplatforms.com/assets/MA/img/zaui/layout/stack/stack_form.svg)
