# getAppInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/basics/getAppInfo
> Last updated: 28/10/2026

```ts
import { getAppInfo } from "zmp-sdk";
```

API to retrieve information about the current Zalo Mini App.

## Example

Get the current live name and version:

```ts
const { name, version } = await getAppInfo({});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<GetAppInfoReturns>` containing the current Zalo Mini App information.

### GetAppInfoReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| name | `string` | No | Zalo Mini App name. |
| description | `string` | No | Zalo Mini App description. |
| version | `string` | No | Current live version. |
| appUrl | `string` | No | Zalo Mini App share link. |
| qrCodeUrl | `string` | No | Zalo Mini App QR link. |
| logoUrl | `string` | No | Path to the Zalo Mini App logo image. |