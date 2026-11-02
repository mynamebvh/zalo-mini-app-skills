# getFileInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/getFileInfo
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Lấy thông tin local file. File có thể ở dạng tạm hoặc đã được lưu bền (local cache hoặc local data).

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| filePath | string |  | true | Đường dẫn tới file trong folder tạm hoặc đã lưu cục bộ |  |
| digestAlgorithm | string | md5 |  | Thuật toán băm để lấy file summary, hỗ trợ các loại sau:  - `md5` - `sha1` |  |
| success | function |  |  | Callback function khi gọi api thành công |  |
| fail | function |  |  | Callback function khi gọi api thất bại |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| size | number | Kích thước file (byte size) |  |
| digest | string | Giá trị băm được tính dựa trên thông số của file (gồm size và tên của file) |  |
| type | string | Kiểu file (Vd: image/jpeg, video/mp4) |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.getFileInfo({
  filePath: "[Đường dẫn tới file]",
  digestAlgorithm: "md5",
  success: (data) => {
    // xử lý khi gọi api thành công
    const { size, digest, type } = data;
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

const getFileInfo = async () => {
  try {
    const { size, digest, type } = await LFSStorage.getFileInfo({
      filePath: "[Đường dẫn tới file]",
      digestAlgorithm: "md5",
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
| -302 | File cannot be found. Please check your param again. |  |
