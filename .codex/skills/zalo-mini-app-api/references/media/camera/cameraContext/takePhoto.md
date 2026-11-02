# CameraContext.takePhoto

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Chụp ảnh từ camera.

## Parameters

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| cameraFrameProps | [PhotoConstraint](#photoconstraint-object) |  |  | Cấu hình cho ảnh chụp. |  |

### PhotoConstraint *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| width | number |  |  | Chiều rộng của ảnh |  |
| height | number |  |  | Chiều cao của ảnh |  |
| format | [PhotoFormat](#photoformat-enum) | PhotoFormat.JPEG |  | Định dạng ảnh. |  |
| quality | [PhotoQuality](#photoquality-enum) | PhotoQuality.NORMAL |  | Chất lượng ảnh nén. Lưu ý: với ảnh PNG không nén, thông số này không có tác dụng |  |
| mirrored | boolean |  |  | Bật chế độ gương cho ảnh chụp |  |
| useVideoSourceSize | boolean |  |  | Ảnh sẽ lấy theo kích thước nội tại của video source |  |
| minScreenshotWidth | number |  |  | Chiều rộng tối thiểu của khung ảnh |  |
| minScreenshotHeight | number |  |  | Chiều cao tối thiểu của khung ảnh |  |

Lưu ý: để xác định kích thước ảnh sdk sẽ lấy theo thứ tự sau:

1. width, height: ảnh sẽ theo đúng thông số này, không đảm bảo sẽ giữ đúng tỉ lệ ảnh so với video source.
2. useVideoSourceSize: sẽ lấy kích thước nội tại của video source (`videoWidth`, `videoHeight`).
3. minScreenshotWidth, minScreenshotHeight: ảnh đảm bảo giữ nguyên tỉ lệ ảnh so với video source, với kích thước tối thiểu theo thông số này. (Khuyến nghị dùng)

### PhotoFormat *enum*

- **WEBP**: "image/webp" (ảnh nén)
- **PNG**: "image/png" (ảnh không nén)
- **JPEG**: "image/jpeg" (ảnh nén)

### PhotoQuality *enum*

- **HIGH**: "high"
- **NORMAL** = "normal"
- **LOW** = "low"

## Return Values

### PhotoFrame *object*

Hàm trả về `null` khi camera chưa streaming hoặc không tạo được khung ảnh.

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| data | string |  |  | Data URL của ảnh |  |
| width | number |  |  | Chiều rộng của ảnh |  |
| height | number |  |  | Chiều cao của ảnh |  |

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
