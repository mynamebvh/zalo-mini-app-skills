# addRating

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/addRating
> Last updated: 28/10/2026
> Supported from: SDK 2.28.0

```ts
import { addRating } from "zmp-sdk";
```

API mở cửa sổ đánh giá ứng dụng, hỗ trợ ghi nhận đánh giá phản hồi của người dùng về chất lượng của Mini App.

> **Warning**
>
> Chỉ có thể hiển thị cửa sổ đánh giá 1 lần/tuần đối với mỗi người dùng. Quá giới hạn trên sẽ trả về [lỗi](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

![Cửa sổ đánh giá ứng dụng](https://docs.zaloplatforms.com/assets/MA/img/api/addRating/addRating_screen.jpg)

## Ví dụ

Mở cửa sổ đánh giá ứng dụng:

```ts
await addRating();
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).
