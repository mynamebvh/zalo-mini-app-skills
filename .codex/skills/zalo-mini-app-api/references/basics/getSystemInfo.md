# getSystemInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/basics/getSystemInfo
> Last updated: 28/10/2026
> Supported from: SDK 2.4.0

```ts
import { getSystemInfo } from "zmp-sdk";
```

API to retrieve system information about the device being used.

## Example

Get the version information:

```ts
const { version, apiVersion, zaloVersion } = getSystemInfo();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `SystemInfo` containing information about the system version, language, and theme.

### SystemInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| version | `string` | No | The version of this Zalo Mini App currently in use. |
| apiVersion | `string` | No | The version of the ZMP SDK currently in use. |
| zaloVersion | `string` | No | The version of the Zalo app on the device. |
| platform | `'android' \| 'iOS' \| 'wp' \| 'unknown' \| ''` | No | Operating system information of the device. |
| language | `string` | No | Display language of the device. |
| zaloLanguage | `string` | No | Display language of the Zalo app on the device. |
| zaloTheme | `string` | No | Current theme of the Zalo app on the device. |