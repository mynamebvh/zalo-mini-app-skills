# followOA

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/followOA
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { followOA } from "zmp-sdk";
```

API that requests following an Official Account. When the API is called, a notification is displayed.

Note: to help Mini App developers use the permission request flow effectively and in line with [section 3.3.4 of the Zalo Mini App policy](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp). The Mini App Team has provided some experience design suggestions as shown below. Developers need to explain clearly and visually the purpose of the permission request so that users can easily understand and agree to provide information.

![Flow request location](https://docs.zaloplatforms.com/assets/images/do-69b3781d38ec1df91ecf5695f3ace020.png)

To ensure a comfortable experience for Mini App users, we will reject Mini Apps whose permission request flow is unclear and does not state the purpose of the permission request to users. Refer to some violation cases below:

![Flow request location reject](https://docs.zaloplatforms.com/assets/images/dont-9d977ba47b76b3f3133c19b03756afa7.png)

## Example

Follow an Official Account:

```ts
await followOA({
  id: "xxxx",
});
```

Error handling:

```ts
try {
  await followOA({
    id: "xxxx",
  });
  console.log("Followed successfully");
} catch (error) {
  const code = (error as AppError).code;
  if (code === -201) {
    console.log("User declined to follow");
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
| id | `string` | Yes | Id of the Official Account to follow. |