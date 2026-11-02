# Modal

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/overlay/Modal

Last updated: 28/10/2026

```ts
import { Modal } from "zmp-ui";
```

Used to display important content or require the user to perform a specific action before continuing to use the application's features.

## Usage


### Props

#### ModalProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| mask | boolean | No | The mask is a gray overlay layer covering the components below the dialog, preventing the user from interacting with that content and focusing on the open dialog. (default: `true`) |
| afterClose | () => void | No | Callback invoked after the dialog closes |
| onClose | (e: React.SyntheticEvent) => void | No | Callback invoked when the user requests to close the dialog. The value of `visible` must be updated if provided. |
| maskClosable | boolean | No | Allows closing the dialog when clicking on the mask. (default: `true`) |
| visible | boolean | No | The display state of the dialog. Must be used together with `onClose` to update the value of `visible` when the user requests to close the dialog. (default: `false`) |
| title | string | No | The title of the dialog, displayed at the top of the dialog. |
| coverSrc | string | No | The path to the dialog's cover image |
| modalStyle | React.CSSProperties | No | Inline style for the dialog |
| maskStyle | React.CSSProperties | No | Inline style for the mask |
| modalClassName | string | No | CSS class for the modal |
| maskClassName | string | No | CSS class for the mask |
| width | string \| number | No | The width of the dialog. If not set, the modal will have a default width based on the content's width and the screen width. |
| height | string \| number | No | The height of the dialog. If not set, the modal will have a default height based on the content's height and the screen height. |
| description | string | No | The content of the dialog, displayed below the title. If the content to display is not text, use `children` to pass a ReactNode instead of `description`. |
| actions | ModalActions[] | No | Array configuring the buttons for the user to perform actions on the dialog. |
| verticalActions | boolean | No | Displays the actions vertically, instead of the default horizontal layout. (default: `false`) |
| children | React.ReactNode | No | The content of the dialog, displayed below the description and above the actions. |
| actionsDivider | boolean | No | Displays a divider between the actions. (default: `false`) |
| zIndex | number | No | The depth of the dialog, used to determine the display order of the dialog when multiple modals are open at the same time. |
| unmountOnClose | boolean | No | By default, when the user closes the dialog, the modal is still rendered in the DOM and is only hidden. This setting allows the dialog to be completely removed from the DOM tree after closing.<br>This setting can help reduce memory usage when the dialog has large content. However, when the dialog is reopened, its content will be rendered again from scratch. Suitable for dialogs that are only used once. (default: `false`) |

#### ModalActions

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| text | string | No | The text on the button |
| highLight | boolean | No | Displays the action as a highlight button (default: `false`) |
| danger | boolean | No | Displays the action as a danger button (default: `false`) |
| onClick | (e: React.MouseEvent) => void | No | Callback invoked when the action is clicked |
| close | boolean | No | If set to `true`, the action will close the modal when clicked (default: `false`) |
| disabled | boolean | No | The active state of the action (default: `false`) |
| key | string | No |  |

## Design guidelines

##### 1. Information Dialog

Dialog:

- Asks the user to verify whether they want to continue or cancel the action
- Displays information the user needs to know

The dialog, along with a dim background, interrupts before the system executes the user's command

Note: Max number of stacking modals = 2

---

###### Components

![Modal light](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-light.png)![Modal dark](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-dark.png)

---

###### Anatomy

![Modal Anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-anatomy.png)

- 1

  Container

- Required

- 2

  Custom View

- Optional
- Can be freely edited within this view

- 3

  Main Items

- Required
- Include
- Title
- Description

![Modal main items](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-main-content.png)![Modal title](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-title.png)![Modal description](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-desc.png)

- 4

  Add-on Items

- Optional
- Can be these items

![Modal Add-on](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/add-on.png)

- 5

  Divider

- Required

- 6

  Action

- Required
- Display:

- Default: 1 primary action (blue or red)
- Optional: add up to 2 secondary actions

- Position:

- Default: horizontal
- If the text is long and the horizontal space is insufficient -> switch to vertical

- 7

  7. Dim Background

- Required

###### Specs

Max height of dialog = 80% screen height

![Overal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/specs-overal.png)![Content](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/specs-content.png)![Actions](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/specs-actions.png)

