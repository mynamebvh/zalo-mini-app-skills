# setNavigationBarLeftButton

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarLeftButton
> Last updated: 28/10/2026

```ts
import { setNavigationBarLeftButton } from "zmp-sdk";
```

API đặt lại nút bên trái trên thanh điều hướng của trang hiện tại.

## Ví dụ

Hiển thị mũi tên quay lại:

```ts
await setNavigationBarLeftButton({
  type: "back",
});
```

Hiển thị nút trở về trang chủ:

```ts
await setNavigationBarLeftButton({
  type: "home",
});
```

Hiển thị cả nút quay lại và nút trở về trang chủ:

```ts
await setNavigationBarLeftButton({
  type: "both",
});
```

Không hiển thị nút bên trái:

```ts
await setNavigationBarLeftButton({
  type: "none",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"none" \| "back" \| "home" \| "both"` | No | Loại nút bên trái. (default: "back") |
