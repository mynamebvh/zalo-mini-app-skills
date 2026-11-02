# Events

> Source: https://docs.zaloplatforms.com/docs/MA/api/events
> Last updated: 28/10/2026
> Supported from: SDK 2.13.0

> **Note**
>
> Starting from API version 2.25.2, `EventName` is added as an alias of `Events` for clearer naming; `Events` continues to be exported.

## API

### on(eventName, listener)

- eventName <string>: The name of the event
- listener <Function>: The event handler function

Adds a function to the end of the array of existing handler functions for the event named **eventName**. When the event occurs, all handler functions for that event are called.

```js
import { events, EventName } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};
events.on(EventName.NetworkChanged, callback);
```

### once(eventName, listener)

- eventName <string>: The name of the event
- listener <Function>: Callback function

Adds a one-time handler function for the event named **eventName**. When the event occurs, this handler is removed and then executed.

```js
import { events, EventName } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};
events.once(EventName.NetworkChanged, callback);
```

### off(eventName, listener)

- eventName <string>: The name of the event
- listener <Function>: Callback function

Removes a specific handler function from the event's array of handler functions for the event named **eventName**

```js
import { events, EventName } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};

events.on(EventName.NetworkChanged, callback);

// ...

events.off(EventName.NetworkChanged, callback);
```

### removeAllListeners(eventName)

- eventName <string>: The name of the event

Removes all handler functions for the event named **eventName**

```js
import { events, EventName } from "zmp-sdk/apis";

events.removeAllListeners(EventName.NetworkChanged);
```

## Events

Zalo Mini App supports the following events:

### AppPaused

This event occurs when Zalo Mini App moves from foreground to background

```js
import { events, EventName } from "zmp-sdk/apis";

events.on(EventName.AppPaused, () => {
  console.log("App paused");
});
```

### AppResumed

This event occurs when Zalo Mini App moves from background to foreground

```js
import { events, EventName } from "zmp-sdk/apis";

events.on(EventName.AppResumed, () => {
  console.log("App resumed");
});
```

### NetworkChanged

This event occurs when a network change is detected on the device

```js
import { events, EventName } from "zmp-sdk/apis";

events.on(EventName.NetworkChanged, (data) => {
  const { state } = data;
  console.log("Network State:", state);
});
```

### OnDataCallback

This event occurs when data is received from the [sendDataToPreviousMiniApp](https://docs.zaloplatforms.com/docs/MA/api/routing/sendDataToPreviousMiniApp) API

```js
import { events, EventName } from "zmp-sdk/apis";

events.on(EventName.OnDataCallback, (data) => {
  console.log("Callback data:", data);
});
```

### OpenApp

> Supported from:
>
> - API version: 2.16.0
> - IOS: 22.02.01
> - Android: 22.03.02

When the Mini App is running in background mode (not fully closed) and is reopened through entry points such as links, QR codes, etc., the [OpenApp](#openapp) event will
occur, and the received value is the path of that entry point.

```js
import { events, EventName } from "zmp-sdk/apis";

events.on(EventName.OpenApp, (data) => {
  console.log("Callback data:", data.path);
});
```

### WebviewClosed

> Supported from:
>
> - API version: 2.30.0

This event occurs when a webview opened from the Mini App is closed.

```js
import { events, EventName } from "zmp-sdk/apis";

events.on(EventName.WebviewClosed, () => {
  console.log("WebviewClosed");
});
```
