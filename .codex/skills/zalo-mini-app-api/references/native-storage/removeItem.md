# removeItem

> Source: https://docs.zaloplatforms.com/docs/MA/api/native-storage/removeItem
> Last updated: 28/10/2026
> Supported from: SDK 2.43.0

```ts
import { nativeStorage } from "zmp-sdk";
```

Deletes data in the cache using the synchronous mechanism.

## Example

Delete the old search keyword from storage:

```ts
nativeStorage.removeItem("recentSearch");
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass the `key` parameter of type `string` directly to the API:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| key | `string` | Yes | Name of the key of the data to delete |