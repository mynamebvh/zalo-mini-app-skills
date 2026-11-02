# ActionSheet

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/overlay/ActionSheet

Last updated: 28/10/2026

```ts
import { Sheet } from "zmp-ui";
const { Action } = Sheet;
```

Used to display a list of actions the user can choose from, in the form of a [Sheet](https://docs.zaloplatforms.com/docs/MA/zaui/overlay/Sheet).


## Props

### ActionSheetProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| divider | boolean | No | Displays a divider between action buttons (default: `false`) |
| actions | ActionButton[] \| ActionButton[][] | No | Array configuring the action buttons. Actions can be grouped by declaring multiple action arrays, with related actions in the same array. |
| groupDivider | boolean | No | Displays a divider between action groups (default: `false`) |

### ActionButton

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| text | string | No | The text on the action button. |
| highLight | boolean | No | Displays the action as a highlight button (default: `false`) |
| danger | boolean | No | Displays the action as a danger button (default: `false`) |
| onClick | (e: React.MouseEvent) => void | No | Callback invoked when the user clicks on the action. |
| close | boolean | No | This action specifies whether to close the sheet when clicked (default: `false`) |
| disabled | boolean | No | The disabled state of the action. (default: `false`) |
| key | string | No | The identifying key of the action. |
