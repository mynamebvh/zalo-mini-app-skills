# sendDataToPreviousMiniApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/routing/sendDataToPreviousMiniApp
> Last updated: 28/10/2026
> Supported from: SDK 2.13.0

```ts
import { sendDataToPreviousMiniApp } from "zmp-sdk";
```

Gửi dữ liệu cho Zalo Mini App trước đó.
Zalo Mini App trước đó cần lắng nghe sự kiện [OnDataCallback](https://docs.zaloplatforms.com/docs/MA/api/events#ondatacallback) để nhận dữ liệu.
Nếu API được gọi nhiều lần thì dữ liệu cuối cùng sẽ được gửi đi.

## Ví dụ

Ví dụ có 2 Zalo Mini App A với id là `2953132499190403100` và B với id là `2953132499190403200`. Để B có thể gửi dữ liệu cho A, chúng ta cần thực hiện những bước sau:

1. Lắng nghe sự kiện [OnDataCallback](https://docs.zaloplatforms.com/docs/MA/api/events#ondatacallback) ở app A:

```ts
import { events, EventName } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};

events.on(EventName.OnDataCallback, callback);
```

2. Gọi API [openMiniApp](https://docs.zaloplatforms.com/docs/MA/api/routing/openMiniApp) để chuyển đến app B:

```ts
import { openMiniApp } from "zmp-sdk/apis";

openMiniApp({
  appId: "2953132499190403200",
});
```

3. Ở app B, gửi dữ liệu cho app A:

```ts
import { sendDataToPreviousMiniApp } from "zmp-sdk/apis";

sendDataToPreviousMiniApp({
  data: "Success",
});
```

4. Tắt app B bằng bằng api [closeApp](https://docs.zaloplatforms.com/docs/MA/api/routing/closeApp) hoặc nhấn nút bên dưới:

![buttonCloseApp](https://docs.zaloplatforms.com/assets/MA/img/button-close-app.png)

5. Sau khi app B đóng hoàn toàn, app A sẽ nhận được dữ liệu đã gửi

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| data | `any` | Yes | Dữ liệu cần gửi. |
