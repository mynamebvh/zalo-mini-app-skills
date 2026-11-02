# scanQRCode

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/qr/scanQRCode
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { scanQRCode } from "zmp-sdk";
```

Allows the app to open the QR Code scanning feature of the Zalo app and returns the result after the user scans successfully.

## Example

Get the content of the scanned QR

```ts
const { content } = await scanQRCode({});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<ScanQRCodeReturns>` containing an object whose `content` property is the content of the scanned QR.