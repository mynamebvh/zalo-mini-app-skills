# viewOAQr

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/viewOAQr
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { viewOAQr } from "zmp-sdk";
```

API that allows the app to display the OA's QR code.

## Example

Display the OA's QR code:

```ts
await viewOAQr({
  id: "765465772305886642",
  displayName: "Galaxy Cinema",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id of the OA. |
| displayName | `string` | No | Display name of the QR code. |