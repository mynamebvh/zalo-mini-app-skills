# setItem

> Source: https://docs.zaloplatforms.com/docs/MA/api/native-storage/setItem
> Last updated: 28/10/2026
> Supported from: SDK 2.43.0

```ts
import { nativeStorage } from "zmp-sdk";
```

Stores data to the cache synchronously. The data is saved on the user's device. The oldest data is deleted if the memory limit (5MB) is reached.

## Example

Save a search keyword to memory:

```ts
nativeStorage.setItem("recentSearch", keyword);
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass the two parameters `key` and `value` of type `string` directly to the API:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| key | `string` | Yes | The name of the key you want to create/update. |
| value | `string` | Yes | The value you want to provide for the key you are creating/updating. |