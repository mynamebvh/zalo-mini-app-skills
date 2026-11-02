# CameraContext.takePhoto

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Take a photo from the camera.

## Parameters

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| cameraFrameProps | [PhotoConstraint](#photoconstraint-object) |  |  | Configuration for the captured photo. |  |

### PhotoConstraint *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| width | number |  |  | Width of the image |  |
| height | number |  |  | Height of the image |  |
| format | [PhotoFormat](#photoformat-enum) | PhotoFormat.JPEG |  | Image format. |  |
| quality | [PhotoQuality](#photoquality-enum) | PhotoQuality.NORMAL |  | Compressed image quality. Note: for uncompressed PNG images, this parameter has no effect |  |
| mirrored | boolean |  |  | Enable mirror mode for the captured photo |  |
| useVideoSourceSize | boolean |  |  | The photo uses the intrinsic size of the video source |  |
| minScreenshotWidth | number |  |  | Minimum width of the photo frame |  |
| minScreenshotHeight | number |  |  | Minimum height of the photo frame |  |

Note: to determine the image size, the SDK uses the following order:

1. width, height: the photo follows these exact parameters; the aspect ratio relative to the video source is not guaranteed to be preserved.
2. useVideoSourceSize: uses the intrinsic size of the video source (`videoWidth`, `videoHeight`).
3. minScreenshotWidth, minScreenshotHeight: the photo preserves the aspect ratio relative to the video source, with the minimum size given by these parameters. (Recommended)

### PhotoFormat *enum*

- **WEBP**: "image/webp" (compressed image)
- **PNG**: "image/png" (uncompressed image)
- **JPEG**: "image/jpeg" (compressed image)

### PhotoQuality *enum*

- **HIGH**: "high"
- **NORMAL** = "normal"
- **LOW** = "low"

## Return Values

### PhotoFrame *object*

The function returns `null` when the camera is not streaming or a photo frame could not be created.

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| data | string |  |  | Data URL of the image |  |
| width | number |  |  | Width of the image |  |
| height | number |  |  | Height of the image |  |

```js
import React, { useEffect, useRef, useState } from "react";
import { Box, Button, Page } from "zmp-ui";
import { createCameraContext, FacingMode, PhotoFormat, PhotoFrame, PhotoQuality } from "zmp-sdk/apis";

const HomePage = () => {
  const cameraRef = useRef(null);
  const videoRef = useRef(null);
  const [data, setData] = useState("");
  useEffect(() => {
    const videoElement = videoRef.current;
    if (!videoElement) {
      console.log("Media component not ready");
      return;
    }
    if (!cameraRef.current) {
      cameraRef.current = createCameraContext({
        videoElement: videoElement,
        mediaConstraints: {
          width: 640,
          height: 480,
          facingMode: FacingMode.BACK,
          audio: false,
        },
      });
    }
  }, []);

  return (
    <Page>
      <Box>
        
        <img
          id="image"
          src={data}
          alt={""}
          style={{ width: "50vw", height: "auto", objectFit: "contain" }}
        ></img>
      </Box>

      <Box mt={5} flex alignContent={"center"}>
        <Button
          size={"small"}
          className="mb-2"
          variant="primary"
          onClick={async () => {
            const camera = cameraRef.current;
            await camera?.start();
          }}
        >
          Start Stream
        </Button>
      </Box>

      <Box className="mb-2" flex alignContent={"center"}>
        <Button
          size={"small"}
          variant="primary"
          onClick={() => {
            let result: PhotoFrame = cameraRef.current?.takePhoto({
              quality: PhotoQuality.NORMAL,
              format: PhotoFormat.JPEG,
              minScreenshotHeight: 1000,
            });
            if (result) {
              setData(result.data);
            } else {
              console.log("No data");
            }
          }}
        >
          Take Photo
        </Button>
      </Box>
    </Page>
  );
};

export default HomePage;
```