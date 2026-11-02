# removeSavedFile

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Xoá local file đã lưu.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| filePath | string |  | true | Đường dẫn tới file trong folder đã lưu cục bộ |  |
| success | function |  |  | Callback function khi gọi api thành công |  |
| fail | function |  |  | Callback function khi gọi api thất bại |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.removeSavedFile({
  filePath: "Đường dẫn tới file",
  success: () => {
    // xử lý khi gọi api thành công
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

const removeSavedFile = async () => {
  try {
    await LFSStorage.removeSavedFile({
      filePath: "Đường dẫn tới file",
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
