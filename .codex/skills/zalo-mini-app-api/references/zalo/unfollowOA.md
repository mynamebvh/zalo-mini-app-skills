# unfollowOA

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/unfollowOA
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { unfollowOA } from "zmp-sdk";
```

API cho phép ứng dụng hiển thị giao diện yêu cầu bỏ theo dõi Official Account để người dùng xác nhận.

## Ví dụ

Hiển thị giao diện yêu cầu bỏ theo dõi Official Account:

```ts
await unfollowOA({
  id: "xxxx",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id của Official Account. |
