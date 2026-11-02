# authorize

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/authorization/authorize
> Last updated: 28/10/2026
> Supported from: SDK 2.34.0, Android 23.12.02 (724), IOS 23.12.02 (573)

```ts
import { authorize } from "zmp-sdk";
```

### Cấp quyền sử dụng API

Một số API cần sự cho phép của người dùng trước khi có thể được gọi. Các API này được chia thành nhiều phạm vi (Scope) tương ứng với từng mục đích sử dụng, mô tả chi tiết tham khảo bảng Scopes:

| Scope | Corresponding APIs | Description |
| --- | --- | --- |
| `scope.userInfo` | `getUserInfo` | Thông tin user (tên, avatar...) |
| `scope.userLocation` | `getLocation` | Thông tin vị trí user |
| `scope.userPhonenumber` | `getPhoneNumber` | Số điện thoại |

Khi một API như vậy được gọi:

- Nếu người dùng chưa chấp nhận hoặc từ chối, một cửa sổ pop-up sẽ xuất hiện để hỏi người dùng có muốn chấp nhận không. API chỉ có thể được gọi sau khi người dùng bấm chấp nhận.
- Nếu người dùng đã chấp nhận cho phép, API có thể được gọi trực tiếp.
- Nếu người dùng từ chối cho phép, callback lỗi sẽ được trả về.

Developer có thể sử dụng API này để chủ động khởi tạo yêu cầu cấp quyền đối với người dùng khi cần, hỗ trợ xin tối đa 3 quyền (đã bao gồm quyền Thông tin user):

![Multi_API_Request](https://docs.zaloplatforms.com/assets/MA/img/authorize/multi_api_request_v2.png)

### Lấy trạng thái của scope

Developer có thể sử dụng API `getSetting` để lấy trạng thái cho phép hiện tại của người dùng.

### Quản lý cấp/thu hồi quyền cho người dùng

Developer có thể gọi API `openPermissionSetting` để mở cài đặt và hướng dẫn người dùng bật/tắt cho phép API.

![permission_settings](https://docs.zaloplatforms.com/assets/MA/img/authorize/permission_management.jpg)

### Thời gian hiệu lực

Sau khi user đồng ý hoặc từ chối cấp quyền, trạng thái cấp quyền sẽ được ghi nhận và đồng bộ cho những lần sử dụng sau này.

### Best Practices

- Chỉ khởi tạo yêu cầu cấp quyền khi cần thiết, giải thích rõ ràng lý do tại sao bạn muốn sử dụng nó trong yêu cầu cấp quyền.
- Sử dụng API `getSetting` trước để lấy trạng thái cho phép hiện tại của người dùng, sau đó yêu cầu xin cấp thêm các quyền còn thiếu.

## Ví dụ

Khởi tạo cấp quyền

```ts
try {
  const data = await authorize({
    scopes: ["scope.userLocation", "scope.userPhonenumber"],
  });
  console.log(data["scope.userLocation"]); // `true` nếu người dùng đồng ý cấp vị trí
  console.log(data["scope.userPhonenumber"]); // `true` nếu người dùng đồng ý cấp số điện thoại
} catch (error) {
  const code = (error as AppError).code;
  if (code === -201) {
    console.log("Người dùng đã từ chối cấp quyền");
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
| scopes | `string[]` | No | Danh sách các quyền cần được cấp, tham khảo bảng Scopes. Nếu không truyền, API mặc định xin quyền userInfo. |

## Kết quả trả về

API trả về `Promise<Scopes>` chứa chứa các trạng thái của các quyền được cấp.

### Scopes

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| userInfo | `boolean` | No | Trạng thái quyền thông tin user. |
| userLocation | `boolean` | No | Trạng thái quyền vị trí user. |
| userPhonenumber | `boolean` | No | Trạng thái quyền số điện thoại. |
