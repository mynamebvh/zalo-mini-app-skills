# followOA

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/followOA
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { followOA } from "zmp-sdk";
```

API yêu cầu theo dõi Official Account. Khi gọi api, một thông báo sẽ được hiển thị.

Lưu ý, để giúp các nhà phát triển Mini App sử dụng flow xin quyền một cách hiệu quả, cũng như phù hợp với [chính sách của Zalo Mini App điều 3.3.4](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp). Mini App Team đã đưa ra một số gợi ý thiết kế trải nghiệm như thông tin bên dưới. Nhà phát triển cần giải thích rõ ràng và trực quan mục đích xin quyền để người dùng dễ dàng hiểu và đồng ý cung cấp thông tin.

![Flow request location](https://docs.zaloplatforms.com/assets/images/do-69b3781d38ec1df91ecf5695f3ace020.png)

Nhằm đảm bảo trải nghiệm thoải mái của người dùng Mini App, chúng tôi sẽ từ chối xét duyệt cho những Mini App có luồng xin cấp quyền chưa rõ ràng, không nêu được mục đích xin quyền đến người dùng. Tham khảo một số trường hợp vi phạm như bên dưới:

![Flow request location reject](https://docs.zaloplatforms.com/assets/images/dont-9d977ba47b76b3f3133c19b03756afa7.png)

## Ví dụ

Theo dõi Official Account:

```ts
await followOA({
  id: "xxxx",
});
```

Xử lý lỗi:

```ts
try {
  await followOA({
    id: "xxxx",
  });
  console.log("Theo dõi thành công");
} catch (error) {
  const code = (error as AppError).code;
  if (code === -201) {
    console.log("Người dùng đã từ chối theo dõi");
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
| id | `string` | Yes | Id của Official Account cần theo dõi. |
