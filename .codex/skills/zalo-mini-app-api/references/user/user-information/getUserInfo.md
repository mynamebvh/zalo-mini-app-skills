# getUserInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getUserInfo
> Last updated: 28/10/2026

```ts
import { getUserInfo } from "zmp-sdk";
```

API that retrieves user information including:

- ID: the user identifier string according to the Zalo App, granted by default.
- Name and Avatar: to comply with Decree No. 13/2023/ND-CP on personal data protection policy, this information will require the user's confirmation before it can be retrieved. If the app needs to use this information, please pass the `autoRequestPermission` param with the value `true`, or use the [authorize](https://docs.zaloplatforms.com/docs/MA/api/user/authorization/authorize) API to request the user's permission to access this information before using this API.

## Example

Automatically request permission to access user information:

```ts
const { userInfo } = await getUserInfo({
  autoRequestPermission: true,
});
```

Handle the event where the user denies access to the information:

```ts
try {
  const { userInfo } = await getUserInfo();
} catch (error) {
  if (error instanceof AppError) {
    if (error.code === -1401) {
      // The user denied providing the name and avatar
    }
  }
}
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| avatarType | `"small" \| "normal" \| "large"` | No | The size of the returned avatar image. Defaults to the smallest image. |
| autoRequestPermission | `boolean` | No | If `true`, the app will automatically display a form requesting the user's permission to access the information. (default: false) |

## Returns

The API returns `Promise<GetUserInfoReturns>` containing the user information including ID, Name, and Avatar.

### GetUserInfoReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| userInfo | `UserInfo` | No | User information. |

### UserInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | No | The user identifier string according to the Zalo App. This string is unique for each user on each Zalo App. Mini Apps sharing the same Zalo App ID can use this string to identify users. This ID can be used to send notifications to the user through the shared Official Account of the Zalo Mini App, refer to [here](https://docs.zaloplatforms.com/docs/MA/openApis/notification/apis/send). |
| name | `string` | No | The user's display name. |
| avatar | `string` | No | The user's avatar. |
| idByOA | `string` | No | The user identifier string according to the Official Account. The string has a value if one of the following conditions is met: - The Mini App has been verified by the Official Account, see details [here](https://miniapp.zaloplatforms.com/blog/huong-dan-khoi-tao#21-x%C3%A1c-th%E1%BB%B1c-ch%E1%BB%A7-s%E1%BB%9F-h%E1%BB%AFu-mini-app:~:text=C%C3%A1ch%201%3A%20X%C3%A1c%20th%E1%BB%B1c%20qua%20OA). - The Zalo App must be linked to the Official Account and the user has followed that Official Account. |
| followedOA | `boolean` | No | The follow status of the Official Account linked to the Zalo App. |
| isSensitive | `boolean` | No | Returns 1 of 2 values: - `true`: this account belongs to the group of users for which Mini App developers need to verify and apply appropriate data processing mechanisms in accordance with legal regulations, which may include but are not limited to deceased or missing persons, illiterate persons, persons with disabilities, children, etc. - `false`: this account belongs to the group of normal users. |