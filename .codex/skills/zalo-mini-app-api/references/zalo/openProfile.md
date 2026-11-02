# openProfile

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openProfile
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openProfile } from "zmp-sdk";
```

API that allows the app to open the profile of a User or an Official Account.

> **Note**
>
> For `oa` and `aliasOA`, the screen that opens depends on whether the user follows that OA: if not following, the OA profile opens; if following, the chat window opens.

## Example

Open a user's profile:

```ts
await openProfile({
  type: "user",
  id: "user-id",
});
```

Open an Official Account (profile or chat window, depending on whether the user follows it):

```ts
await openProfile({
  type: "oa",
  id: "oa-id",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"user" \| "oa" \| "aliasOA"` | Yes | Accepts the following values: `user`: Open the User profile. `oa`: Open the OA profile, or the chat window if the user already follows the OA. `aliasOA`: Same as `oa`, but the `id` field passed is the alias of the OA. |
| id | `string` | Yes | Id of the User or OA. |