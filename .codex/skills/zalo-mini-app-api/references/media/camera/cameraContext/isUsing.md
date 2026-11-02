# CameraContext.isUsing

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/isUsing
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Check the streaming status

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

    const isUsing = camera.isUsing();
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