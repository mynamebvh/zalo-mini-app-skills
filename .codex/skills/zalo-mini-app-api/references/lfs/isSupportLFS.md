# isSupportLFS

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Check whether LFS is supported.

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

const isSupportLFS = async () => {
  try {
    const { support } = await LFSStorage.isSupportLFS();
    if (support) {
      // LFS is supported
    } else {
      // LFS is not supported
    }
  } catch (error) {
    // handle when the api call fails
    console.log(error);
  }
};
```