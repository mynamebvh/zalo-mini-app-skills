---
name: zalo-mini-app-api
description: Use the Zalo Mini App JavaScript API (zmp-sdk) in a Mini App project. Covers installation, user authorization and scopes, user info, storage, local files, routing, UI, location, camera, media, device, permissions, Zalo social APIs, advertising, and widgets.
---

# Zalo Mini App — JavaScript API (zmp-sdk)

This skill packages the official Zalo Mini App API documentation and turns it into a reference you can use while implementing or debugging Mini App features.

- Source: <https://docs.zaloplatforms.com/docs/MA/api/intro>
- Accessed: 2026-11-02; the documentation states it was last updated on October 28, 2026.
- Package: `zmp-sdk`
- Scope: 93 pages — every API listed in the official introduction, plus events, error codes, and changelog.

## Installation

```bash
npm install zmp-sdk
```

Import each API by name:

```ts
import { getAppInfo, getUserInfo, authorize, showToast } from "zmp-sdk";
```

## Approval requirement

Some APIs require an approval request before they can be used in production. With an **Admin account of the app**, you can call every API during development without waiting for approval.

## How to use this skill

1. Find the API in the category map below or in `references/intro.md`.
2. Read its reference file before writing code. Each page documents the example, parameters, and return value.
3. For permission-gated APIs, read `references/user/authorization/authorize.md` first.
4. For error handling, read `references/errorCode.md`.
5. Do not invent parameters or return fields. If a page does not document something, say so.

## Category map

| Category | APIs | Reference |
| --- | --- | --- |
| Events | `on`, `once`, `off`, `removeAllListeners`, `onNetworkStatusChange` | `references/events.md` |
| User — Authorization | `authorize` | `references/user/authorization/` |
| User — Information | `getUserID`, `getUserInfo`, `getAccessToken`, `getPhoneNumber` | `references/user/user-information/` |
| User — Settings | `getSetting` | `references/user/setting/` |
| Basic | `getAppInfo`, `getSystemInfo`, `getDeviceIdAsync`, `getContextAsync` | `references/basics/` |
| Routing | `closeApp`, `openMiniApp`, `openWebview`, `sendDataToPreviousMiniApp`, `getRouteParams` | `references/routing/` |
| Storage | `setItem`, `getItem`, `removeItem`, `clear`, `getNativeStorageInfo` | `references/native-storage/` |
| Local File Storage | `isSupportLFS`, `getFileInfo`, `getSavedFileList`, `removeSavedFile`, `saveFile` | `references/lfs/` |
| UI — Feedback | `showToast`, `closeLoading` | `references/user-interface/interative/` |
| UI — View | `configAppView`, `setNavigationBarColor`, `setNavigationBarLeftButton`, `setNavigationBarTitle` | `references/user-interface/view/` |
| UI — Keyboard | `hideKeyboard` | `references/user-interface/keyboard/` |
| Location | `getLocation` | `references/location/` |
| Media — Camera | `createCameraContext`, `checkZaloCameraPermission`, `requestCameraPermission` | `references/media/camera/` |
| Media — Camera context | `start`, `stop`, `pause`, `resume`, `isUsing`, `updateMediaConstraints`, `takePhoto`, `flip`, `setMirror`, `getCameraList`, `getSelectedDeviceId`, `setDeviceId`, `on`, `off` | `references/media/camera/cameraContext/` |
| Media — Files | `chooseImage`, `openMediaPicker`, `saveImageToGallery`, `saveVideoToGallery`, `downloadFile`, `openDocument` | `references/media/file/` |
| Device — Network | `getNetworkType`, `onNetworkStatusChange` | `references/device/network/` |
| Device — Contact | `openPhone`, `openSMS` | `references/device/contact/` |
| Device — QR | `scanQRCode` | `references/device/qr/` |
| Device — Screen | `keepScreen` | `references/device/screen/` |
| Device — Vibrate | `vibrate` | `references/device/vibrate.md` |
| Device — Biometrics | `openBioAuthentication`, `checkStateBioAuthentication` | `references/device/bio-authentication/` |
| Permission | `requestSendNotification`, `openPermissionSetting` | `references/permission/` |
| Zalo | `openProfile`, `openProfilePicker`, `openChat`, `followOA`, `unfollowOA`, `openShareSheet`, `openPostFeed`, `createShortcut`, `viewOAQr`, `requestUpdateZalo`, `minimizeApp`, `favoriteApp`, `addRating`, `interactOA` | `references/zalo/` |
| Advertising | `setupAd`, `loadAd`, `displayAd`, `refreshAd` | `references/advertising/` |
| Widgets | `showOAWidget`, `showFunctionButtonWidget` | `references/widgets/` |
| Error codes | Error code table | `references/errorCode.md` |

