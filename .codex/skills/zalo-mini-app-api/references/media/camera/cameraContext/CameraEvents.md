# CameraEvents

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Events from the camera

- **OnFrameCallback**: Event that returns a frame ([PhotoFrame](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto#photoframe-object)) in real time from the camera.

```js
import api, { CameraEvents, PhotoFrame } from "zmp-sdk";

const camera = api.createCameraContext({ videoElement });
camera.on(CameraEvents.OnFrameCallback, (data: PhotoFrame) => {
  const { data, width, height } = data;
});

//...camera.start
```

- **OnStartCallback**: Event for when streaming from the camera starts.

```js
import api, { CameraEvents } from "zmp-sdk";

const camera = api.createCameraContext({ videoElement });
camera.on(CameraEvents.OnStartCallback, () => {
  console.log("START STREAMING");
});

//...camera.start
```

- **OnStopCallback**: Event for when streaming from the camera ends.

```js
import api, { CameraEvents } from "zmp-sdk";

const camera = api.createCameraContext({ videoElement });
camera.on(CameraEvents.OnStopCallback, () => {
  console.log("STOP STREAMING");
});
//...camera.start
//...camera.stop
```