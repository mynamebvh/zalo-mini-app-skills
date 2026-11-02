# authorize

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/authorization/authorize
> Last updated: 28/10/2026
> Supported from: SDK 2.34.0, Android 23.12.02 (724), IOS 23.12.02 (573)

```ts
import { authorize } from "zmp-sdk";
```

### Granting API permissions

Some APIs require the user's permission before they can be called. These APIs are divided into multiple scopes, each corresponding to a purpose of use; see the Scopes table for detailed descriptions:

| Scope | Corresponding APIs | Description |
| --- | --- | --- |
| `scope.userInfo` | `getUserInfo` | User information (name, avatar...) |
| `scope.userLocation` | `getLocation` | User location information |
| `scope.userPhonenumber` | `getPhoneNumber` | Phone number |

When such an API is called:

- If the user has not accepted or declined, a pop-up window appears asking whether the user wants to accept. The API can only be called after the user taps accept.
- If the user has already granted permission, the API can be called directly.
- If the user declines permission, an error callback is returned.

Developers can use this API to proactively initiate a permission request to the user when needed, supporting up to 3 permissions (including the User Info permission):

![Multi_API_Request](https://docs.zaloplatforms.com/assets/MA/img/authorize/multi_api_request_v2.png)

### Get the status of a scope

Developers can use the `getSetting` API to get the user's current permission status.

### Manage granting/revoking permissions for users

Developers can call the `openPermissionSetting` API to open settings and guide the user to turn API permissions on/off.

![permission_settings](https://docs.zaloplatforms.com/assets/MA/img/authorize/permission_management.jpg)

### Validity period

After the user accepts or declines the permission, the permission status is recorded and synced for subsequent uses.

### Best Practices

- Only initiate a permission request when necessary, and clearly explain why you want to use it in the permission request.
- Use the `getSetting` API first to get the user's current permission status, then request the remaining missing permissions.

## Example

Initiate permission request

```ts
try {
  const data = await authorize({
    scopes: ["scope.userLocation", "scope.userPhonenumber"],
  });
  console.log(data["scope.userLocation"]); // `true` if the user agrees to grant location
  console.log(data["scope.userPhonenumber"]); // `true` if the user agrees to grant the phone number
} catch (error) {
  const code = (error as AppError).code;
  if (code === -201) {
    console.log("The user declined to grant permission");
  } else {
    console.log("Other error");
  }
}
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| scopes | `string[]` | No | List of permissions to grant; see the Scopes table. If not passed, the API requests the userInfo permission by default. |

## Returns

Returns `Promise<Scopes>` containing the statuses of the granted permissions.

### Scopes

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| userInfo | `boolean` | No | Status of the user info permission. |
| userLocation | `boolean` | No | Status of the user location permission. |
| userPhonenumber | `boolean` | No | Status of the phone number permission. |