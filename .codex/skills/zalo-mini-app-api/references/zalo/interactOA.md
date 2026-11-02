# interactOA

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/interactOA
> Last updated: 28/10/2026
> Supported from: SDK 2.28.8

```ts
import { interactOA } from "zmp-sdk";
```

API yêu cầu người dùng cho phép gửi thông báo thông qua Official Account. API sẽ chỉ hiển thị thông báo khi cần yêu cầu quyền từ người dùng. Lưu ý, để giúp các nhà phát triển Mini App sử dụng flow xin quyền một cách hiệu quả, cũng như phù hợp với [chính sách của Zalo Mini App điều 3.3.4](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp). Mini App Team đã đưa ra một số gợi ý thiết kế trải nghiệm như thông tin bên dưới. Nhà phát triển cần giải thích rõ ràng và trực quan mục đích xin quyền để người dùng dễ dàng hiểu và đồng ý cung cấp thông tin.

![Flow request interact](https://docs.zaloplatforms.com/assets/images/interact_do-4072231e4feb67a9102229f849e307c1.png)

Nhằm đảm bảo trải nghiệm thoải mái của người dùng Mini App, chúng tôi sẽ từ chối xét duyệt cho những Mini App có luồng xin cấp quyền chưa rõ ràng, không nêu được mục đích xin quyền đến người dùng. Tham khảo một số trường hợp vi phạm như bên dưới:

![Flow request interact reject](https://docs.zaloplatforms.com/assets/images/interact_dont-6861386220f3781f35b7500910548fcd.png)

## Ví dụ

Yêu cầu người dùng cho phép gửi thông báo thông qua Official Account:

```ts
await interactOA({
  oaId: "xxxx",
});
```

Xử lý lỗi:

```ts
try {
  await interactOA({
    oaId: "xxxx",
  });
  console.log("Người dùng đã cho phép");
} catch (error) {
  const code = (error as AppError).code;
  if (code === -201) {
    console.log("Người dùng đã từ chối");
  } else {
    console.log("Lỗi khác");
  }
}
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| oaId | `string` | Yes | Id của Official Account. |
