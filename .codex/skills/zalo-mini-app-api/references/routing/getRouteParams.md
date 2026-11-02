# getRouteParams

> Source: https://docs.zaloplatforms.com/docs/MA/api/routing/getRouteParams
> Last updated: 28/10/2026
> Supported from: SDK 2.11.0

```ts
import { getRouteParams } from "zmp-sdk";
```

API that retrieves the parameters passed to the current page.

## Example

Get the product ID passed in the URL:

```ts
const { id } = getRouteParams();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Record<string, string>` containing all parameters as key-value pairs.