# BottomNavigation

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/layout/BottomNavigation

Last updated: October 28, 2026

```ts
import { BottomNavigation } from "zmp-ui";
```

Used to display a fixed navigation bar at the bottom of the screen. Helps users easily navigate to other pages.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| activeKey | string | No | Specifies which tab is currently selected to display the corresponding content \_(active tab)\_.<br>Must be used together with `onChange` to update the value. |
| onChange | (activeKey: string) => void | No | Handles the event when the selected tab changes. The value of `activeKey` must be updated if it is passed in. |
| defaultActiveKey | string | No | Specifies which tab is selected by default when the component is displayed.<br>\_Note: Changing `defaultActiveKey` after the component has rendered has no effect.\_ |
| children | ReactNode | No |  |
| fixed | boolean | No | Keeps `BottomNavigation` fixed at the bottom of the app and does not scroll with the content. (default: `false`) |
| zIndex | number | No | Determines the display order (`z-index`) of the BottomNavigation component relative to other elements that may overlay on the app. |

## Design guidelines

##### BottomNavigation

Bottom Navigation helps users move between primary content areas within an app.

---

###### Usage

Helps navigate to the app's **primary content**

- Has 4-6 items
- The icon and label on each item represent primary content

---

###### Behavior

- Always opens the first item when the app starts
  Only one item is open at a time
- Bottom Navigation behaves the same on both Android and iOS instead of using the platform's default behavior. When switching to a primary content area, it goes to the position the user previously interacted with. If the user previously interacted or navigated to a detail page such as scrolling, opening a bottom sheet, opening a page, selecting a tab, and so on, that state is preserved when the user returns. (In some cases the interaction is reset and the user is taken to the first position of the primary content.)
- Navigation can be changed when needed to improve the user experience. The user can be taken back to the first position (or have the scroll position reset, or the first tab reset) if that is better for the experience.
  When moving within a primary content area, from the first position to more detailed pages, the bottom navigation can be kept to enable better navigation.
- First position: the initially displayed screen. The state before any interaction has been performed (for example, scrolling, opening a bottom sheet, opening a detail page, switching tabs, and so on).

---

###### Anatomy

Bottom Navigation includes a Badge in the top-right corner of the icon.

![white text](https://docs.zaloplatforms.com/assets/MA/img/zaui/bottom-navigation/anatomy.png)

- 1

  Container

- Required

- 2

  Icon

- Required

- 3

  Label

- Required
- Text

- 4

  Badge

- Optional

- 5

  Divider

- Required

###### Specs

![white text](https://docs.zaloplatforms.com/assets/MA/img/zaui/bottom-navigation/specs.png)

**Padding and spacing**

- Padding left, right = 4px
- Padding top = 4px
- Padding bottom = 2px
- Spacing = 2px
- The Badge is always located in the top-right corner of the Icon and creates an intersection area
  - The intersection area has w = 6px, h = 16px
  - The Badge is anchored to the top-left corner of the intersection area
