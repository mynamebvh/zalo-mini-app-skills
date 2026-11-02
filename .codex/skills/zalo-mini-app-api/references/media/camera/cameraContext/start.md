# CameraContext.start

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Bắt đầu streaming camera. Nếu bạn muốn sử dụng thêm micro thì có thể đặt config [MediaConstraints](https://docs.zaloplatforms.com/docs/MA/api/media/camera/createCameraContext#mediaconstraints-object) với `audio` là `true`, hoặc gọi [resume](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/resume) với **StreamType**.AUDIO.

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
    </Page>
  );
};

export default HomePage;
```
