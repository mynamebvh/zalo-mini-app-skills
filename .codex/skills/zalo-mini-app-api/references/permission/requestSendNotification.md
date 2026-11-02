# requestSendNotification

> Source: https://docs.zaloplatforms.com/docs/MA/api/permission/requestSendNotification
> Last updated: 28/10/2026
> Supported from: SDK 2.27.1

```ts
import { requestSendNotification } from "zmp-sdk";
```

API that requests the user's permission to receive notifications via the Mini App OA. When the API is called, a notification is displayed.

![Demo of the notification requesting permission to receive notifications via the Mini App OA](https://docs.zaloplatforms.com/assets/images/send_zns-06aee7ce69cda2ca2944d1a0c4068bf0.png)

## Example

Request the user's permission to receive notifications:

```ts
await requestSendNotification();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).