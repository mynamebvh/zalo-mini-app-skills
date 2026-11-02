# createShortcut

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/createShortcut
> Last updated: 28/10/2026
> Supported from: SDK 2.16.1

```ts
import { createShortcut } from "zmp-sdk";
```

API that allows the app to create a shortcut on the home screen.

### Shortcut creation process on Android

![shorcut android](https://docs.zaloplatforms.com/assets/images/shortcut-android-316d3f0da0ad419330ed9d12fc858dfb.png)

Note: different params will create different shortcuts

### Shortcut creation process on iOS

![shorcut ios](https://docs.zaloplatforms.com/assets/images/shorcut-ios-e3dd37062cec1ba92eb70e1ae6353a0e.png)

## Example

Create a simple shortcut:

```ts
await createShortcut();
```

Create a shortcut with params:

```ts
await createShortcut({
  params: {
    utm_source: "shortcut",
  },
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| params | `Record<string, string>` | No | The params to add to the Zalo Mini App when it opens.. |