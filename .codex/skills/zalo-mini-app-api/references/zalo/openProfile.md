# openProfile

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openProfile
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openProfile } from "zmp-sdk";
```

API cho phép ứng dụng mở profile của User hoặc Official Account.

> **Note**
>
> Với `oa` và `aliasOA`, màn hình được mở phụ thuộc trạng thái quan tâm của người dùng với OA đó: chưa quan tâm thì mở profile OA, đã quan tâm thì mở cửa sổ chat.

## Ví dụ

Mở profile của người dùng:

```ts
await openProfile({
  type: "user",
  id: "user-id",
});
```

Mở Official Account (profile hoặc cửa sổ chat, tuỳ trạng thái user có quan tâm hay chưa):

```ts
await openProfile({
  type: "oa",
  id: "oa-id",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"user" \| "oa" \| "aliasOA"` | Yes | Nhận các giá trị sau: `user`: Mở profile User. `oa`: Mở profile OA, hoặc cửa sổ chat nếu người dùng đã quan tâm OA. `aliasOA`: Như `oa`, nhưng field id truyền lên là alias của OA. |
| id | `string` | Yes | Id của User hoặc OA. |
