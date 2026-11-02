# unfollowOA

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/unfollowOA
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { unfollowOA } from "zmp-sdk";
```

API that allows the app to display an interface requesting to unfollow an Official Account for the user to confirm.

## Example

Display the interface requesting to unfollow an Official Account:

```ts
await unfollowOA({
  id: "xxxx",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id of the Official Account. |