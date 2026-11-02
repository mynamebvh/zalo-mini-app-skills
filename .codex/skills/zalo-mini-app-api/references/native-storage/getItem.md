# getItem

> Source: https://docs.zaloplatforms.com/docs/MA/api/native-storage/getItem
> Last updated: 28/10/2026
> Supported from: SDK 2.43.0

```ts
import { nativeStorage } from "zmp-sdk";
```

Gets data stored in the cache using the synchronous mechanism.

## Example

Get the recent search value

```ts
const keyword = getItem("recentSearch");
```

Get the product list from the cache. Make sure to always use `try/catch` when parsing JSON to avoid errors that could crash the app.

```ts
try {
  const data: Product[] = JSON.parse(getItem("cache.productList"));
} catch (error) {
  // No data found in the cache, or the data is not a valid JSON string
}
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| key | `string` | Yes | Name of the key of the data to get |

## Returns

The API returns a `string` containing the value of the requested key, or `null` if the key does not exist.