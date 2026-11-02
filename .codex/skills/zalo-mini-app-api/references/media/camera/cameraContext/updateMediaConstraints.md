# CameraContext.updateMediaConstraints

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/updateMediaConstraints
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Update the streaming configuration.

## Parameters

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| mediaConstraints | [MediaConstraints](https://docs.zaloplatforms.com/docs/MA/api/media/camera/createCameraContext#mediaconstraints-object) |  | true | Streaming configuration. |  |

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

  type STREAM_TYPE = {
    audio: boolean,
    video: boolean,
  };
  const startStream = async (type: STREAM_TYPE) => {
    const camera = cameraRef.current;
    const enableVideo = type.video;
    const enableAudio = type.audio;
    await camera?.updateMediaConstraints({
      audio: enableAudio,
      video: enableVideo,
    });

    if (!camera?.isUsing()) {
      await camera?.start();
    }
  };
  return (
    <Page>
      <Box>
        
      </Box>

      <Box mt={5} flex alignContent={"center"}>
        <Box flex alignContent={"center"}>
          <Button
            size={"small"}
            className="mb-2"
            variant="primary"
            onClick={async () => {
              await startStream({ audio: true, video: false });
            }}
          >
            Start Microphone
          </Button>
          <Button
            size={"small"}
            className="mb-2"
            variant="primary"
            onClick={async () => {
              await startStream({ audio: false, video: true });
            }}
          >
            Start Camera
          </Button>
          <Button
            size={"small"}
            className="mb-2"
            variant="primary"
            onClick={async () => {
              await startStream({ audio: true, video: true });
            }}
          >
            Start All
          </Button>
        </Box>
      </Box>
    </Page>
  );
};

export default HomePage;
```