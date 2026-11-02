# getSavedFileList

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/getSavedFileList
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Get information about all saved local data files of the mini app.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| success | function |  |  | Callback function when the api call succeeds |  |
| fail | function |  |  | Callback function when the api call fails |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| list | Array <FileInfo> | List of locally saved files |  |

## Entities

### FileInfo

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| filePath | string | Path to the file in the mini app's local folder. |  |
| size | number | File size (byte size) |  |
| createTime | number | Time the file was created |  |
| type | string | File type (e.g. image/jpeg, video/mp4) |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.getSavedFileList({
  success: (data) => {
    // handle when the api call succeeds
    const { list } = data;
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

const getSavedFileList = async () => {
  try {
    const { list } = await LFSStorage.getSavedFileList({});
  } catch (error) {
    // handle when the api call fails
    console.log(error);
  }
};
```