## Core concepts

### Permissions and scopes

APIs that access user data require explicit consent. Scopes group those APIs:

| Scope | API | Data |
| --- | --- | --- |
| `scope.userInfo` | `getUserInfo` | Name, avatar, and other profile data |
| `scope.userLocation` | `getLocation` | User location |
| `scope.userPhonenumber` | `getPhoneNumber` | Phone number |
| `scope.camera` | `createCameraContext` | Camera |
| `scope.micro` | `createCameraContext` | Microphone |

Behavior when a permission-gated API is called:

- User has not decided yet: a consent dialog appears, and the API runs only after the user accepts.
- User already accepted: the API runs directly.
- User declined: the call fails with an error callback.

Use `authorize` to request up to three scopes at once (including user info). Use `getSetting` to read current consent, and `openPermissionSetting` to send the user to the app's permission settings.

```ts
import { authorize, getSetting } from "zmp-sdk";

const { authSetting } = await getSetting();

if (!authSetting["scope.userLocation"]) {
  await authorize({ scopes: ["scope.userLocation"] });
}
```

Best practice: request consent only when needed, explain why, and check `getSetting` before asking again.

### Camera lifecycle

`createCameraContext` returns a camera context that controls streaming:

```ts
const camera = await createCameraContext({ videoElement });
await camera.start();
// ...
await camera.stop();
```

- State-changing methods (`start`, `pause`, `resume`, `updateMediaConstraints`, `setDeviceId`, `flip`) return a Promise; always `await` them to avoid state conflicts.
- Call `stop()` when finished to release the camera and microphone.
- Streaming stops automatically when the app goes to the background; call `start()` again when it returns to the foreground.

### Storage vs. local files

- `setItem` / `getItem` / `removeItem` / `clear`: synchronous key-value storage on the user's device.
- LFS (`saveFile`, `getSavedFileList`, `getFileInfo`, `removeSavedFile`): stores files from temporary paths into local data, and reports local cache and local data usage.

### Routing between Mini Apps

- `openMiniApp` opens another Mini App; `sendDataToPreviousMiniApp` sends data back to the app that opened the current one.
- `getRouteParams` reads parameters passed to the current page.
- `openWebview` opens a web page inside Zalo.

### Events

`on`, `once`, `off`, and `removeAllListeners` subscribe to and clean up event handlers. Event names include `AppPaused`, `AppResumed`, `NetworkChanged`, `OnDataCallback`, and `OpenApp`.

```ts
import { on, off } from "zmp-sdk";

const handler = () => console.log("app resumed");
on("AppResumed", handler);
// later
off("AppResumed", handler);
```

### Errors and SDK versions

- Every API page links to the shared error code table. Read `references/errorCode.md` before mapping error codes to user-facing messages.
- Pages include a `Supported from` line when an API needs a minimum SDK, Android, or iOS version. Check it before using newer APIs.

## Rules for writing code

- Always `await` API calls that return a Promise, and wrap them in `try/catch` when the API can fail.
- Check consent with `getSetting` before calling permission-gated APIs; do not prompt on app launch.
- Release resources: call `stop()` on camera contexts and `closeLoading()` when a loading screen is no longer needed.
- Prefer the documented parameter names and return fields; do not rename them in destructuring.
- When an API requires a minimum SDK version, state the requirement in the code review or migration note.
- Do not add extra wrapper libraries around `zmp-sdk` for a single call.

## Pre-finish checklist

- [ ] `zmp-sdk` is installed and APIs are imported by name.
- [ ] Permission-gated APIs are preceded by a consent check.
- [ ] Promise-returning calls are awaited and errors are handled.
- [ ] Camera contexts are stopped when the screen unmounts.
- [ ] Error codes are mapped to user-facing messages.
- [ ] Required minimum SDK versions are satisfied.