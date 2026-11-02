# createShortcut

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/createShortcut
> Last updated: 28/10/2026
> Supported from: SDK 2.16.1

```ts
import { createShortcut } from "zmp-sdk";
```

API cho phép ứng dụng tạo shortcut trên màn hình chờ.

### Quy trình tạo shortcut trên android

![shorcut android](https://docs.zaloplatforms.com/assets/images/shortcut-android-316d3f0da0ad419330ed9d12fc858dfb.png)

Lưu ý: params khác nhau sẽ tạo shortcut khác nhau

### Quy trình tạo shortcut trên ios

![shorcut ios](https://docs.zaloplatforms.com/assets/images/shorcut-ios-e3dd37062cec1ba92eb70e1ae6353a0e.png)

## Ví dụ

Tạo shortcut đơn giản:

```ts
await createShortcut();
```

Tạo shortcut với params:

```ts
await createShortcut({
  params: {
    utm_source: "shortcut",
  },
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| params | `Record<string, string>` | No | Params cần thêm vào Zalo Mini App khi mở.. |
