# vibrate

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/vibrate
> Last updated: 28/10/2026
> Supported from: SDK 2.9.8

```ts
import { vibrate } from "zmp-sdk";
```

API rung thiết bị.

## Ví dụ

Rung thiết bị trong 500 mili giây:

```ts
await vibrate();
```

Rung thiết bị trong 1 giây:

```ts
await vibrate({
  type: "oneShot",
  milliseconds: 1000,
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `string` | No | Loại rung, hiện tại chỉ hỗ trợ `oneShot`. (default: "oneShot") |
| milliseconds | `number` | No | Thời gian rung (tính bằng mili giây). Chỉ có thể thiết lập trên thiết bị Android. (default: 500) |
