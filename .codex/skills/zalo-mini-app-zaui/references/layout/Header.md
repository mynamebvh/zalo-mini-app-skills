# Header

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/layout/Header

Last updated: October 28, 2026

```ts
import { Header } from "zmp-ui";
```

Used to display fixed information at the top of the screen.

Tips

There are 2 types of header in Zalo Mini App:

- **Native header**: displayed by the Zalo app, configured via `app-config.json`, and cannot be customized within the Mini App.
- **Header component** (the one on this page): content and colors can be customized and extended with React/CSS. New Mini Apps use this type by default.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| backIcon | ReactNode | No | Customizes the back button at the start of the header. If not passed in, the default back button is used. |
| showBackIcon | boolean | No | Whether to show the back button at the start of the header. (default: `true`) |
| onBackClick | (e: React.MouseEvent) => void | No | Callback called when the back button is clicked. |
| backgroundColor | string | No | Background color of the header. |
| textColor | string | No | Text color of the header. |
| title | string | No | Title of the header. |

## Design guidelines

##### Header

The Mini App header consists of the content area and the Mini App Control, such as the "menu" and "close" buttons. The header bar is displayed at the top of the screen.

---

There are 2 distinct color options

- The title and icon group has color options: white, black
- The navigation bar has color options: unlimited

Note

Choose and combine the title/icon colors and the action bar color correctly to ensure sufficient contrast.

**Black text, icon color**

---

![black text](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/black-text-header.png)

**White text, icon color**

---

![white text](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/white-text-header.png)

---

###### Anatomy

The header bar consists of the following elements:

- Left (back) button
- Title
- Mini App Control (fixed)

![anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/anatomy.png)

---

###### Header bar container

By default, the header bar container has a solid color. You can hide the header and replace it with a custom header; see the technical guide [here](https://docs.zaloplatforms.com/docs/MA/devtools/app-config).

![anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/transparent-header.png)

Note

Do not display an additional navigation bar below the default navigation bar (header) of the Zalo Mini App.

![Dont Do](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-1.png)

If you customize and hide the default header, make sure content is displayed appropriately for the header bar's height.

![Dont Do](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-2.png)

---

###### Left Button

You can add a navigation element in this area, usually a "back" button — it should only be added on secondary pages.

![Left Button](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/left-button.png)

Note

Avoid displaying a "home" button in this area.

![Home Button](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-home-button.png)

---

###### Title

Titles are commonly used for the following purposes:

- Display the name of the screen
- Indicate the current feature
- Display the Mini App name

Titles should be concise, easy to understand, and optimized to be displayed in full.

![Title](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-title.png)

---

###### Mini App Control

Mini App Control is a default part of the Mini App. Users can use it to open the Mini App menu or close the Mini App.

![Title](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/mini-app-control.png)
