# closeLoading

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/interative/closeLoading
> Last updated: 28/10/2026
> Supported from: SDK 2.17.0

```ts
import { closeLoading } from "zmp-sdk";
```

Khi người dùng mở Zalo Mini App, một màn hình loading sẽ được hiển thị trong lúc chờ Mini App được tải. Màn hình này gọi là Splash Loading.
Mặc định Splash Loading sẽ tự động đóng khi Mini App được tải xong. Tuy nhiên, phía tích hợp có thể chọn thời điểm phù hợp để đóng loading bằng cách:

- Thêm thiết lập `selfControlLoading: true` trong `app-config.json`. Xem [Cấu Hình Zalo Mini App](https://docs.zaloplatforms.com/docs/MA/devtools/app-config#app).
- Gọi `closeLoading` ở thời điểm thích hợp để đóng Splash Loading.

Lưu ý:

- Nếu thiết lập `selfControlLoading: true` mà API này không được gọi, **Mini App sẽ stuck ở màn hình Splash Loading**.
- Do code gọi API này chỉ được thực thi sau khi Mini App đã được tải xong, nên Splash Loading sẽ được đóng trễ hơn so với bình thường. Chỉ sử dụng cơ chế này khi cần thiết (để giảm layout shift hoặc không muốn người dùng thấy nội dung chưa hoàn chỉnh).

## Ví dụ

Đóng loading sau khi HomePage đã render xong:

```ts
function HomePage() {
  useEffect(() => {
    closeLoading();
  }, []);
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).
