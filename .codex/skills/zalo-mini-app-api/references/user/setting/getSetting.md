# getSetting

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/setting/getSetting
> Last updated: 28/10/2026
> Supported from: SDK 2.31.0

```ts
import { getSetting } from "zmp-sdk";
```

API that gets the user's current settings.

## Example

Get the user's current settings:

```ts
const { authSetting } = await getSetting();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<GetSettingReturn>` containing the user's current settings.

### GetSettingReturn

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| authSetting | `AuthorizeType` | No | Permission info; see the [Scopes](#scopes) table. For scopes whose returned value is `true`, meaning the user has previously granted permission to use the API, the Mini App can access the information directly. |

## Scopes

| Scope | Corresponding APIs | Description |
| --- | --- | --- |
| scope.userInfo | `getUserInfo` | User information (name, avatar...) |
| scope.userLocation | `getLocation` | User location information |
| scope.userPhonenumber | `getPhoneNumber` | Phone number |
| scope.camera | `createCameraContext` | Camera |
| scope.micro | `createCameraContext` | Micro |