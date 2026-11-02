# openPermissionSetting

> Source: https://docs.zaloplatforms.com/docs/MA/api/permission/openPermissionSetting
> Last updated: 28/10/2026
> Supported from: SDK 2.27.0

```ts
import { openPermissionSetting } from "zmp-sdk";
```

API mở cửa sổ Quản lý quyền mà người dùng đã cấp cho Mini App. Người dùng có thể thay đổi các thiết lập quyền (cấp thêm hoặc thu hồi) tại đây.

![openpermissionsetting](https://docs.zaloplatforms.com/assets/MA/img/api/openPermissionSetting/permission_setting_screen.jpeg)

## Ví dụ

Mở cửa sổ cài đặt quyền:

```ts
await openPermissionSetting();
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).
