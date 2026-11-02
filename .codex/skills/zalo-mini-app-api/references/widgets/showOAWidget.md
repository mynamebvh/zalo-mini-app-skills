# showOAWidget

> Source: https://docs.zaloplatforms.com/docs/MA/api/widgets/showOAWidget
> Last updated: 28/10/2026
> Supported from: SDK 2.38.0

```ts
import { showOAWidget } from "zmp-sdk";
```

Follow OA Widget: When the user taps the "Follow" button on the widget, they will follow immediately without displaying a permission request bottom sheet. The OA information is taken from the OA that verified the Mini App.

| User has not followed the OA | User has followed the OA |
| --- | --- |
| Zalo OA Widget | Zalo OA Widget |

## Example

Display the Follow OA Widget:

```ts
import React, { useEffect } from "react";
import { showOAWidget } from "zmp-sdk/apis";

function HomePage() {
  useEffect(() => {
    showOAWidget({
      id: "oaWidget",
      guidingText: "Receive the latest promotion notifications from the store",
      color: "#0068FF",
      onStatusChange: (status) => {
        console.log(status);
      },
    });
  }, []);

  return (
    <>
      ...
      <div id="oaWidget" />
      ...
    </>
  );
}

export default HomePage;
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | The ID of the element where the widget should be displayed. |
| guidingText | `string` | No | The string used to notify the user. (default: "Receive the latest promotion notifications from the store") |
| color | `string` | No | The primary color of the widget. The value must be a hex string. (default: "#0068FF") |
| onStatusChange | `(status: boolean) => void` | No | Callback called when the user taps to follow the OA. The new follow status is passed into the callback's parameter. |