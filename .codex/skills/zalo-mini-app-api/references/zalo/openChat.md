# openChat

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openChat
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openChat } from "zmp-sdk";
```

API cho phép ứng dụng mở cửa sổ chat với User hoặc Official Account. Có thể tự động điền nội dung tin nhắn, tuy nhiên việc gửi tin nhắn hay không phụ thuộc vào quyết định của người dùng.

## Ví dụ

Mở cửa sổ chat với người dùng:

```ts
await openChat({
  type: "user",
  id: "xxx",
});
```

Mở cửa sổ chat với Official Account:

```ts
await openChat({
  type: "oa",
  id: "xxx",
});
```

Tự động điền nội dung tin nhắn:

```ts
await openChat({
  type: "oa",
  id: "xxx",
  message: `Xin chào, tôi muốn mua sản phẩm này: ${productName}`,
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"user" \| "oa"` | Yes | Đối tượng mở cửa sổ chat. |
| id | `string` | Yes | Id của User hoặc Official Account tương ứng. |
| message | `string` | No | Nội dung sẽ được tự động điền vào ô tin nhắn. Người dùng có thể thay đổi nội dung này trước khi gửi. |
