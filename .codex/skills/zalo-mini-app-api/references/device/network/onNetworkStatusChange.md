# onNetworkStatusChange

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/network/onNetworkStatusChange
> Last updated: 28/10/2026

```ts
import { onNetworkStatusChange } from "zmp-sdk";
```

Callback to listen for network change events.

## Example

Listen for network change events:

```ts
onNetworkStatusChange(function (data) {
  const { isConnected, networkType } = data;
  console.log(`Network connection: ${isConnected}, Network type: ${networkType}`);
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass a callback function directly to the API:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| callback | `(data: NetworkStatusChangeData) => void` | Yes | Callback function that is called when the network changes. |

### NetworkStatusChangeData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| isConnected | `boolean` | No | Network connection status. |
| networkType | `"none" \| "wifi" \| "cellular" \| "unknown"` | No | Current network connection type with the following values: - `none`: No network. - `wifi`: Wi-Fi network. - `cellular`: Mobile network (2g/3g/4g). - `unknown`: Unknown network (Android). |