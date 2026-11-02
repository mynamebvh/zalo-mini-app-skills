# openBioAuthentication

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/bio-authentication/openBioAuthentication
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

Lets the app open the device's biometric login UI. Note: only standard operating systems that are not rooted or jailbroken are supported.

## Parameters

## Object *object*

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| secretData | string |  | true | Secret key used once for the authentication process. You can create secretData = hash(accessToken + eventTime) | 2.5.3 |
| ui | [object](#ui-object) |  |  |  | 2.5.3 |
| requireFingerprint | boolean |  |  | Use fingerprint only. Android only | 2.5.3 |
| success | function |  |  | Callback function when the API call succeeds | 2.5.3 |
| fail | function |  |  | Callback function when the API call fails | 2.5.3 |

### UI Object

| Property | Type | Default | Required | Description | Minimum Version |
| --- | --- | --- | --- | --- | --- |
| title | string | "Authenticate" |  | Title of the authentication form |  |
| subTitle | string | "Use your biometrics to authenticate" |  | Guidance text |  |
| negativeButtonText | string | "Close" |  | Title of the exit button |  |

#### Sample code

```js
import { openBioAuthentication } from "zmp-sdk/apis";

openBioAuthentication({
  secretData: "<secretData>",
  ui: {
    title: "Biometric login for my app",
    subTitle: "Log in using your biometric credential",
    negativeButtonText: "Cancel",
  },
  success: (data) => {},
  fail: (error) => {
    const { code } = error;
  },
});
```

Or

```jsx
import { openBioAuthentication } from "zmp-sdk/apis";

const openBioAuthenUI = async () => {
  try {
    const data = await openBioAuthentication({
      secretData: "<secretData>",
      ui: {
        title: "Biometric login for my app",
        subTitle: "Log in using your biometric credential",
        negativeButtonText: "Cancel",
      },
    });
  } catch (error) {
    const { code } = error;
  }
};
```
