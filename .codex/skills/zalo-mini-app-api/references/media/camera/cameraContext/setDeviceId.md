# CameraContext.setDeviceId

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setDeviceId
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Chuyển camera active bằng deviceId

## Parameters

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| deviceId | string |  | true | DeviceId lấy từ [getCameraList](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getCameraList) |  |

```js
import React, { useEffect, useRef, useState } from "react";
import { Box, Button, Page, Select } from "zmp-ui";
const { Option } = Select;
import { createCameraContext, FacingMode } from "zmp-sdk/apis";

const HomePage = () => {
  const cameraRef = useRef(null);
  const videoRef = useRef(null);
  const [cameraList, setCameraList] = useState([]);
  const [deviceId, setDeviceId] = useState("");
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
            const list = camera?.getCameraList();
            if (list) {
              setCameraList(list);
            }
          }}
        >
          Start Stream
        </Button>
      </Box>
      {
        <Box className="mb-2" flex alignContent={"center"}>
          <Select
            label="Danh sách camera"
            value={deviceId}
            defaultValue={deviceId}
            onChange={(e) => {
              setDeviceId(String(e));
              cameraRef.current?.setDeviceId(String(e));
            }}
          >
            {cameraList.map((item, index) => {
              return (
                
              );
            })}
          </Select>
        </Box>
      }
    </Page>
  );
};

export default HomePage;
```
