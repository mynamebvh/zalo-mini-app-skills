# getFileInfo

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/getFileInfo
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Get local file information. The file can be temporary or persistently stored (local cache or local data).

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| filePath | string |  | true | Path to the file in the temporary folder or saved locally |  |
| digestAlgorithm | string | md5 |  | Hash algorithm to obtain the file summary; supports the following types:  - `md5` - `sha1` |  |
| success | function |  |  | Callback function when the api call succeeds |  |
| fail | function |  |  | Callback function when the api call fails |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| size | number | File size (byte size) |  |
| digest | string | Hash value calculated based on the file's parameters (including the file's size and name) |  |
| type | string | File type (e.g. image/jpeg, video/mp4) |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.getFileInfo({
  filePath: "[Path to file]",
  digestAlgorithm: "md5",
  success: (data) => {
    // handle when the api call succeeds
    const { size, digest, type } = data;
  },
  fail: (error) => {
    // handle when the api call fails
    console.log(error);
  },
});
```

// or

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

const getFileInfo = async () => {
  try {
    const { size, digest, type } = await LFSStorage.getFileInfo({
      filePath: "[Path to file]",
      digestAlgorithm: "md5",
    });
  } catch (error) {
    // handle when the api call fails
    console.log(error);
  }
};
```

## Errors

| Code | Message | Note |
| --- | --- | --- |
| -302 | File cannot be found. Please check your param again. |  |