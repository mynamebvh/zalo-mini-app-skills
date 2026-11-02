# openChat

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openChat
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openChat } from "zmp-sdk";
```

API that allows the app to open a chat window with a User or an Official Account. The message content can be pre-filled, but whether the message is sent depends on the user's decision.

## Example

Open a chat window with a user:

```ts
await openChat({
  type: "user",
  id: "xxx",
});
```

Open a chat window with an Official Account:

```ts
await openChat({
  type: "oa",
  id: "xxx",
});
```

Pre-fill the message content:

```ts
await openChat({
  type: "oa",
  id: "xxx",
  message: `Hello, I would like to buy this product: ${productName}`,
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"user" \| "oa"` | Yes | The entity to open a chat window with. |
| id | `string` | Yes | Id of the corresponding User or Official Account. |
| message | `string` | No | Content that will be pre-filled in the message box. The user can change this content before sending. |