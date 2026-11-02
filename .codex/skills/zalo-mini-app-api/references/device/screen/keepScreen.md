# keepScreen

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/screen/keepScreen
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { keepScreen } from "zmp-sdk";
```

API that allows the app to keep the screen on. For example: when playing a video. When exiting the app, this setting returns to the default to avoid keeping the screen always on.

## Example

Keep the screen on:

```ts
await keepScreen({
  keepScreenOn: true,
});
```

Turn off keep-screen mode:

```ts
await keepScreen({
  keepScreenOn: false,
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| keepScreenOn | `boolean` | Yes | Pass `true` to keep the screen on. Pass `false` to turn off this mode. |