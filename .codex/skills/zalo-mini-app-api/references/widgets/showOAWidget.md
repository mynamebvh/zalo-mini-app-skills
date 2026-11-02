# showOAWidget

> Source: https://docs.zaloplatforms.com/docs/MA/api/widgets/showOAWidget
> Last updated: 28/10/2026
> Supported from: SDK 2.38.0

```ts
import { showOAWidget } from "zmp-sdk";
```

Widget Quan tâm OA: Người dùng bấm nút "Quan tâm" trên widget sẽ thực hiện quan tâm ngay mà không cần hiển thị bottom sheet xin quyền. Thông tin OA được lấy từ OA đã xác thực Mini App.

| Người dùng chưa quan tâm OA | Người dùng đã quan tâm OA |
| --- | --- |
| Widget Zalo OA | Widget Zalo OA |

## Ví dụ

Hiển thị Widget Quan tâm OA:

```ts
import React, { useEffect } from "react";
import { showOAWidget } from "zmp-sdk/apis";

function HomePage() {
  useEffect(() => {
    showOAWidget({
      id: "oaWidget",
      guidingText: "Nhận thông báo khuyến mãi mới nhất từ cửa hàng",
      color: "#0068FF",
      onStatusChange: (status) => {
        console.log(status);
      },
    });
  }, []);

  return (
    <>
      ...
      <div id="oaWidget" />
      ...
    </>
  );
}

export default HomePage;
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | ID của element, nơi cần hiển thị widget. |
| guidingText | `string` | No | Chuỗi dùng để thông báo cho người dùng. (default: "Nhận thông báo khuyến mãi mới nhất từ cửa hàng") |
| color | `string` | No | Màu chủ đạo của widget. Giá trị phải là chuỗi hex. (default: "#0068FF") |
| onStatusChange | `(status: boolean) => void` | No | Callback được gọi khi người dùng nhấn theo dõi OA. Trạng thái theo dõi mới được truyền vào tham số của callback. |
