# checkStateBioAuthentication

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/bio-authentication/checkStateBioAuthentication
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

**checkStateBioAuthentication** lets the app check whether the biometric credentials have changed since the last time, for example when a fingerprint is added, Face ID is added, or fingerprints are reset. You can also use it to determine whether the device supports biometrics.

Note: biometrics are supported only on standard operating systems that are not rooted or jailbroken.

## Parameters

### Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| success | function |  |  | Callback function when the API call succeeds |  |
| fail | function |  |  | Callback function when the API call fails |  |

## Return Values

### Promise <Object *data*>

| Property | Type | Description | Minimum Version |
| --- | --- | --- | --- |
| bioState | string | Value used to verify whether the biometric login state has changed (changing a fingerprint, adding Face ID, and so on changes this value) | 2.5.3 |

## Sample Code

```jsx
import { checkStateBioAuthentication } from "zmp-sdk/apis";

checkStateBioAuthentication({
  success: (data) => {
    const { bioState } = data;
    // Biometrics are supported
  },
  fail: (err) => {
    // Biometrics are not supported
  }
});
```

Or

```jsx
import { checkStateBioAuthentication } from "zmp-sdk/apis";

const checkBioAuthState = async () => {
  try {
   const { bioState } = await checkStateBioAuthentication({});
  } catch (error) {
    // handle a failed API call
    console.log(error);
  }
};
```

### Error code

| Code | Error |
| --- | --- |
| 107 | The device has not set up a biometric lock. Check the device settings. |
| 100 | Unknown error |
