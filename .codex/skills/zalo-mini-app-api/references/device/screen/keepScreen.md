# keepScreen

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/screen/keepScreen
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { keepScreen } from "zmp-sdk";
```

API cho phép ứng dụng giữ cho màn hình luôn bật. Ví dụ: trường hợp play video. Khi thoát khỏi ứng dụng, cài đặt này sẽ quay về mặc định để tránh màn hình luôn bật.

## Ví dụ

Giữ màn hình luôn bật:

```ts
await keepScreen({
  keepScreenOn: true,
});
```

Tắt chế độ giữ màn hình:

```ts
await keepScreen({
  keepScreenOn: false,
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| keepScreenOn | `boolean` | Yes | Truyền `true` để giữ màn hình luôn bật. Truyền `false` để tắt chế độ này. |
