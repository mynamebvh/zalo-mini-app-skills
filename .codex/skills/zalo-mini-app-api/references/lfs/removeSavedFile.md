# removeSavedFile

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

Delete a saved local file.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| filePath | string |  | true | Path to the file in the locally saved folder |  |
| success | function |  |  | Callback function when the api call succeeds |  |
| fail | function |  |  | Callback function when the api call fails |  |

## Sample Code

```jsx
import { LFSStorage } from 'zmp-sdk/apis';

LFSStorage.removeSavedFile({
  filePath: "Path to file",
  success: () => {
    // handle when the api call succeeds
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

const removeSavedFile = async () => {
  try {
    await LFSStorage.removeSavedFile({
      filePath: "Path to file",
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