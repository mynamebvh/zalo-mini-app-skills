# createCameraContext

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/createCameraContext
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

Nhằm đơn giản hóa cách truy cập và sử dụng camera/micro trên nền tảng MiniApp, SDK cung cấp class **ZMACamera** với các
chức năng như thay đổi động thông số streaming, tắt/bật camera/micro, chuyển camera, chụp ảnh với cấu hình tùy chọn, và
lắng nghe các sự kiện liên quan đến camera (vd: frame realtime callback khi streaming camera).

**Lưu ý**:

- Các hàm thay đổi trạng thái streaming (start, pause, resume, updateMediaConstraints, setDeviceId, flip) sẽ trả về một
  Promise, bạn cần sử dụng await hoặc .then() để đảm bảo không xung đột trạng thái dẫn đến các chức năng hoạt động không
  như mong đợi.
- Sau khi sử dụng xong, bạn nên gọi hàm [stop](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/stop) để giải phóng camera/micro. Vì lý do privacy của
  user khi app xuống background sẽ stop streaming, nếu app muốn tiếp tục streaming khi quay lại foreground thì cần gọi
  lại hàm [start](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start).

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| videoElement | HTMLVideoElement |  | true | thẻ video chính để render stream từ camera |  |
| mediaConstraints | [MediaConstraints](#mediaconstraints-object) | `width`: 1024,   `height`: 768,   `facingMode`: FacingMode.FRONT,   `mirrored`: false,   `audio`: false,   `video`: true |  | Cấu hình khởi tạo streaming. Mặc định chỉ lấy stream từ camera, |  |

### MediaConstraints *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| width | number |  |  | Chiều rộng của video |  |
| height | number |  |  | Chiều cao của video |  |
| facingMode | [FacingMode](#facingmode-enum) |  |  | Hướng camera |  |
| deviceId | string |  |  | deviceId camera cần sử dụng. DeviceId lấy từ [getCameraList](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getCameraList) |  |
| video | boolean |  |  | Bật/tắt stream camera |  |
| audio | boolean |  |  | Bật/tắt stream micro |  |
| mirrored | boolean |  |  | Chế độ gương, lật ngược ảnh |  |

### FacingMode *enum*

- **FRONT**: Camera trước
- **BACK**: Camera sau

## Return Values

### <ZMACamera *object*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| [start](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start) | function | Bắt đầu streaming từ camera |  |
| [stop](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/stop) | function | Kết thúc streaming từ camera |  |
| [pause](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/pause) | function | Tạm dừng streaming |  |
| [resume](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/resume) | function | Tiếp tục lại streaming |  |
| [isUsing](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/isUsing) | function | Kiểm tra trạng thái streaming |  |
| [updateMediaConstraints](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/updateMediaConstraints) | function | Update cấu hình streaming |  |
| [takePhoto](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto) | function | Chụp ảnh từ camera |  |
| [flip](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/flip) | function | Chuyển camera trước/sau |  |
| [setMirror](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setMirror) | function | Bật/tắt chế độ gương cho ảnh. |  |
| [getCameraList](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getCameraList) | function | Lấy danh sách camera mà thiết bị có thể sử dụng |  |
| [getSelectedDeviceId](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getSelectedDeviceId) | function | Lấy deviceId của camera đang active |  |
| [setDeviceId](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setDeviceId) | function | Chuyển camera active bằng deviceId |  |
| [on](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/on) | function | Lắng nghe các sự kiện CameraEvents |  |
| [off](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/off) | function | Ngừng lắng nghe sự kiện CameraEvents |  |

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
