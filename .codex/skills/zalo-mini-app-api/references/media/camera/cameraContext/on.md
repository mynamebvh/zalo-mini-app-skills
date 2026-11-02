# CameraContext.on

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/on
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Lắng nghe các sự kiện từ camera

### on(eventName, listener)

- eventName <[**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents)>: Tên của sự kiện
- listener <Function>: Hàm xử lý sự kiện

Thêm một hàm vào cuối mảng chứa hàm xử lý đã có của sự kiện [**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents). Khi sự kiện xảy ra, tất cả các hàm xử lý của sự kiện đó sẽ được gọi.

```js
import { CameraEvents } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};
camera.on(CameraEvents.OnFrameCallback, callback);
```
