# createCameraContext

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/createCameraContext
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

To simplify how the camera/microphone is accessed and used on the Mini App platform, the SDK provides the **ZMACamera** class with
features such as dynamically changing streaming parameters, turning the camera/microphone on or off, switching cameras, taking photos with custom configuration, and
listening for camera-related events (e.g., realtime frame callback while streaming the camera).

**Note**:

- The functions that change the streaming state (start, pause, resume, updateMediaConstraints, setDeviceId, flip) return a
  Promise, so you need to use await or .then() to avoid state conflicts that cause the functions to behave unexpectedly.
- When you are done, you should call the [stop](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/stop) function to release the camera/microphone. For user privacy reasons,
  streaming stops when the app goes to the background, so if the app wants to continue streaming when it returns to the foreground, it needs to call
  the [start](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start) function again.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| videoElement | HTMLVideoElement |  | true | the main video element used to render the stream from the camera |  |
| mediaConstraints | [MediaConstraints](#mediaconstraints-object) | `width`: 1024,   `height`: 768,   `facingMode`: FacingMode.FRONT,   `mirrored`: false,   `audio`: false,   `video`: true |  | Configuration for initializing streaming. By default, only the stream from the camera is captured, |  |

### MediaConstraints *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| width | number |  |  | Width of the video |  |
| height | number |  |  | Height of the video |  |
| facingMode | [FacingMode](#facingmode-enum) |  |  | Camera direction |  |
| deviceId | string |  |  | deviceId of the camera to use. The DeviceId is obtained from [getCameraList](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getCameraList) |  |
| video | boolean |  |  | Turn the camera stream on/off |  |
| audio | boolean |  |  | Turn the microphone stream on/off |  |
| mirrored | boolean |  |  | Mirror mode, flips the image |  |

### FacingMode *enum*

- **FRONT**: Front camera
- **BACK**: Back camera

## Return Values

### <ZMACamera *object*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| [start](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start) | function | Start streaming from the camera |  |
| [stop](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/stop) | function | Stop streaming from the camera |  |
| [pause](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/pause) | function | Pause streaming |  |
| [resume](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/resume) | function | Resume streaming |  |
| [isUsing](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/isUsing) | function | Check the streaming status |  |
| [updateMediaConstraints](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/updateMediaConstraints) | function | Update the streaming configuration |  |
| [takePhoto](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto) | function | Take a photo from the camera |  |
| [flip](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/flip) | function | Switch between the front/back camera |  |
| [setMirror](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setMirror) | function | Turn mirror mode on/off for the image. |  |
| [getCameraList](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getCameraList) | function | Get the list of cameras available on the device |  |
| [getSelectedDeviceId](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getSelectedDeviceId) | function | Get the deviceId of the active camera |  |
| [setDeviceId](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setDeviceId) | function | Switch the active camera by deviceId |  |
| [on](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/on) | function | Listen for CameraEvents |  |
| [off](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/off) | function | Stop listening for CameraEvents |  |

## Sample Code

```js
import React, { useEffect, useRef } from "react";
import { Box, Page } from "zmp-ui";
import { createCameraContext, FacingMode } from "zmp-sdk/apis";

const HomePage = () => {
  const videoRef = useRef(null);
  useEffect(() => {
    const videoElement = videoRef.current;
    if (!videoElement) {
      console.log("Media component not ready");
      return;
    }
    const camera = createCameraContext({
        videoElement: videoElement,
        mediaConstraints: {
          width: 640,
          height: 480,
          facingMode: FacingMode.BACK,
          audio: false,
        },
      });
  }, []);

  return (
    <Page>
      <Box>
        
      </Box>
    </Page>
  );
};

export default HomePage;
```