---


###### Dismiss

The user can dismiss the Modal by

- **Tap out to dismiss** (tapOutsideToDismiss)
  - Can be ON/OFF
  - Default = ON
- **Tap dismissive button** (passed in from outside)

**Focused Text Input with keyboard**

**Case 1**
The Modal is pushed up above the keyboard

- The Modal is 16px from the keyboard

![Modal Focus Input](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-input-focus-1.png)

**Case 2**
The Modal has been pushed up and has reached the status bar, but there is not enough room to push the full modal

- The Content area becomes a Scrollview
- The Focused Text Input is 32px from the keyboard

![Modal Focus Input](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-input-focus-2.png)

**Conditions for closing the keyboard**

Satisfy one of the following conditions:

- When the user taps on any area within the InformationDialog, outside the InputFields
- When the user dismisses the InformationDialog

\*When the user scrolls within the InformationDialog, the keyboard does not close.

---


###### Confirmation Dialog

**Normal**

The dialog appears after the user selects any action that needs to be confirmed before the action is performed

![Modal Normal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-normal.png)![Modal Normal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-normal-2.png)![Modal Normal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-normal-3.png)

**Danger**

The dialog appears after the user selects a destructive action (Delete, Exit, Recall, Log out, and so on) that needs to be confirmed before the action is performed

![Danger](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-danger-1.png)![Danger](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-danger-2.png)![Dabger](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-danger-3.png)

**Text Input**

The dialog appears after the user selects an action that then requires entering information to continue the process of performing the action

![With Input](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-input.png)![With Input](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/modal-input-2.png)

##### 2. Promotion Popup

- The dialog is used for the purpose of promoting, introducing, and onboarding new features
- Should be used in the right context because the level of interruption is very high

---

###### Components

![Promotion modal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-1.png)![Promotion modal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-1-dark.png)![Promotion modal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-2.png)![Promotion modal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-2-dark.png)![Promotion modal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-3.png)![Promotion modal](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-3-dark.png)

---

###### Anatomy

![Promotion modal specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-specs.png)

- 5

  Container

- Required

- 6

  Content View

- Required

- 7

  Action

- Required
- Display
- Default: 1 primary button (blue)
- Optional: add up to 1 secondary button

- 8

  Dim Background

- Required

**Content View**

Consists of 2 parts:

- Content Page
- Page Indicator

![Promotion modal content view](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-content-view.png)

- 1

  Content Page

- Required
- Consists of 2 types:

- 1. Custom (vertical, freely custom content)
- 2. Default

![Promotion modal content view](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-content-default.png)

- 1

  Image View

- Required

- 2

  Title

- Required
- No line limit
- Font-size: h-normal

![Promotion modal content view](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-title.png)

- 3

  Description

- Required
- Number of text rows

- Design: maximum 3 rows

- 1 text row: do not use an icon
- 2 - 3 text rows: use an icon as a bullet point

- Dev: can add multiple

- Font-size: t-normal

![Promotion modal content view](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-desc.png)

- 2

  Page Indicator

- Used when 2 or more content pages are passed in

---

###### Specs

Max height of dialog = **80% screen height**

![Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-specs.png)![Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-specs-content.png)

**Content Page**

**1. Custom (Vertical, freely custom)**

Recommended spacing specs

![Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-specs-custom.png)

**2. Default**

![Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-specs-default.png)

Actions

![actions](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-specs-actions.png)

---


###### Behavior

The user can dismiss the Modal by

- **Tap out to dismiss** (maskClosable)
  - Can be ON/OFF
  - Default = OFF
- **Press the dismissive button** (passed in from outside)

###### Scroll

When the Modal contains content that exceeds the max height, a scrollbar should be displayed.
Animation: use the native ScrollView

Scrollbar Specs

![Scrollbar](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/pr-modal-scrollbar.png)

---

###### Usage

**Transparent background**

![Transparent Background](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/usage-transparent-bg-1.png)![Transparent Background](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/usage-transparent-bg-2.png)

**Filled background**

![Filled Background](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/usage-filled-bg-1.png)![Filled Background](https://docs.zaloplatforms.com/assets/MA/img/zaui/modal/usage-filled-bg-2.png)
