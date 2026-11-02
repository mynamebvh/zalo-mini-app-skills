# openProfilePicker

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openProfilePicker
> Last updated: 28/10/2026
> Supported from: SDK 2.16.1

```ts
import { openProfilePicker } from "zmp-sdk";
```

API that opens a friend picker in Zalo; the API returns the list of selected people.

![openProfilePicker](https://docs.zaloplatforms.com/assets/images/profilePicker-27e8f2a55289e5d654d5ed556c4a1119.png)

## Example

Select up to 2 friends from the user's friend list:

```ts
const { users } = await openProfilePicker({
  maxProfile: 2,
});
console.log(users);
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| maxProfile | `number` | No | Maximum number of friends that can be selected. Limited to the range 1 to 10. (default: 1) |

## Returns

Returns `Promise<OpenProfilePickerReturns>` containing the list of selected friends.

### OpenProfilePickerReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| users | `PickedProfile[]` | No | List of selected friends. |

### PickedProfile

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | No | User ID. This string is unique for each user per Zalo App. Zalo Mini Apps that share the same Zalo App can use each other's user IDs. |
| profile | `ProfileInfo` | No | User information. |
| code | `number` | No | Error code: - 0: Successfully retrieved user information. - -1: Failed to retrieve user information. |
| message | `string` | No | Error message. |

### ProfileInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| name | `string` | No | Display name of the user. |
| avatar | `string` | No | User avatar. |