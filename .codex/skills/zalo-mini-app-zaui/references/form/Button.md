# Button

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/form/Button

Last updated: 28/10/2026

```ts
import { Button } from "zmp-ui";
```

Used to create buttons that help users interact to perform an action.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| variant | 'primary' \| 'secondary' \| 'tertiary' | No | The variant type of the button. It can take one of the following values:<br>- `primary`: Primary button, has a dark color and highlights important actions<br>- `secondary`: Secondary button, lighter color to focus the user's attention on other actions that are more important<br>- `tertiary`: Tertiary button, has a white color and is usually used for actions less important than the secondary button (default: `'primary'`) |
| loading | boolean | No | Show loading icon (default: `false`) |
| disabled | boolean | No | Disabled state (default: `false`) |
| children | React.ReactNode | No |  |
| type | 'highlight' \| 'danger' \| 'neutral' | No | The action type of the button. It can take one of the following values:<br>- highlight: Has the primary color, making the button stand out from other components in the app<br>- danger: Has a red color, emphasizing that the button's action may lead to important or dangerous consequences<br>- neutral: Has a white color, neutral with other components in the app (default: `'highlight'`) |
| htmlType | 'submit' \| 'button' \| 'reset' | No | The default `type` attribute of the `<button>` tag (default: `'button'`) |
| size | 'large' \| 'medium' \| 'small' | No | The size of the button. (default: `'medium'`) |
| fullWidth | boolean | No | If enabled, the button will have a width of 100% of its container. (default: `false`) |
| prefixIcon | React.ReactNode | No | Add a prefix icon |
| suffixIcon | React.ReactNode | No | Add a suffix icon |
| icon | React.ReactNode | No | Add an icon to the button |

## Design guidelines

##### Button

Button represents an action that the user can perform on the UI.

---

###### Anatomy

![anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/anatomy.png)

| Element | Description |
| --- | --- |
| 1. Leading Icon | Optional |
| 2. Text | Optional |
| 3. Trailing Icon | Optional |
| 4. Container | Optional |

---


###### **Label Button**

Button represents an action that the user can perform on the UI.

![Label Button](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/label-button.png)

###### **Icon Button**

A button type that contains only an icon.

![Icon Button](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/icon-button.png)

---


###### **Levels**

Button has 3 levels: Primary, Secondary, Tertiary

![Button Levels](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/icon-button.png)

**Primary Button**

![Button Primary](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/primary-button.png)

**Secondary Button**

![Button Secondary](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/secondary-button.png)

**Tertiary Button**

![Button Tertiary](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/tertiary-button.png)

###### **Sizes**

Button has 3 sizes: Large, Medium, Small

![Button Size](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/button-size.png)

###### **States**

Button has 3 states:

1. Pressed: Represents the state when the user presses and holds the button
2. Loading: Represents the state of an action being performed
3. Disabled: Represents the state where the button is unavailable at the time the user is using it

**Primary Button**

![Button State](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/primary-state.png)

**Secondary Button**

![Button State](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/secondary-state.png)

**Tertiary Button**

![Button State](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/tertiary-state.png)

---

###### **Usage**

**LABEL BUTTON**

A button that contains text and may come with an icon, commonly used for:

- Confirmation-type actions
- Actions of high importance

---

**ICON BUTTON**

A button that contains only an icon, commonly used for:

- Supplementary actions
- Less important actions

---

###### **Sizes**

**LARGE**

Use Large size when the Button is on a page

Note

Also use a divider when the Button is docked to the bottom of the screen

![Button Large](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/large-size.png)

---

**SMALL**

Use Small size when the Button is inside a small section or a UI element of small size

![Button Small](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/small-size.png)

---

###### **Floating Action Button**

The Button is used floating on the UI, commonly docked to the top or bottom of the screen.

![Button FAB](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/floating-button.png)

---

###### **Button Group**

Button Group is a group of Buttons together

- Only one Primary Button in a Button Group
- Ensure contrast in importance between the Buttons

**DIRECTION**

Button Group has 2 directions:

- Horizontal: Primary Button is always on the right
- Vertical: Primary Button is always at the top

![Button Group](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/group-button.png)

---

###### **Specs**

**General Specs**

![General Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/general-specs.png)

**Overall Specs**

![Overal Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/overal-specs.png)

**Button Group**

![Overal Specs](https://docs.zaloplatforms.com/assets/MA/img/zaui/button/button-group-specs.png)
