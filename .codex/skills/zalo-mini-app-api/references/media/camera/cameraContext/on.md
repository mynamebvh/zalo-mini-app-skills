# CameraContext.on

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/on
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Listen for camera events

### on(eventName, listener)

- eventName <[**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents)>: Event name
- listener <Function>: Event handler function

Add a function to the end of the array of existing handlers for the [**CameraEvents**](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/CameraEvents) event. When the event occurs, all handlers for that event are called.

```js
import { CameraEvents } from "zmp-sdk/apis";

const callback = (data) => {
  console.log(data);
};
camera.on(CameraEvents.OnFrameCallback, callback);
```