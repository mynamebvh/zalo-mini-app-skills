# interactOA

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/interactOA
> Last updated: 28/10/2026
> Supported from: SDK 2.28.8

```ts
import { interactOA } from "zmp-sdk";
```

API that requests that the user allow sending notifications through an Official Account. The API only displays a notification when permission needs to be requested from the user. Note: to help Mini App developers use the permission request flow effectively and in line with [section 3.3.4 of the Zalo Mini App policy](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp). The Mini App Team has provided some experience design suggestions as shown below. Developers need to explain clearly and visually the purpose of the permission request so that users can easily understand and agree to provide information.

![Flow request interact](https://docs.zaloplatforms.com/assets/images/interact_do-4072231e4feb67a9102229f849e307c1.png)

To ensure a comfortable experience for Mini App users, we will reject Mini Apps whose permission request flow is unclear and does not state the purpose of the permission request to users. Refer to some violation cases below:

![Flow request interact reject](https://docs.zaloplatforms.com/assets/images/interact_dont-6861386220f3781f35b7500910548fcd.png)

## Example

Request that the user allow sending notifications through an Official Account:

```ts
await interactOA({
  oaId: "xxxx",
});
```

Error handling:

```ts
try {
  await interactOA({
    oaId: "xxxx",
  });
  console.log("User has granted permission");
} catch (error) {
  const code = (error as AppError).code;
  if (code === -201) {
    console.log("User has declined");
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
| oaId | `string` | Yes | Id of the Official Account. |