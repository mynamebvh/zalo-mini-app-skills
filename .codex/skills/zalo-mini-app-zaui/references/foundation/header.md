# Header (Foundation)

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/foundation/header

Last updated: 28/10/2026

The Mini App header consists of the content area and the Mini App Control, such as the "menu" and "close" buttons. The header bar is displayed at the top of the screen.

---

There are 2 separate color options

- The title and icon cluster has the following color options: white, black
- The navigation bar has the following color options: unlimited

Note

Choose and combine the title/icon color and the action bar color appropriately to ensure sufficient contrast

**Black text, icon color**

---

![black text](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/black-text-header.png)

**White text, icon color**

---

![white text](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/white-text-header.png)


---

## Anatomy

The header bar consists of the following components:

- Left (back) button
- Title
- Mini App Control (fixed)

![anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/anatomy.png)


---

## Header bar container

By default, the Header bar container has a solid color. You can hide the header to replace it with a custom header; see the technical guide [here](https://docs.zaloplatforms.com/docs/MA/devtools/app-config)

![anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/transparent-header.png)

Note

You should not display an additional navigation bar below the default navigation bar (headers) of Zalo Mini App

![Dont Do](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-1.png)

If you customize by hiding the default header, make sure the content displayed matches the height of the header bar

![Dont Do](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-2.png)


---

## Left Button

You can add navigation components in this area, usually a "back" button — it should only be added on secondary pages

![Left Button](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/left-button.png)

Note

Avoid displaying a "home" button in this area.

![Home Button](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-home-button.png)


---

## Title

The title is typically used for the following purposes:

- Display the name of the screen
- Display the current function
- Display the Mini App name

The title should be concise, easy to understand, and optimized to be fully visible

![Title](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/dont-do-title.png)


---

## Mini App Control

Mini App Control is a default component of the Mini App. Users can use it to open the Mini App menu or close the Mini App.

![Title](https://docs.zaloplatforms.com/assets/MA/img/zaui/header/mini-app-control.png)
