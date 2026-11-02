# vibrate

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/vibrate
> Last updated: 28/10/2026
> Supported from: SDK 2.9.8

```ts
import { vibrate } from "zmp-sdk";
```

API that vibrates the device.

## Example

Vibrate the device for 500 milliseconds:

```ts
await vibrate();
```

Vibrate the device for 1 second:

```ts
await vibrate({
  type: "oneShot",
  milliseconds: 1000,
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `string` | No | Vibration type; currently only `oneShot` is supported. (default: "oneShot") |
| milliseconds | `number` | No | Vibration duration (in milliseconds). Can only be set on Android devices. (default: 500) |