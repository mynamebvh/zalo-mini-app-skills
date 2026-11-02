# CameraEvents

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Các sự kiện từ camera

- **OnFrameCallback**: Sự kiện trả về frame ([PhotoFrame](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto#photoframe-object)) theo thời gian thực từ camera.

```js
import api, { CameraEvents, PhotoFrame } from "zmp-sdk";

const camera = api.createCameraContext({ videoElement });
camera.on(CameraEvents.OnFrameCallback, (data: PhotoFrame) => {
  const { data, width, height } = data;
});

//...camera.start
```

- **OnStartCallback**: Sự kiện bắt đầu streaming từ camera.

```js
import api, { CameraEvents } from "zmp-sdk";

const camera = api.createCameraContext({ videoElement });
camera.on(CameraEvents.OnStartCallback, () => {
  console.log("START STREAMING");
});

//...camera.start
```

- **OnStopCallback**: Sự kiện kết thúc streaming từ camera.

```js
import api, { CameraEvents } from "zmp-sdk";

const camera = api.createCameraContext({ videoElement });
camera.on(CameraEvents.OnStopCallback, () => {
  console.log("STOP STREAMING");
});
//...camera.start
//...camera.stop
```
