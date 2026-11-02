# showToast

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/interative/showToast
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { showToast } from "zmp-sdk";
```

API that displays a short notification on the screen.

## Example

Show a successful order notification:

```ts
showToast({
  message: "Order placed successfully!",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| message | `string` | Yes | The content of the notification to display. |