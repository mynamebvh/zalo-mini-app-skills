# viewOAQr

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/viewOAQr
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { viewOAQr } from "zmp-sdk";
```

API cho phép ứng dụng hiển thị QR code của OA.

## Ví dụ

Hiển thị QR code của OA:

```ts
await viewOAQr({
  id: "765465772305886642",
  displayName: "Galaxy Cinema",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id của OA. |
| displayName | `string` | No | Tên hiển thị của QR code. |
