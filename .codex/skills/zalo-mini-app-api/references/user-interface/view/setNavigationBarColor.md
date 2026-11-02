# setNavigationBarColor

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarColor
> Last updated: 28/10/2026

```ts
import { setNavigationBarColor } from "zmp-sdk";
```

API that sets the navigation bar color of the current page.

## Example

Change the navigation bar color to black:

```ts
setNavigationBarColor({
  color: "#000000",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| color | `string` | Yes | Color value, valid values are hexadecimal colors, for example `#000000`. If this value is empty, the navigation bar will be hidden. |
| textColor | `"black" \| "white"` | No | The color of the text and icons on the action bar and status bar. On iOS devices, only the icon color on the action bar can be changed. |
| statusBarColor | `string` | No | The color of the status bar when the navigation bar is hidden, valid values are hexadecimal colors, for example `#000000`. |