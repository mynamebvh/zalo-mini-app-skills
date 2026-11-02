# requestCameraPermission

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/requestCameraPermission
> Last updated: 28/10/2026
> Supported from: SDK 2.8.0

Cho phép ứng dụng yêu cầu device cấp quyền truy cập camera. Lưu ý: đối với IOS, chỉ cấp quyền lần đầu khi cài app Zalo. Nếu user không cấp quyền trong lần đầu hiển thị, hoặc thu hồi quyền trong quá trình sử dụng thì lần gọi sau cũng KHÔNG hiển thị lại. Nếu user muốn cấp quyền lại phải vào setting của device.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| success | function |  |  | Callback function khi gọi api thành công |  |
| fail | function |  |  | Callback function khi gọi api thất bại |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| userAllow | boolean | Nhận các giá trị sau:  - true: user cấp quyền - false: user không cấp quyền |  |
| message | string | Mô tả trạng thái |  |

## Sample Code

```jsx
import { requestCameraPermission } from "zmp-sdk/apis";

requestCameraPermission({
  success: ({ userAllow, message }) => {
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
import { requestCameraPermission } from "zmp-sdk/apis";

const requestCamera = async () => {
  try {
    const { userAllow, message } = await requestCameraPermission({});
    if (userAllow) {
      // được phép sử dụng camera
    }
  } catch (error) {
    // xử lý khi gọi api thất bại
    console.log(error);
  }
};
```
