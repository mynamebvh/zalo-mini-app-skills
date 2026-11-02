# saveFile

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Lưu file từ **network** hoặc **file tạm** về vùng nhớ cục bộ (local data). Hỗ trợ tải file với các định dạng được liệt kê tại [**đây**](https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile#support-file-type).

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| filePath | string |  | true | Đường dẫn tới file trên **network** hoặc **file tạm** (trả về sau khi gọi API openMediaPicker) của mini app |  |
| success | function |  |  | Callback function khi gọi api thành công |  |
| fail | function |  |  | Callback function khi gọi api thất bại |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| savedPath | string | Đường dẫn tới file đã được lưu cục bộ |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.saveFile({
  filePath: "[Đường dẫn tới file]",
  success: (data) => {
    // xử lý khi gọi api thành công
    const { savedPath } = data;
  },
  fail: (error) => {
    // xử lý khi gọi api thất bại
    console.log(error);
  },
});
```

// hoặc

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

const saveFile = async () => {
  try {
    const { savedPath } = await LFSStorage.saveFile({
      filePath: "[Đường dẫn tới file]",
    });
  } catch (error) {
    // xử lý khi gọi api thất bại
    console.log(error);
  }
};
```

## Errors

| Code | Message | Note |
| --- | --- | --- |
| -300 | Your max 10MB of local storage data is reached | Dung lượng của folder lưu trữ local cache files giới hạn là 10MB. Xóa file cũ không cần thiết để có thể lưu thêm file. Tham khảo [Xoá local file đã lưu](https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile) |
| -301 | Your device run out of storage |  |
| -302 | File cannot be found. Please check your param again. | Không tìm được file. Có 2 trường hợp dẫn đến lỗi  - Path sử dụng http (Chỉ hỗ trợ https) - File không tồn tại |
| -303 | Please wait... We're still download the file. |  |
| -304 | No Internet connection. Please check your network settings. |  |
| -305 | Download failed. Please check your network or file path again. |  |
