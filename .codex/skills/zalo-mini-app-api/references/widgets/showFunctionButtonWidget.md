# showFunctionButtonWidget

> Source: https://docs.zaloplatforms.com/docs/MA/api/widgets/showFunctionButtonWidget
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

```ts
import { showFunctionButtonWidget } from "zmp-sdk";
```

Widget Function Button: Khi người dùng nhấn vào button này, Mini App sẽ nhận được 1 interact token (có giá trị trong 1 giờ).

Từ phiên bản `2.52.2` trở lên, `showFunctionButtonWidget` hỗ trợ hiển thị nhiều Widget Function Button trên cùng một trang; mỗi widget cần một element có `id` riêng biệt.

![Widget FunctionButton](https://docs.zaloplatforms.com/assets/images/function_button_widget-a4f5805d306239f21aae8e631fd02460.png)

## Ví dụ

Hiển thị Widget Function Button:

```ts
import React, { useEffect } from "react";
import { showFunctionButtonWidget } from "zmp-sdk/apis";

function HomePage() {
  useEffect(() => {
    showFunctionButtonWidget({
      id: "orderButton",
      type: "ORDER",
      text: "Đặt hàng",
      color: "#0068FF",
      textColor: "#FFFFFF",
      borderRadius: "48px",
      onDataReceived: (interactToken) => {
        console.log(interactToken);
      },
      onError: (error) => {
        console.error("onError:", error.code, error.message);
      },
    });
  }, []);

  return (
    <>
      ...
      <div id="orderButton" />
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
| id | `string` | Yes | ID của element, nơi cần hiển thị widget. Mỗi widget trên cùng một trang cần sử dụng một element có ID riêng biệt. |
| type | `"ORDER"` | Yes | Loại nút, hiện tại chỉ hỗ trợ giá trị: `ORDER`. |
| text | `string` | Yes | Chuỗi hiển thị trong button. - Các giá trị sẽ trả về `interactToken`: `Thanh toán`, `Xác nhận và thanh toán`, `Đặt xe`, `Đặt hàng`, `Đăng ký gói` |
| fontSize | `string` | No | Kích thước font chữ. Giá trị nhỏ nhất là 14px. (default: "16px") |
| color | `string` | No | Màu chủ đạo của widget. Giá trị phải là chuỗi hex. (default: "#0068FF") |
| textColor | `string` | No | Màu chữ trong button. Giá trị phải là chuỗi hex. (default: "#FFFFFF") |
| borderRadius | `string` | No | Bo góc (bo tròn các góc của button). (default: "48px") |
| disabled | `boolean` | No | Trạng thái vô hiệu hóa của widget. |
| onDataReceived | `(interactToken: string, type: string, context: { callAction: (actionName: string, actionData: any) => void }) => void` | No | Callback được gọi khi người dùng nhấn vào widget. Callback nhận `interactToken` có giá trị trong 1 giờ, loại widget `type` và `context` chứa hàm `callAction(actionName, actionData)`. |
| onError | `(error: AppError) => void` | No | Callback được gọi khi có lỗi xảy ra khi người dùng nhấn vào widget. Callback này chứa `error` là thông tin về lỗi. |
