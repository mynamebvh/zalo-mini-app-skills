# openMiniApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/routing/openMiniApp
> Last updated: 28/10/2026
> Supported from: SDK 2.7.0

```ts
import { openMiniApp } from "zmp-sdk";
```

API dùng để mở một Zalo Mini App khác. Có thể mở với một đường dẫn cụ thể bên trong Mini App đó, hoặc đính kèm các tham số bổ sung.

## Ví dụ

Mở Mini App "ZaUI Coffee":

```ts
openMiniApp({
  appId: "194839900003483517",
});
```

Mở tab "Cá nhân" bên trong "ZaUI Coffee":

```ts
openMiniApp({
  appId: "194839900003483517",
  path: "/profile",
});
```

Mở "ZaUI Coffee" với `utm_campaign` tracking:

```ts
openMiniApp({
  appId: "194839900003483517",
  params: {
    utm_campaign: "spring_promo",
  },
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| appId | `string` | Yes | ID của Zalo Mini App cần mở. |
| path | `string` | No | Đường dẫn đến một trang cụ thể bên trong Zalo Mini App cần mở. |
| params | `Record<string, string>` | No | Object chứa các tham số bổ sung cần đính kèm với đường dẫn. |
