# CameraContext.flip

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/flip
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Switch between front/back camera

```js
import React, { useEffect, useRef } from "react";
import { Box, Button, Page } from "zmp-ui";
import { createCameraContext, FacingMode } from "zmp-sdk/apis";

const HomePage = () => {
  const cameraRef = useRef(null);
  const videoRef = useRef(null);
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
        
      </Box>

      <Box mt={5} flex alignContent={"center"}>
        <Button
          size={"small"}
          variant="primary"
          onClick={async () => await cameraRef.current?.start()}
        >
          Start Stream
        </Button>
        <Button
          size={"small"}
          variant="primary"
          onClick={async () => await cameraRef.current?.flip()}
        >
          Flip Camera
        </Button>
      </Box>
    </Page>
  );
};

export default HomePage;
```