# requestCameraPermission

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/requestCameraPermission
> Last updated: 28/10/2026
> Supported from: SDK 2.8.0

Allows the app to request that the device grant camera access. Note: on iOS, permission is granted only the first time after Zalo is installed. If the user does not grant permission the first time it is shown, or revokes the permission while using the app, subsequent calls will also NOT show it again. If the user wants to grant permission again, they must go to the device settings.

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
| userAllow | boolean | Takes the following values:  - true: the user grants permission - false: the user does not grant permission |  |
| message | string | Description of the status |  |

## Sample Code

```jsx
import { requestCameraPermission } from "zmp-sdk/apis";

requestCameraPermission({
  success: ({ userAllow, message }) => {
    if (userAllow) {
      // allowed to use the camera
    }
  },
  fail: (err) => {
    // handle the api call failure
    console.log(err);
  }
});
```

Or

```jsx
import { requestCameraPermission } from "zmp-sdk/apis";

const requestCamera = async () => {
  try {
    const { userAllow, message } = await requestCameraPermission({});
    if (userAllow) {
      // allowed to use the camera
    }
  } catch (error) {
    // handle the api call failure
    console.log(error);
  }
};
```