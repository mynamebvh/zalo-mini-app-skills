# setNavigationBarColor

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarColor
> Last updated: 28/10/2026

```ts
import { setNavigationBarColor } from "zmp-sdk";
```

API đặt lại màu thanh điều hướng của trang hiện tại.

## Ví dụ

Đổi màu thanh điều hướng thành màu đen:

```ts
setNavigationBarColor({
  color: "#000000",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| color | `string` | Yes | Giá trị màu, có giá trị hợp lệ là màu thập lục phân, ví dụ `#000000`. Nếu giá trị này rỗng thì thanh điều hướng sẽ bị ẩn. |
| textColor | `"black" \| "white"` | No | Màu của text và icon trên thanh action bar và status bar. Trên thiết bị iOS, chỉ có thể thay đổi màu icon ở thanh action bar. |
| statusBarColor | `string` | No | Màu của thanh status bar khi thanh điều hướng bị ẩn, có giá trị hợp lệ là màu thập lục phân, ví dụ `#000000`. |
