# minimizeApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/minimizeApp
> Last updated: 28/10/2026
> Supported from: SDK 2.26.1

```ts
import { minimizeApp } from "zmp-sdk";
```

API chủ động thu nhỏ ứng dụng. Khi gọi API, Mini App sẽ được thu nhỏ vào một floating icon ở góc màn hình, giúp người sử dụng có thể tạm thời sử dụng các chức năng khác của Zalo, và quay trở lại Mini App của bạn mà không cần phải tải lại từ đầu.

![Thu nhỏ ứng dụng](https://docs.zaloplatforms.com/assets/MA/img/ZMA-Floating.png)Ứng dụng đã được thu nhỏ

## Ví dụ

Thu nhỏ ứng dụng:

```ts
await minimizeApp();
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).
