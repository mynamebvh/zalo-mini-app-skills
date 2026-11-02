# checkZaloCameraPermission

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/camera/checkZaloCameraPermission
> Last updated: 28/10/2026
> Supported from: SDK 2.31.0

Allows a Mini App to check the Zalo app's camera access permission. Note: if running on an older Zalo version, an unsupported error will be reported

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| success | function |  |  | Callback function when the API call succeeds |  |
| fail | function |  |  | Callback function when the API call fails |  |

## Return Values

### Promise<Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| userAllow | boolean | Takes the following values:  - true: the user grants permission - false: the user does not grant permission |  |

## Sample Code

```jsx
import { checkZaloCameraPermission } from "zmp-sdk/apis";

checkZaloCameraPermission({
  success: ({ userAllow }) => {
    if (userAllow) {
      // camera usage is allowed
    }
  },
  fail: (err) => {
    // handle the failed API call
    console.log(err);
  }
});
```

Or

```jsx
import { checkZaloCameraPermission } from "zmp-sdk/apis";

const checkCamera = async () => {
  try {
    const { userAllow } = await checkZaloCameraPermission({});
    if (userAllow) {
      // camera usage is allowed
    }
  } catch (error) {
    // handle the failed API call
    console.log(error);
  }
};
```