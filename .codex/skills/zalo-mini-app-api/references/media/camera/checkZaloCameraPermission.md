# checkZaloCameraPermission

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/checkZaloCameraPermission
> Last updated: 28/10/2026
> Supported from: SDK 2.31.0

Cho phép mini app kiểm tra quyền truy cập camera của ứng dụng Zalo. Lưu ý: nếu chạy trên phiên bản Zalo cũ sẽ báo lỗi chưa hỗ trợ

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| success | function |  |  | Callback function khi gọi api thành công |  |
| fail | function |  |  | Callback function khi gọi api thất bại |  |

## Return Values

### Promise<Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| userAllow | boolean | Nhận các giá trị sau:  - true: user cấp quyền - false: user không cấp quyền |  |

## Sample Code

```jsx
import { checkZaloCameraPermission } from "zmp-sdk/apis";

checkZaloCameraPermission({
  success: ({ userAllow }) => {
    if (userAllow) {
      // được phép sử dụng camera
    }
  },
  fail: (err) => {
    // xử lý khi gọi api thất bại
    console.log(err);
  }
});
```

Hoặc

```jsx
import { checkZaloCameraPermission } from "zmp-sdk/apis";

const checkCamera = async () => {
  try {
    const { userAllow } = await checkZaloCameraPermission({});
    if (userAllow) {
      // được phép sử dụng camera
    }
  } catch (error) {
    // xử lý khi gọi api thất bại
    console.log(error);
  }
};
```
