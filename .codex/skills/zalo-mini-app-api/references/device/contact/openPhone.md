# openPhone

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/contact/openPhone
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openPhone } from "zmp-sdk";
```

API cho phép mở màn hình cuộc gọi với một số điện thoại cụ thể.

## Ví dụ

Mở màn hình cuộc gọi với số điện thoại cụ thể:

```ts
await openPhone({
  phoneNumber: "0123456789",
});
```

Số điện thoại có thể bắt đầu bằng mã quốc tế:

```ts
await openPhone({
  phoneNumber: "+84123456789",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| phoneNumber | `string` | Yes | Số điện thoại cần gọi. |
