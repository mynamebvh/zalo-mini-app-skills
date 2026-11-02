# setNavigationBarTitle

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarTitle
> Last updated: 28/10/2026

```ts
import { setNavigationBarTitle } from "zmp-sdk";
```

API đặt lại tiêu đề trên thanh điều hướng của trang hiện tại.

## Ví dụ

Khi người dùng truy cập trang Giỏ hàng:

```ts
function CartPage() {
  useEffect(() => {
    setNavigationBarTitle({ title: "Giỏ hàng" });
  }, []);
}
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| title | `string` | Yes | Tiêu đề mới cần đặt cho trang. |
