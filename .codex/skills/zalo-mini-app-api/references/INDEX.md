# Zalo Mini App API — Reference Index

> Crawled from https://docs.zaloplatforms.com/docs/MA/api (last updated 28/10/2026; accessed 2026-11-02).

## Getting started

- [Introduction](intro.md) — Zalo Mini App API provides APIs for interacting with the Zalo app. Some APIs require you to submit a review request before they can be used.
- [Events](events.md) — Adds a function to the end of the array of existing handler functions for the event named **eventName**. When the event occurs, all handler functions for that event are called.
- [Error codes](errorCode.md) — Most APIs in the ZMP SDK return a Promise when used, so you can get the returned result and handle errors as follows:
- [Changelog](changelog.md)

## User

- [Authorization](user/authorization/authorize.md) — Some APIs require the user's permission before they can be called. These APIs are divided into multiple scopes, each corresponding to a purpose of use; see the Scopes table for detailed descriptions:

### User information

- [getAccessToken](user/user-information/getAccessToken.md) — API used to get user authentication information.
- [getPhoneNumber](user/user-information/getPhoneNumber.md) — Get the user's phone number information. When the API is called, a permission request notification will be displayed. The Mini App can only obtain the phone number information if the user agrees to grant permission to share the phone number.
- [getUserID](user/user-information/getUserID.md) — API that allows retrieving the user ID. The ID is the user identifier string according to the Zalo App. This string is unique for each user on each Zalo App ID. Mini Apps sharing the same Zalo App ID can use this string to identify users. (This API does not require user confirmation.)
- [getUserInfo](user/user-information/getUserInfo.md) — API that retrieves user information including:

### Settings

- [getSetting](user/setting/getSetting.md) — API that gets the user's current settings.

## Basics

### Basic APIs

- [getAppInfo](basics/getAppInfo.md) — API to retrieve information about the current Zalo Mini App.
- [getContextAsync](basics/getContextAsync.md) — API that returns the context information of the user or group when the Mini App is opened from the extended Menu in the Zalo chat window.
- [getDeviceIdAsync](basics/getDeviceIdAsync.md) — API that returns the hashed Device ID string of the device. Different user accounts logged in on the same device and using the same Mini App (or Mini Apps that share the same Zalo App ID) will have the same Device ID value. If the Device ID cannot be obtained, the returned value is `unknown`.
- [getSystemInfo](basics/getSystemInfo.md) — API to retrieve system information about the device being used.

## Routing

### Routing APIs

- [closeApp](routing/closeApp.md) — API that requests to close the Zalo Mini App.
- [getRouteParams](routing/getRouteParams.md) — API that retrieves the parameters passed to the current page.
- [openMiniApp](routing/openMiniApp.md) — API used to open another Zalo Mini App. It can open a specific path inside that Mini App, or attach additional parameters.
- [openWebview](routing/openWebview.md) — Loads a web page using Webview.
- [sendDataToPreviousMiniApp](routing/sendDataToPreviousMiniApp.md) — Send data to the previous Zalo Mini App.

## Storage

### Native storage

- [clear](native-storage/clear.md) — Deletes all data in the cache using the synchronous mechanism.
- [getItem](native-storage/getItem.md) — Gets data stored in the cache using the synchronous mechanism.
- [getStorageInfo](native-storage/getNativeStorageInfo.md) — Gets information about the cache using the synchronous mechanism.
- [removeItem](native-storage/removeItem.md) — Deletes data in the cache using the synchronous mechanism.
- [setItem](native-storage/setItem.md) — Stores data to the cache synchronously. The data is saved on the user's device. The oldest data is deleted if the memory limit (5MB) is reached.

### Local file storage

