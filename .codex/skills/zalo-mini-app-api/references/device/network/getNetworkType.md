# getNetworkType

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/network/getNetworkType
> Last updated: 28/10/2026

```ts
import { getNetworkType } from "zmp-sdk";
```

API to retrieve the current network connection type.

## Example

Get the current network connection type:

```ts
const { networkType } = await getNetworkType();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<GetNetworkTypeReturns>` containing the current network connection type.

### GetNetworkTypeReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| networkType | `"none" \| "wifi" \| "cellular" \| "unknown"` | No | Current network connection type with the following values: - `none`: No network. - `wifi`: Wi-Fi network. - `cellular`: Mobile network (2g/3g/4g). - `unknown`: Unknown network (Android). |