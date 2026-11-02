# CameraContext.off

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/off
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Ngừng lắng nghe các sự kiện từ camera

### off(eventName)

- eventName <[**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents)>: Tên của sự kiện

Xoá tất cả hàm xử lý đã đăng ký cho sự kiện [**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents).

```js
import { CameraEvents } from "zmp-sdk/apis";

const onCallback = (data) => {
  console.log(data);
};
camera.on(CameraEvents.OnFrameCallback, onCallback);

// ...
camera.off(CameraEvents.OnFrameCallback);
```