- [getFileInfo](lfs/getFileInfo.md) — Get local file information. The file can be temporary or persistently stored (local cache or local data).
- [getSavedFileList](lfs/getSavedFileList.md) — Get information about all saved local data files of the mini app.
- [isSupportLFS](lfs/isSupportLFS.md) — Check whether LFS is supported.
- [Local file overview](lfs/localFileSystem.md) — During the use of APIs (e.g. [openMediaPicker](https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker), [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile)), local files are generated. Based on the purpose of use, local files are divided into the following 2 types:
- [removeSavedFile](lfs/removeSavedFile.md) — Delete a saved local file.
- [saveFile](lfs/saveFile.md) — Save a file from the **network** or a **temporary file** to local storage (local data). Supports downloading files with the formats listed [**here**](https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile#support-file-type).

## UI

### Feedback

- [closeLoading](user-interface/interative/closeLoading.md) — When the user opens the Zalo Mini App, a loading screen is displayed while the Mini App is loading. This screen is called Splash Loading.
- [showToast](user-interface/interative/showToast.md) — API that displays a short notification on the screen.

### View

- [configAppView](user-interface/view/configAppView.md) — API to customize the main interface components on the Mini App, including:
- [setNavigationBarColor](user-interface/view/setNavigationBarColor.md) — API that sets the navigation bar color of the current page.
- [setNavigationBarLeftButton](user-interface/view/setNavigationBarLeftButton.md) — API that sets the left button on the navigation bar of the current page.
- [setNavigationBarTitle](user-interface/view/setNavigationBarTitle.md) — API that sets the title on the navigation bar of the current page.

### Keyboard

- [hideKeyboard](user-interface/keyboard/hideKeyboard.md) — API to hide the virtual keyboard.

## Location

### Location

- [getLocation](location/getLocation.md) — API to retrieve the user's current location. When the API is called, a permission request notification will be displayed. The Mini App can only obtain location information if the user agrees to grant location sharing permission.

## Media

### Camera

- [checkZaloCameraPermission](media/camera/checkZaloCameraPermission.md) — Allows a Mini App to check the Zalo app's camera access permission. Note: if running on an older Zalo version, an unsupported error will be reported
- [createCameraContext](media/camera/createCameraContext.md) — To simplify how the camera/microphone is accessed and used on the Mini App platform, the SDK provides the **ZMACamera** class with
- [requestCameraPermission](media/camera/requestCameraPermission.md) — Allows the app to request that the device grant camera access. Note: on iOS, permission is granted only the first time after Zalo is installed. If the user does not grant permission the first time it is shown, or revokes the permission while using the app, subsequent calls will also NOT show it again. If the user wants to grant permission again, they must go to the device settings.

### Camera context

- [CameraEvents](media/camera/cameraContext/CameraEvents.md) — Events from the camera
- [CameraContext.flip](media/camera/cameraContext/flip.md) — Switch between front/back camera
- [CameraContext.getCameraList](media/camera/cameraContext/getCameraList.md) — Get the list of cameras that the device can use. Note: the full list is only returned after [start](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start) has been called.
- [CameraContext.getSelectedDeviceId](media/camera/cameraContext/getSelectedDeviceId.md) — Get the deviceId of the currently active camera
- [CameraContext.isUsing](media/camera/cameraContext/isUsing.md) — Check the streaming status
- [CameraContext.off](media/camera/cameraContext/off.md) — Stop listening for camera events
- [CameraContext.on](media/camera/cameraContext/on.md) — Listen for camera events
- [CameraContext.pause](media/camera/cameraContext/pause.md) — Pause streaming
- [CameraContext.resume](media/camera/cameraContext/resume.md) — Resume streaming
- [CameraContext.setDeviceId](media/camera/cameraContext/setDeviceId.md) — Switch the active camera using deviceId
- [CameraContext.setMirror](media/camera/cameraContext/setMirror.md) — Enable/disable mirror mode for images.
- [CameraContext.start](media/camera/cameraContext/start.md) — Start camera streaming. If you also want to use the microphone, you can set the [MediaConstraints](https://docs.zaloplatforms.com/docs/MA/api/media/camera/createCameraContext#mediaconstraints-object) config with `audio` set to `true`, or call [resume](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/resume) with **StreamType**.AUDIO.
- [CameraContext.stop](media/camera/cameraContext/stop.md) — End streaming from the camera
- [CameraContext.takePhoto](media/camera/cameraContext/takePhoto.md) — Take a photo from the camera.
- [CameraContext.updateMediaConstraints](media/camera/cameraContext/updateMediaConstraints.md) — Update the streaming configuration.

### Files

- [chooseImage](media/file/chooseImage.md) — API for choosing images from the album or camera.
- [downloadFile](media/file/downloadFile.md) — API that supports downloading files to the device; the file size limits are as follows:
- [openDocument](media/file/openDocument.md) — API that allows the app to view documents (PDF) directly from a URL or a local file in [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem).
- [openMediaPicker](media/file/openMediaPicker.md) — Opens a media picker (camera, photos, files, videos) from the device.
- [saveImageToGallery](media/file/saveImageToGallery.md) — Saves an image to the device's media library.
- [saveVideoToGallery](media/file/saveVideoToGallery.md) — Saves a video to the device's media library; the file size limits are as follows:

## Device

### Network

- [getNetworkType](device/network/getNetworkType.md) — API to retrieve the current network connection type.
- [onNetworkStatusChange](device/network/onNetworkStatusChange.md) — Callback to listen for network change events.

### Contact

- [openPhone](device/contact/openPhone.md) — API that allows opening the call screen with a specific phone number.
- [openSMS](device/contact/openSMS.md) — API that opens the messaging app with a specific content and phone number.

### QR

- [scanQRCode](device/qr/scanQRCode.md) — Allows the app to open the QR Code scanning feature of the Zalo app and returns the result after the user scans successfully.

### Screen

- [keepScreen](device/screen/keepScreen.md) — API that allows the app to keep the screen on. For example: when playing a video. When exiting the app, this setting returns to the default to avoid keeping the screen always on.
- [Vibrate](device/vibrate.md) — API that vibrates the device.

### Biometric authentication

- [checkStateBioAuthentication](device/bio-authentication/checkStateBioAuthentication.md) — **checkStateBioAuthentication** lets the app check whether the biometric credentials have changed since the last time, for example when a fingerprint is added, Face ID is added, or fingerprints are reset. You can also use it to determine whether the device supports biometrics.
- [openBioAuthentication](device/bio-authentication/openBioAuthentication.md) — Lets the app open the device's biometric login UI. Note: only standard operating systems that are not rooted or jailbroken are supported.

## Permission

### Permission

- [openPermissionSetting](permission/openPermissionSetting.md) — API that opens the Permission Management window showing the permissions the user has granted to the Mini App. Users can change permission settings (grant more or revoke) here.
- [requestSendNotification](permission/requestSendNotification.md) — API that requests the user's permission to receive notifications via the Mini App OA. When the API is called, a notification is displayed.

## Zalo

### Zalo APIs

- [addRating](zalo/addRating.md) — API that opens the app rating dialog, supporting the recording of user feedback ratings about the quality of the Mini App.
- [createShortcut](zalo/createShortcut.md) — API that allows the app to create a shortcut on the home screen.
- [favoriteApp](zalo/favoriteApp.md) — API that adds the app to the user's favorites list in the Zalo Mini Apps Store.
- [followOA](zalo/followOA.md) — API that requests following an Official Account. When the API is called, a notification is displayed.
- [interactOA](zalo/interactOA.md) — API that requests that the user allow sending notifications through an Official Account. The API only displays a notification when permission needs to be requested from the user. Note: to help Mini App developers use the permission request flow effectively and in line with [section 3.3.4 of the Zalo Mini App policy](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp). The Mini App Team has provided some experience design suggestions as shown below. Developers need to explain clearly and visually the purpose of the permission request so that users can easily understand and agree to provide information.
- [minimizeApp](zalo/minimizeApp.md) — API that proactively minimizes the app. When the API is called, the Mini App is minimized into a floating icon at the corner of the screen, allowing users to temporarily use other Zalo features and return to your Mini App without reloading from the beginning.
- [openChat](zalo/openChat.md) — API that allows the app to open a chat window with a User or an Official Account. The message content can be pre-filled, but whether the message is sent depends on the user's decision.
- [openPostFeed](zalo/openPostFeed.md) — API that allows the app to open the share interface so users can share information to their Zalo journal.
- [openProfile](zalo/openProfile.md) — API that allows the app to open the profile of a User or an Official Account.
- [openProfilePicker](zalo/openProfilePicker.md) — API that opens a friend picker in Zalo; the API returns the list of selected people.
- [openShareSheet](zalo/openShareSheet.md) — API that allows the app to open the share interface so users can share information with Zalo friends.
- [requestUpdateZalo](zalo/requestUpdateZalo.md) — API that proactively directs users to the App Store/Google Play to update to the latest Zalo version.
- [unfollowOA](zalo/unfollowOA.md) — API that allows the app to display an interface requesting to unfollow an Official Account for the user to confirm.
- [viewOAQr](zalo/viewOAQr.md) — API that allows the app to display the OA's QR code.

## Advertising

### Advertising

- [displayAd](advertising/displayAd.md) — Displays an ad after it has loaded. The ad position is determined by the ID of each ad type.
- [loadAd](advertising/loadAd.md) — Loads ads. The following ad types are available:
- [refreshAd](advertising/refreshAd.md) — Clears the ad in the current session.
- [setupAd](advertising/setupAd.md) — Configures the information used to serve ads. Call this API when the app initializes.

## Widgets

### Widgets

- [showFunctionButtonWidget](widgets/showFunctionButtonWidget.md) — Function Button Widget: When the user taps this button, the Mini App will receive 1 interact token (valid for 1 hour).
- [showOAWidget](widgets/showOAWidget.md) — Follow OA Widget: When the user taps the "Follow" button on the widget, they will follow immediately without displaying a permission request bottom sheet. The OA information is taken from the OA that verified the Mini App.
