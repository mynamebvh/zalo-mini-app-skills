# List

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/List

Last updated: 28/10/2026

```ts
import { List } from "zmp-ui";
```

Used to display data in a list format.


## Props

### ListProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| dataSource | T[] | No | Use `dataSource` together with `renderItem` to display the list of items, instead of passing the items directly as children.<br>The data source must be an array of values, and the value type can be any data type. |
| renderItem | (item: T, index: number, loading: boolean) => React.ReactNode | No | Function used to render each item in `dataSource`. This function takes 3 parameters:<br>- `item`: The value to render, taken from `dataSource`.<br>- `index`: The current position of the item being rendered.<br>- `loading`: The loading state of the list.<br>The result returns a `ReactNode`, preferably a `<ListItem>`. |
| loading | boolean | No | The loading state of the list. (default: `false`) |
| divider | boolean | No | Displays a divider between the items in the list. (default: `true`) |
| noSpacing | boolean | No | Does not display spacing between the items in the list. (default: `false`) |
| children | React.ReactNode | No | The items to display in the list. \_Has no effect when used together with `dataSource`.\_ |

### ListItemProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| title | string | No | The title of the list item. |
| subTitle | string | No | The subtitle of the list item. Located below the main title. |
| prefix | React.ReactNode | No | The element to display at the start of the list item. Usually an icon. |
| suffix | React.ReactNode | No | The element to display at the end of the list item. Usually an icon. |
| brackets | string | No | Content inside parentheses, after the list item's main title. Usually used to add extra information. |
| children | React.ReactNode | No | The element to display directly inside the list item. Located below the main title and subtitle. |
| onClick | React.MouseEventHandler | No | Callback invoked when the list item is clicked / pressed. |
