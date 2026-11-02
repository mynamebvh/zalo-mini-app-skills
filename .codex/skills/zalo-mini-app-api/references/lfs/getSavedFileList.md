# getSavedFileList

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/getSavedFileList
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Lấy thông tin tất cả các local data file đã được lưu của mini app.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| success | function |  |  | Callback function khi gọi api thành công |  |
| fail | function |  |  | Callback function khi gọi api thất bại |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| list | Array <FileInfo> | Danh sách file đã lưu cục bộ |  |

## Entities

### FileInfo

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| filePath | string | Đường dẫn tới file trong folder cục bộ của mini app. |  |
| size | number | Kích thước file (byte size) |  |
| createTime | number | Thời gian file được tạo |  |
| type | string | Type của file (Vd: image/jpeg, video/mp4) |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.getSavedFileList({
  success: (data) => {
    // xử lý khi gọi api thành công
    const { list } = data;
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

const getSavedFileList = async () => {
  try {
    const { list } = await LFSStorage.getSavedFileList({});
  } catch (error) {
    // xử lý khi gọi api thất bại
    console.log(error);
  }
};
```
