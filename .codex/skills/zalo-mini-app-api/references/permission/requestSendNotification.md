# requestSendNotification

> Source: https://docs.zaloplatforms.com/docs/MA/api/permission/requestSendNotification
> Last updated: 28/10/2026
> Supported from: SDK 2.27.1

```ts
import { requestSendNotification } from "zmp-sdk";
```

API yêu cầu người dùng cho phép nhận thông báo qua OA Mini App. Khi gọi API, một thông báo sẽ được hiển thị.

![Demo thông báo yêu cầu cho phép nhận thông báo qua OA Mini App](https://docs.zaloplatforms.com/assets/images/send_zns-06aee7ce69cda2ca2944d1a0c4068bf0.png)

## Ví dụ

Yêu cầu người dùng cho phép nhận thông báo:

```ts
await requestSendNotification();
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).
