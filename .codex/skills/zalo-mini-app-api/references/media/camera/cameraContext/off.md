# CameraContext.off

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/off
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Stop listening for camera events

### off(eventName)

- eventName <[**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents)>: Event name

Remove all handlers registered for the [**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents) event.

```js
import { CameraEvents } from "zmp-sdk/apis";

const onCallback = (data) => {
  console.log(data);
};
camera.on(CameraEvents.OnFrameCallback, onCallback);

// ...
camera.off(CameraEvents.OnFrameCallback);
```