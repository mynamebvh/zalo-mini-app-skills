# sendDataToPreviousMiniApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/routing/sendDataToPreviousMiniApp
> Last updated: 28/10/2026
> Supported from: SDK 2.13.0

```ts
import { sendDataToPreviousMiniApp } from "zmp-sdk";
```

Send data to the previous Zalo Mini App.
The previous Zalo Mini App needs to listen for the [OnDataCallback](https://docs.zaloplatforms.com/docs/MA/api/events#ondatacallback) event to receive the data.
If the API is called multiple times, the last data will be sent.

## Example

For example, there are 2 Zalo Mini Apps: A with id `2953132499190403100` and B with id `2953132499190403200`. For B to send data to A, we need to perform the following steps:

1. Listen for the [OnDataCallback](https://docs.zaloplatforms.com/docs/MA/api/events#ondatacallback) event in app A:

```ts
import { events, EventName } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};

events.on(EventName.OnDataCallback, callback);
```

2. Call the [openMiniApp](https://docs.zaloplatforms.com/docs/MA/api/routing/openMiniApp) API to navigate to app B:

```ts
import { openMiniApp } from "zmp-sdk/apis";

openMiniApp({
  appId: "2953132499190403200",
});
```

3. In app B, send data to app A:

```ts
import { sendDataToPreviousMiniApp } from "zmp-sdk/apis";

sendDataToPreviousMiniApp({
  data: "Success",
});
```

4. Close app B using the [closeApp](https://docs.zaloplatforms.com/docs/MA/api/routing/closeApp) API or press the button below:

![buttonCloseApp](https://docs.zaloplatforms.com/assets/MA/img/button-close-app.png)

5. After app B is completely closed, app A will receive the sent data

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| data | `any` | Yes | The data to send. |