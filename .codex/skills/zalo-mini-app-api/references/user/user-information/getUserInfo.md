# getUserInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getUserInfo
> Last updated: 28/10/2026

```ts
import { getUserInfo } from "zmp-sdk";
```

API truy xuất thông tin của người dùng bao gồm:

- ID: chuỗi định danh người dùng theo Zalo App, được cấp mặc định.
- Tên và Ảnh đại diện: nhằm tuân thủ Nghị Định số 13/2023/NĐ-CP về chính sách bảo vệ dữ liệu cá nhân, thông tin này sẽ yêu cầu người dùng xác nhận cho phép trước khi truy xuất. Nếu ứng dụng cần sử dụng thông tin này, vui lòng truyền param `autoRequestPermission` với giá trị `true`, hoặc sử dụng API [authorize](https://docs.zaloplatforms.com/docs/MA/api/user/authorization/authorize) để yêu cầu người dùng cho phép truy cập trước khi sử dụng API này.

## Ví dụ

Tự động yêu cầu quyền truy cập thông tin người dùng:

```ts
const { userInfo } = await getUserInfo({
  autoRequestPermission: true,
});
```

Xử lý sự kiện người dùng từ chối truy cập thông tin:

```ts
try {
  const { userInfo } = await getUserInfo();
} catch (error) {
  if (error instanceof AppError) {
    if (error.code === -1401) {
      // Người dùng từ chối cung cấp tên và ảnh đại diện
    }
  }
}
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| avatarType | `"small" \| "normal" \| "large"` | No | Kích thước ảnh avatar trả về. Mặc định là ảnh nhỏ nhất. |
| autoRequestPermission | `boolean` | No | Nếu `true`, ứng dụng sẽ tự động hiển thị form yêu cầu người dùng cho phép truy cập thông tin. (default: false) |

## Kết quả trả về

API trả về `Promise<GetUserInfoReturns>` chứa Thông tin người dùng bao gồm ID, Tên, và Ảnh đại diện.

### GetUserInfoReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| userInfo | `UserInfo` | No | Thông tin người dùng. |

### UserInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | No | Chuỗi định danh người dùng theo Zalo App. Chuỗi này là duy nhất cho mỗi người dùng trên mỗi Zalo App. Các Mini App cùng chung một Zalo App ID sẽ có thể dùng chuỗi này để định danh người dùng. Có thể sử dụng ID này để gửi thông báo tới người dùng qua OA chung của Zalo Mini App, tham khảo tại [đây](https://docs.zaloplatforms.com/docs/MA/openApis/notification/apis/send). |
| name | `string` | No | Tên hiển thị của người dùng. |
| avatar | `string` | No | Ảnh đại diện người dùng. |
| idByOA | `string` | No | Chuỗi định danh người dùng theo Official Account. Chuỗi có giá trị nếu thỏa 1 trong các điều kiện dưới đây: - Mini App đã được xác thực bởi Official Account, chi tiết xem [tại đây](https://miniapp.zaloplatforms.com/blog/huong-dan-khoi-tao#21-x%C3%A1c-th%E1%BB%B1c-ch%E1%BB%A7-s%E1%BB%9F-h%E1%BB%AFu-mini-app:~:text=C%C3%A1ch%201%3A%20X%C3%A1c%20th%E1%BB%B1c%20qua%20OA). - Zalo App phải được liên kết với Official Account và người dùng đã follow Official Account đó. |
| followedOA | `boolean` | No | Trạng thái theo dõi Official Account đã được liên kết với Zalo App. |
| isSensitive | `boolean` | No | Trả về 1 trong 2 giá trị: - `true`: tài khoản này thuộc nhóm người dùng cần nhà phát triển Mini App xác minh và áp dụng các cơ chế xử lý dữ liệu phù hợp theo quy định Pháp luật, có thể bao gồm nhưng không giới hạn người đã chết hoặc mất tích, người không biết chữ, người khuyết tật, trẻ em,… - `false`: tài khoản này thuộc nhóm người dùng bình thường. |
