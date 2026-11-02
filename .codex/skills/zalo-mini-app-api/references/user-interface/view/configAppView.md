# configAppView

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/configAppView
> Last updated: 28/10/2026
> Supported from: SDK 2.25.0, Android 23.02.01.r2, IOS 23.02.01.r2

```ts
import { configAppView } from "zmp-sdk";
```

API to customize the main interface components on the Mini App, including:

- Status bar
- Action bar
- Bottom Navigation (Android) / Safe Area Inset Bottom (iOS)

With the `configAppView` API, you can show/hide and customize the colors and display styles of the default components on the Mini App. See the descriptive images below to understand which components can be customized on your Mini App.

## Example

Change the action bar title:

```ts
configAppView({
  actionBar: {
    title: "Cart",
  },
});
```

To get a full-screen interface:

```ts
configAppView({
  hideAndroidBottomNavigationBar: true,
  hideIOSSafeAreaBottom: true,
  statusBarType: "transparent", // or "hidden"
  actionBar: {
    hide: true,
  },
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| headerColor | `string` | No | Color code, valid values are hexadecimal colors, for example `#000000`. |
| headerTextColor | `"white" \| "black"` | No | The color of the text and icons on the action bar and status bar. |
| statusBarType | `"normal" \| "hidden" \| "transparent"` | No | The display style of the status bar. (default: "normal") |
| hideAndroidBottomNavigationBar | `boolean` | No | Hide the navigation bar on Android. (default: false) |
| hideIOSSafeAreaBottom | `boolean` | No | Hide the safe area inset bottom bar on iOS. (default: false) |
| hide | `boolean` | No | Hide the action bar. |
| title | `string` | No | The title displayed on the action bar. |
| leftButton | `"back" \| "none"` | No | Customize the left navigation button of the action bar. Shows the back button by default. Pass `none` to hide the button. (default: "back") |
| textAlign | `"left" \| "center"` | No | Customize the position of the title displayed on the action bar. (default: "left") |