# getUserID

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getUserID
> Last updated: 28/10/2026
> Supported from: SDK 2.32.2

```ts
import { getUserID } from "zmp-sdk";
```

API that allows retrieving the user ID. The ID is the user identifier string according to the Zalo App. This string is unique for each user on each Zalo App ID. Mini Apps sharing the same Zalo App ID can use this string to identify users. (This API does not require user confirmation.)

## Example

Retrieve the user ID:

```ts
const userID = await getUserID({});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

The API returns `Promise<string>` containing the user ID.