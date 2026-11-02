# openPermissionSetting

> Source: https://docs.zaloplatforms.com/docs/MA/api/permission/openPermissionSetting
> Last updated: 28/10/2026
> Supported from: SDK 2.27.0

```ts
import { openPermissionSetting } from "zmp-sdk";
```

API that opens the Permission Management window showing the permissions the user has granted to the Mini App. Users can change permission settings (grant more or revoke) here.

![openpermissionsetting](https://docs.zaloplatforms.com/assets/MA/img/api/openPermissionSetting/permission_setting_screen.jpeg)

## Example

Open the permission settings window:

```ts
await openPermissionSetting();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).