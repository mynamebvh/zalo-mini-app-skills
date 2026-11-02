# saveFile

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Save a file from the **network** or a **temporary file** to local storage (local data). Supports downloading files with the formats listed [**here**](https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile#support-file-type).

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| filePath | string |  | true | Path to the file on the **network** or a **temporary file** (returned after calling the openMediaPicker API) of the mini app |  |
| success | function |  |  | Callback function when the api call succeeds |  |
| fail | function |  |  | Callback function when the api call fails |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| savedPath | string | Path to the locally saved file |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.saveFile({
  filePath: "[Path to file]",
  success: (data) => {
    // handle when the api call succeeds
    const { savedPath } = data;
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

const saveFile = async () => {
  try {
    const { savedPath } = await LFSStorage.saveFile({
      filePath: "[Path to file]",
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
| -300 | Your max 10MB of local storage data is reached | The storage capacity of the local cache files folder is limited to 10MB. Delete unnecessary old files to be able to save more files. Refer to [Delete a saved local file](https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile) |
| -301 | Your device run out of storage |  |
| -302 | File cannot be found. Please check your param again. | File could not be found. There are 2 cases that lead to the error  - Path uses http (Only https is supported) - File does not exist |
| -303 | Please wait... We're still download the file. |  |
| -304 | No Internet connection. Please check your network settings. |  |
| -305 | Download failed. Please check your network or file path again. |  |