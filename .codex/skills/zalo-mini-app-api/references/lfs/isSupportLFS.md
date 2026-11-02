# isSupportLFS

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Kiểm tra xem LFS có được hỗ trợ không.

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

const isSupportLFS = async () => {
  try {
    const { support } = await LFSStorage.isSupportLFS();
    if (support) {
      // LFS được hỗ trợ
    } else {
      // LFS không được hỗ trợ
    }
  } catch (error) {
    // xử lý khi gọi api thất bại
    console.log(error);
  }
};
```
