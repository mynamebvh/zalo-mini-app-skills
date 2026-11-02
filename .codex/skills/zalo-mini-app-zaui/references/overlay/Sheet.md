# Sheet

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/overlay/Sheet

Last updated: 28/10/2026

```ts
import { Sheet } from "zmp-ui";
```

Used to display supplementary information or let the user perform some secondary actions related to the main content on the screen, continuing to use a feature of the application

## Usage


### Props

#### SheetProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| mask | boolean | No | The mask is a gray overlay layer covering the components below the picker's dialog, preventing the user from interacting with that content and focusing on the open dialog. (default: `true`) |
| afterClose | () => void | No | Callback invoked after the sheet is closed. |
| onClose | (e: React.SyntheticEvent) => void | No | Callback invoked when the user requests to close the sheet. The value of `visible` must be updated if it is passed in this callback. |
| maskClosable | boolean | No | Allows the sheet to close automatically when clicking on the mask. (default: `true`) |
| visible | boolean | No | The open or closed state of the sheet.<br>Must be used together with `onClose` to update the value of `visible` when the user requests to close the sheet; otherwise the sheet will not be able to close. (default: `false`) |
| title | string | No | The title of the sheet, displayed at the top. |
| modalStyle | React.CSSProperties | No | Inline style of the sheet. |
| maskStyle | React.CSSProperties | No | Inline style of the mask. |
| modalClassName | string | No | CSS class of the sheet. |
| maskClassName | string | No | CSS class of the mask. |
| width | string \| number | No | The width of the sheet. If not set, the sheet will have a default width of the full screen. |
| height | string \| number | No | The height of the sheet. If not set, the sheet will have a default height based on the content. |
| children | React.ReactNode | No | The content to display inside the bottom sheet. |
| zIndex | number | No | The depth of the sheet, used to determine the display order of the sheet relative to other floating elements, if any. |
| handler | boolean | No | The sheet handler is a horizontal black bar at the top of the sheet, used to drag the sheet up or down. (default: `true`) |
| autoHeight | boolean | No | Automatically adjusts the sheet's height according to the content. (default: `false`) |
| contentRef | React.MutableRefObject | No | A reference to the sheet's content container element in the DOM tree. |
| swipeToClose | boolean | No | Allows the user to close the sheet by swiping down on the sheet's content. (default: `true`) |
| snapPoints | number[] \| ((props: { sheetModalHeight: number }) => number[]) | No | Declares the sheet's snap points. Snap points are the points at which the sheet will stop when the user drags it up or down. The number of snap points is unlimited.<br>Each snap point has a value from 0 to 1, where 0 is when the sheet is fully open and 1 is when the sheet is fully closed. In addition to passing a snap point as a fixed number, functions for calculating snap points based on the sheet's height can also be passed in.<br>The number of snap points is unlimited. |
| defaultSnapPoint | number | No | The default snap point when opening the sheet. The value is passed as an index in the `snapPoints` array. |
| onSnap | (snapPoint: number) => void | No | Callback invoked when the sheet snaps to a new snap point. |
| unmountOnClose | boolean | No | By default, when the user closes the sheet, its interface is still rendered in the DOM and is only hidden. This setting allows the sheet to be completely removed from the DOM tree after closing.<br>This setting can help reduce memory usage when the sheet has large content. However, when the sheet is reopened, all content will have to be rendered again from scratch. (default: `false`) |

#### SheetContentProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| title | string | No | The title of the sheet, displayed at the top. |
| children | React.ReactNode | No | The content to display inside the bottom sheet. |
| ariaId | string | No |  |
| onVisibleChanged | (visible: boolean) => void | No | Callback invoked when the display state of the sheet changes. |
| onMouseDown | React.MouseEventHandler | No |  |
| onMouseUp | React.MouseEventHandler | No |  |
| modalRef | React.MutableRefObject | No | A reference to the sheet's content container element in the DOM tree. |

