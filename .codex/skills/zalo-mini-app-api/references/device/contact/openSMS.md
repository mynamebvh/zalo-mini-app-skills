# openSMS

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/contact/openSMS
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openSMS } from "zmp-sdk";
```

API mở ứng dụng tin nhắn với nội dung và số điện thoại cụ thể.

## Ví dụ

Mở ứng dụng tin nhắn với nội dung và số điện thoại cụ thể:

```ts
await openSMS({
  content: "text",
  phoneNumber: "+84123456789",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| content | `string` | Yes | Nội dung tin nhắn. |
| phoneNumber | `string` | Yes | Số điện thoại nhận tin nhắn. |
