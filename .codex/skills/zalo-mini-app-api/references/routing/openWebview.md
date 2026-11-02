# openWebview

> Source: https://docs.zaloplatforms.com/docs/MA/api/routing/openWebview
> Last updated: 28/10/2026
> Supported from: SDK 2.11.0

```ts
import { openWebview } from "zmp-sdk";
```

Loads a web page using Webview.
To know when the Webview is closed, please listen for the [WebviewClosed](https://docs.zaloplatforms.com/docs/MA/api/events#webviewclosed) event.

## Example

Open the Zalo Mini App homepage:

```ts
openWebview({
  url: "https://mini.zalo.me",
});
```

Open the Zalo Mini App homepage in full screen:

```ts
openWebview({
  url: "https://mini.zalo.me",
  config: {
    style: "normal",
  },
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| url | `string` | Yes | URL of the web page to load. |
| style | `"bottomSheet" \| "normal"` | No | Display style of the Webview: (default: "bottomSheet") |
| leftButton | `"back" \| "none"` | No | Left button of the header bar: (only supported for style 'bottomSheet') (default: "back") |