#### SheetRef

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| snapTo | (snapPoint: number) => void | No | Function used to snap to a declared snap point. See more about `Sheet`'s snapPoints. |
| sheet | HTMLDivElement | No | Points to the sheet's element in the DOM tree |

## Design guidelines

##### Sheet

The Sheet is a container for supplementary items and content, anchored at the bottom of the screen, and the content inside can be laid out as a list, carousel, or grid. The Items and content can include text, image, icon, button, selections, and so on...

---

###### Usage

- Need a list of options or extended settings
- Need a panel that displays supplementary content, but can later be expanded or collapsed on the screen

---


###### Display

The bottom sheet has 3 display levels; the Initial appearance is required, and depending on the usage needs the sheet will additionally have the expand and collapse levels

- **Initial appearance (Required)**: The initial height when the sheet has just been opened
- **Expanded sheet (Optional)**: The maximum height of the sheet after being expanded
- **Collapsed sheet (Optional)**: The minimum height of the sheet after being collapsed
- **compact Limit level** = Screen height - Status Bar

![Bottom Sheet Display](https://docs.zaloplatforms.com/assets/images/bottom-sheet-display-05694cad05862634792f538a70a09b43.png)

---

Display

Initial appearance

•
To ensure the main content can be interacted with again, when starting to open:

• Default sheet height = 50% screen height

• Depending on the case, sheet height = custom (% screen height)

•

You can choose sheet height = hug content (in this case, there cannot be
expand/collapse forms)

•
Scrolling inside is not allowed until it reaches the
limit level

**Expanded sheet**

- Taller than when it was just opened, and is the maximum height:
  - Default max height = Screen height - Status Bar (limit level)
  - Depending on the case, sheet height = custom (% screen height)

**Collapsed sheet**

- Can or cannot be dismissed depending on the usage needs
- Can add a Button to expand back to the initial size
- Default collapsed height = 20% screen height
- Depending on the case, collapsed height = custom (% screen height)

**Hidden sheet**

- The Sheet still exists but does not appear on the screen

###### Anatomy

The Content and components on the Header can change depending on the case:

- Message Reaction
- Post Reaction & Comment
- Menu Actions
- Login History
- Message
- Phonebook
- Post
- Selection List
- ...

  ![Anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/sheet/anatomy.png)

---

###### Specs

![Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/sheet/specs.png)

Padding and spacing

- Padding top = 10px
- Padding left, right, bottom = 16px
- Spacing from handle to header = 8px
- Spacing from header to content = 16px
- If the content already has padding
  - Sheet padding = 0px
  - Spacing from header to content = 0px
- Radius = 16px

---


###### Supplementary Bottom Sheet

**Usage**

- Helps display supplementary items or content for the main content of the screen, while the user can still interact with the main content.

**Behavior**

- Cannot be dismissed when interacting with the main content
- Should not be opened from another Bottom Sheet

![Supplementary](https://docs.zaloplatforms.com/assets/MA/img/zaui/sheet/sheet-supplementary.png)


###### Supplementary Bottom Sheet

**Usage**

- Helps display a panel with interactions, or longer descriptive content. Will be dismissed when interacting with the main content.

**Behavior**

- Always dismissed when interacting with the main content
- Can never collapse

![Supplementary Bottom Sheet](https://docs.zaloplatforms.com/assets/MA/img/zaui/sheet/modal-sheet.png)

###### List Bottom Sheet

- List Bottom Sheet is used to replace the native sheet from Android and iOS

**Display**

- Sheet height = hug content
- No expand or collapse state
- Padding bottom = 32px

**Type**

- **Default List**: Used when the lists are of normal options or settings
- **Section List**: Used when the lists are divided into multiple sections

  ![List Bottom sheet](https://docs.zaloplatforms.com/assets/MA/img/zaui/sheet/list-bottom-sheet.png)
