# getStorageInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/native-storage/getNativeStorageInfo
> Last updated: 28/10/2026
> Supported from: SDK 2.43.0

```ts
import { nativeStorage } from "zmp-sdk";
```

Gets information about the cache using the synchronous mechanism.

## Example

```ts
const { currentSize, limitSize } = nativeStorage.getStorageInfo();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

The API returns `StorageInfo` containing information about the cache.

### StorageInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| currentSize | `number` | No | Currently occupied space (in KB) |
| limitSize | `number` | No | Size limit of the space (in KB) |