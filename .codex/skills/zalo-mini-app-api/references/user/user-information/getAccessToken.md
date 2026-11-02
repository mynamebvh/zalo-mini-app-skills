# getAccessToken

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getAccessToken
> Last updated: 28/10/2026

```ts
import { getAccessToken } from "zmp-sdk";
```

API used to get user authentication information.

> **Update**
>
> Starting from SDK version 2.35.0, apps have access token permission by default without requiring the user's consent. Through this access token, the app can only export the user's ID. If the app needs to use the Name and Avatar, please use the **[authorize API](https://docs.zaloplatforms.com/docs/MA/api/user/authorization/authorize)** to request the user's permission to access scope.userInfo before using this API. Note: For Zalo Apps with more than 1 Mini App, the system still requires the user to confirm when accessing access tokens for each Mini App.

## Example

```ts
const accessToken = await getAccessToken();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

The API returns `Promise<string>` containing the `accessToken`.