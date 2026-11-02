# getSetting

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/setting/getSetting
> Last updated: 28/10/2026
> Supported from: SDK 2.31.0

```ts
import { getSetting } from "zmp-sdk";
```

API lấy thông tin cài đặt hiện tại của người dùng.

## Ví dụ

Lấy thông tin cài đặt hiện tại của người dùng:

```ts
const { authSetting } = await getSetting();
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<GetSettingReturn>` chứa chứa thông tin cài đặt hiện tại của người dùng.

### GetSettingReturn

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| authSetting | `AuthorizeType` | No | Thông tin cấp quyền, tham khảo bảng [Scopes](#scopes). Với các scope có giá trị trả về là `true`, tương ứng với việc người dùng đã cấp quyền sử dụng API trước đó, Mini Apps có thể truy xuất thông tin một cách trực tiếp. |

## Scopes

| Scope | Corresponding APIs | Description |
| --- | --- | --- |
| scope.userInfo | `getUserInfo` | Thông tin user (tên, avatar...) |
| scope.userLocation | `getLocation` | Thông tin vị trí user |
| scope.userPhonenumber | `getPhoneNumber` | Số điện thoại |
| scope.camera | `createCameraContext` | Camera |
| scope.micro | `createCameraContext` | Micro |
