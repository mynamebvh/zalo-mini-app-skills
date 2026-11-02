# getDeviceIdAsync

> Source: https://docs.zaloplatforms.com/docs/MA/api/basics/getDeviceIdAsync
> Last updated: 28/10/2026
> Supported from: SDK 2.20.0

```ts
import { getDeviceIdAsync } from "zmp-sdk";
```

API that returns the hashed Device ID string of the device. Different user accounts logged in on the same device and using the same Mini App (or Mini Apps that share the same Zalo App ID) will have the same Device ID value. If the Device ID cannot be obtained, the returned value is `unknown`.

## Example

Use in combination with `await`:

```ts
const deviceId = await getDeviceIdAsync();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<string>` containing the hashed Device ID string of the device.