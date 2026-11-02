# configAppView

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/configAppView
> Last updated: 28/10/2026
> Supported from: SDK 2.25.0, Android 23.02.01.r2, IOS 23.02.01.r2

```ts
import { configAppView } from "zmp-sdk";
```

API tuỳ chỉnh các thành phần giao diện chính trên Mini App, bao gồm:

- Status bar
- Action bar
- Bottom Navigation (Android) / Safe Area Inset Bottom (iOS)

Với api `configAppView`, bạn có thể ẩn/ hiện, tuỳ chỉnh màu sắc, kiểu hiển thị của các thành phần mặc định trên Mini App. Xem hình ảnh mô tả bên dưới để hiểu rõ các thành phần có thể tuỳ chỉnh trên Mini App của bạn.

## Ví dụ

Thay đổi tiêu đề action bar:

```ts
configAppView({
  actionBar: {
    title: "Giỏ hàng",
  },
});
```

Để có được giao diện toàn màn hình:

```ts
configAppView({
  hideAndroidBottomNavigationBar: true,
  hideIOSSafeAreaBottom: true,
  statusBarType: "transparent", // hoặc "hidden"
  actionBar: {
    hide: true,
  },
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| headerColor | `string` | No | Mã màu, có giá trị hợp lệ là màu thập lục phân, ví dụ `#000000`. |
| headerTextColor | `"white" \| "black"` | No | Màu của text và icon trên thanh action bar và status bar. |
| statusBarType | `"normal" \| "hidden" \| "transparent"` | No | Kiểu hiển thị của status bar. (default: "normal") |
| hideAndroidBottomNavigationBar | `boolean` | No | Ẩn thanh navigation bar trên Android. (default: false) |
| hideIOSSafeAreaBottom | `boolean` | No | Ẩn thanh safe area inset bottom trên iOS. (default: false) |
| hide | `boolean` | No | Ẩn action bar. |
| title | `string` | No | Tiêu đề hiển thị trên action bar. |
| leftButton | `"back" \| "none"` | No | Tuỳ chỉnh nút điều hướng bên trái action bar. Mặc định hiển thị nút back. Truyền `none` để ẩn nút. (default: "back") |
| textAlign | `"left" \| "center"` | No | Tuỳ chỉnh vị trí tiêu đề hiển thị trên action bar. (default: "left") |
