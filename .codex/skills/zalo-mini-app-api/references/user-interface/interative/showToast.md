# showToast

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/interative/showToast
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { showToast } from "zmp-sdk";
```

API hiển thị một thông báo ngắn trên màn hình.

## Ví dụ

Hiện thông báo đặt hàng thành công:

```ts
showToast({
  message: "Đặt hàng thành công!",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| message | `string` | Yes | Nội dung thông báo cần hiển thị. |
