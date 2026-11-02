# CameraContext.pause

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/pause
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Pause streaming

### StreamType

- **VIDEO**: Stream Camera
- **AUDIO**: Stream Microphone

```js
import React, { useEffect, useRef } from "react";
import { Box, Button, Page, Text } from "zmp-ui";
import { createCameraContext, FacingMode, StreamType } from "zmp-sdk/apis";

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

      <Box mx={4} mb={4} mt={5}>
        <Box mt={5} flex alignContent={"center"}>
          <Button
            size={"small"}
            variant="primary"
            onClick={async () => await cameraRef.current?.start()}
          >
            Start Stream
          </Button>
        </Box>

        <Box className="mb-2" flex alignContent={"center"}>
          <Text className="mb-2 mr-2">Video:</Text>
          <Button
            size={"small"}
            variant="primary"
            onClick={async () => {
              await cameraRef.current?.resume(StreamType.VIDEO);
            }}
          >
            ON
          </Button>
          <Button
            size={"small"}
            variant="primary"
            onClick={async () => {
              await cameraRef.current?.pause(StreamType.VIDEO);
            }}
          >
            OFF
          </Button>
        </Box>

        <Box className="mb-2" flex alignContent={"center"}>
          <Text className="mb-2 mr-2">Audio:</Text>
          <Button
            size={"small"}
            variant="primary"
            onClick={async () => {
              await cameraRef.current?.resume(StreamType.AUDIO);
            }}
          >
            ON
          </Button>
          <Button
            size={"small"}
            variant="primary"
            onClick={async () => {
              await cameraRef.current?.pause(StreamType.AUDIO);
            }}
          >
            OFF
          </Button>
        </Box>
      </Box>
    </Page>
  );
};

export default HomePage;
```