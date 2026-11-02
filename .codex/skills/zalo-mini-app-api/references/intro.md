# Introduction

> Source: https://docs.zaloplatforms.com/docs/MA/api/intro
> Last updated: 28/10/2026

Zalo Mini App API provides APIs for interacting with the Zalo app. Some APIs require you to submit a review request before they can be used.

> **Tip**
>
> With an **App Admin** account, you can use all APIs during app development without waiting for review.

## Installation

```sh
npm install zmp-sdk
```

## Events API

| Name | Description | Note |
| --- | --- | --- |
| [on](https://docs.zaloplatforms.com/docs/MA/api/events#oneventname-listener) | Adds a handler function for an event. When the event occurs, all handler functions for that event are called |  |
| [once](https://docs.zaloplatforms.com/docs/MA/api/events#onceeventname-listener) | Adds a one-time handler function for an event. When the event occurs, this handler is removed and then executed |  |
| [off](https://docs.zaloplatforms.com/docs/MA/api/events#offeventname-listener) | Removes a specific handler function from the event's array of handler functions |  |
| [removeAllListeners](https://docs.zaloplatforms.com/docs/MA/api/events#removealllistenerseventname) | Removes all handler functions for the event |  |
| onConfirmToExit | Used to listen for the event when the user taps to close the Mini App | No longer supported |
| offConfirmToExit | Cancels listening for the event when the user taps to close the Mini App | No longer supported |
| [onNetworkStatusChange](https://docs.zaloplatforms.com/docs/MA/api/device/network/onNetworkStatusChange) | Used to listen for network change events |  |

## Events Name

| Name | Description |
| --- | --- |
| [AppPaused](https://docs.zaloplatforms.com/docs/MA/api/events#apppaused) | This event occurs when Zalo Mini App moves from foreground to background |
| [AppResumed](https://docs.zaloplatforms.com/docs/MA/api/events#appresumed) | This event occurs when Zalo Mini App moves from background to foreground |
| [NetworkChanged](https://docs.zaloplatforms.com/docs/MA/api/events#networkchanged) | This event occurs when a network connection change is detected |
| [OnDataCallback](https://docs.zaloplatforms.com/docs/MA/api/events#ondatacallback) | This event occurs when data is received from a previously opened Mini App |
| [OpenApp](https://docs.zaloplatforms.com/docs/MA/api/events#openapp) | This event occurs when Zalo Mini App is reopened from background mode (not fully closed) |

## User

### Authorization

| Name | Description |
| --- | --- |
| [authorize](https://docs.zaloplatforms.com/docs/MA/api/user/authorization/authorize) | Grants permission to use the API |

### User Information

| Name | Description |
| --- | --- |
| [getUserID](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getUserID) | Gets the user's ID |
| [getUserInfo](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getUserInfo) | Gets user information |
| [getAccessToken](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getAccessToken) | Gets the token used to identify the user |
| [getPhoneNumber](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getPhoneNumber) | Gets the user's phone number information |

### User Settings

| Name | Description |
| --- | --- |
| [getSetting](https://docs.zaloplatforms.com/docs/MA/api/user/setting/getSetting) | Gets the user's current settings information. |

## Basic

| Name | Description |
| --- | --- |
| [getAppInfo](https://docs.zaloplatforms.com/docs/MA/api/basics/getAppInfo) | Gets Zalo Mini App information |
| [getSystemInfo](https://docs.zaloplatforms.com/docs/MA/api/basics/getSystemInfo) | Gets Zalo App and device information |
| [getDeviceIdAsync](https://docs.zaloplatforms.com/docs/MA/api/basics/getDeviceIdAsync) | Gets a unique identifier string for each device. |
| [getContextAsync](https://docs.zaloplatforms.com/docs/MA/api/basics/getContextAsync) | Gets information about the context in which Zalo Mini App was opened |

## Routing

| Name | Description |
| --- | --- |
| [closeApp](https://docs.zaloplatforms.com/docs/MA/api/routing/closeApp) | Closes the Mini App |
| [openMiniApp](https://docs.zaloplatforms.com/docs/MA/api/routing/openMiniApp) | Opens a Mini App |
| [openWebview](https://docs.zaloplatforms.com/docs/MA/api/routing/openWebview) | Opens a webview |
| [sendDataToPreviousMiniApp](https://docs.zaloplatforms.com/docs/MA/api/routing/sendDataToPreviousMiniApp) | Sends data to the previous Mini App |
| [getRouteParams](https://docs.zaloplatforms.com/docs/MA/api/routing/getRouteParams) | Gets the params sent to the current page of the Mini App |

## Storage

| Name | Description |
| --- | --- |
| [setItem](https://docs.zaloplatforms.com/docs/MA/api/native-storage/setItem) | Stores data in the cache synchronously. The data is saved on the user's device. |
| [getItem](https://docs.zaloplatforms.com/docs/MA/api/native-storage/getItem) | Gets data stored in the cache synchronously |
| [removeItem](https://docs.zaloplatforms.com/docs/MA/api/native-storage/removeItem) | Removes data stored in the cache synchronously |
| [clear](https://docs.zaloplatforms.com/docs/MA/api/native-storage/clear) | Removes all data stored in the cache synchronously |
| [getStorageInfo](https://docs.zaloplatforms.com/docs/MA/api/native-storage/getNativeStorageInfo) | Gets cache information synchronously |

## Local File Storage

| Name | Description |
| --- | --- |
| [Local file overview](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem) | Provides an overview of the Mini App's local file system. |
| [isSupportLFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS) | Checks whether LFS is supported. |
| [getFileInfo](https://docs.zaloplatforms.com/docs/MA/api/lfs/getFileInfo) | Gets local file information (local cache or local data). |
| [getSavedFileList](https://docs.zaloplatforms.com/docs/MA/api/lfs/getSavedFileList) | Gets information about all saved local files of the Mini App. |
| [removeSavedFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile) | Removes a saved local file. |
| [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) | Saves a file from a temporary path to local storage (local data) |

## UI

### Feedback

| Name | Description |
| --- | --- |
| [showToast](https://docs.zaloplatforms.com/docs/MA/api/user-interface/interative/showToast) | Displays a toast that automatically hides after a period of time |
| [closeLoading](https://docs.zaloplatforms.com/docs/MA/api/user-interface/interative/closeLoading) | Closes the Splash Loading screen |

### View

| Name | Description |
| --- | --- |
| [configAppView](https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/configAppView) | Hides/shows and customizes the color and display style of the status bar, action bar, bottom navigation (Android) / safe area inset bottom (iOS) |
| [setNavigationBarColor](https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarColor) | Resets the navigation bar color of the current page |
| [setNavigationBarLeftButton](https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarLeftButton) | Resets the left button (Home, Back) on the navigation bar of the current page |
| [setNavigationBarTitle](https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarTitle) | Resets the title on the navigation bar of the current page |

### Keyboard

| Name | Description |
| --- | --- |
| [hideKeyboard](https://docs.zaloplatforms.com/docs/MA/api/user-interface/keyboard/hideKeyboard) | Hides the keyboard |

## Location

| Name | Description |
| --- | --- |
| [getLocation](https://docs.zaloplatforms.com/docs/MA/api/location/getLocation) | Gets the user's current location |

## Media

### Camera

| Name | Description |
| --- | --- |
| [createCameraContext](https://docs.zaloplatforms.com/docs/MA/api/media/camera/createCameraContext) | Creates a streaming management object |
| [start](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/start) | Starts streaming from the camera |
| [stop](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/stop) | Stops streaming from the camera |
| [pause](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/pause) | Pauses streaming |
| [resume](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/resume) | Resumes streaming |
| [isUsing](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/isUsing) | Checks the streaming status |
| [updateMediaConstraints](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/updateMediaConstraints) | Updates the streaming configuration |
| [takePhoto](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/takePhoto) | Takes a photo from the camera |
| [flip](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/flip) | Switches between front and rear camera |
| [setMirror](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setMirror) | Turns mirror mode on/off for images. |
| [getCameraList](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getCameraList) | Gets the list of active cameras on the phone |
| [getSelectedDeviceId](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/getSelectedDeviceId) | Gets the deviceId of the active camera |
| [setDeviceId](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/setDeviceId) | Switches the active camera by deviceId |
| [on](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/on) | Listens for CameraEvents |
| [off](https://docs.zaloplatforms.com/docs/MA/api/media/camera/cameraContext/off) | Stops listening for CameraEvents |
| [checkZaloCameraPermission](https://docs.zaloplatforms.com/docs/MA/api/media/camera/checkZaloCameraPermission) | Lets the app check Zalo's camera access permission |
| [requestCameraPermission](https://docs.zaloplatforms.com/docs/MA/api/media/camera/requestCameraPermission) | Lets the app request camera access permission from the device |

### Media

| Name | Description |
| --- | --- |
| [chooseImage](https://docs.zaloplatforms.com/docs/MA/api/media/file/chooseImage) | Selects an image from the album or camera |
| [openMediaPicker](https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker) | Opens the media picker (camera, photos, files, videos) on the device |
| [saveImageToGallery](https://docs.zaloplatforms.com/docs/MA/api/media/file/saveImageToGallery) | Saves an image to the device's media library |
| [saveVideoToGallery](https://docs.zaloplatforms.com/docs/MA/api/media/file/saveVideoToGallery) | Saves a video to the device's media library |
| [downloadFile](https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile) | Downloads a file to the device |
| [openDocument](https://docs.zaloplatforms.com/docs/MA/api/media/file/openDocument) | Opens a PDF document from a URL |

## Device

### Network

| Name | Description |
| --- | --- |
| [getNetworkType](https://docs.zaloplatforms.com/docs/MA/api/device/network/getNetworkType) | Gets network connection information |
| [downloadFile](https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile) | Downloads a file to the device |

### Contact

| Name | Description |
| --- | --- |
| [openPhone](https://docs.zaloplatforms.com/docs/MA/api/device/contact/openPhone) | Opens the device's phone app |
| [openSMS](https://docs.zaloplatforms.com/docs/MA/api/device/contact/openSMS) | Opens the device's messaging app |

### Screen

| Name | Description |
| --- | --- |
| [keepScreen](https://docs.zaloplatforms.com/docs/MA/api/device/screen/keepScreen) | Keeps the screen on |

### Vibrate

| Name | Description |
| --- | --- |
| [vibrate](https://docs.zaloplatforms.com/docs/MA/api/device/vibrate) | Triggers the device's vibration mode |

### Biometric Authentication

| Name | Description |
| --- | --- |
| [openBioAuthentication](https://docs.zaloplatforms.com/docs/MA/api/device/bio-authentication/openBioAuthentication) | Opens the biometric login interface |
| [checkStateBioAuthentication](https://docs.zaloplatforms.com/docs/MA/api/device/bio-authentication/checkStateBioAuthentication) | Checks biometric authentication information |

## Permission

| Name | Description |
| --- | --- |
| [requestSendNotification](https://docs.zaloplatforms.com/docs/MA/api/permission/requestSendNotification) | Asks the user to allow the app to send notifications via OA Mini App |
| [openPermissionSetting](https://docs.zaloplatforms.com/docs/MA/api/permission/openPermissionSetting) | Opens the settings screen for permissions the user has granted to the app |

## Zalo

| Name | Description |
| --- | --- |
| [openProfile](https://docs.zaloplatforms.com/docs/MA/api/zalo/openProfile) | Opens the profile screen of a user or Official Account |
| [openProfilePicker](https://docs.zaloplatforms.com/docs/MA/api/zalo/openProfilePicker) | Opens the friend picker in Zalo |
| [openChat](https://docs.zaloplatforms.com/docs/MA/api/zalo/openChat) | Opens the chat window with a user or Official Account |
| [followOA](https://docs.zaloplatforms.com/docs/MA/api/zalo/followOA) | Follows an Official Account |
| [unfollowOA](https://docs.zaloplatforms.com/docs/MA/api/zalo/unfollowOA) | Unfollows an Official Account |
| [openShareSheet](https://docs.zaloplatforms.com/docs/MA/api/zalo/openShareSheet) | Opens the share sheet in Zalo |
| [openPostFeed](https://docs.zaloplatforms.com/docs/MA/api/zalo/openPostFeed) | Opens the share-to-journal window in Zalo |
| [createShortcut](https://docs.zaloplatforms.com/docs/MA/api/zalo/createShortcut) | Creates a shortcut for the Mini App on the device home screen |
| [viewOAQr](https://docs.zaloplatforms.com/docs/MA/api/zalo/viewOAQr) | Displays the Official Account's QR code |
| [requestUpdateZalo](https://docs.zaloplatforms.com/docs/MA/api/zalo/requestUpdateZalo) | Proactively directs the user to the App Store/Google Play to update to the latest Zalo version |
| [minimizeApp](https://docs.zaloplatforms.com/docs/MA/api/zalo/minimizeApp) | Minimizes the Mini App |
| [favoriteApp](https://docs.zaloplatforms.com/docs/MA/api/zalo/favoriteApp) | Adds the app to the favorites list in the Mini Store |
| [addRating](https://docs.zaloplatforms.com/docs/MA/api/zalo/addRating) | Opens the app rating window |

## Advertising

| Name | Description |
| --- | --- |
| [setupAd](https://docs.zaloplatforms.com/docs/MA/api/advertising/setupAd) | Configures the information used to run ads. |
| [loadAd](https://docs.zaloplatforms.com/docs/MA/api/advertising/loadAd) | API used to load an ad |
| [displayAd](https://docs.zaloplatforms.com/docs/MA/api/advertising/displayAd) | API used to display an ad after loading |
| [refreshAd](https://docs.zaloplatforms.com/docs/MA/api/advertising/refreshAd) | API used to clear the ad in the current session |

## Widgets

| Name | Description |
| --- | --- |
| [showOAWidget](https://docs.zaloplatforms.com/docs/MA/api/widgets/showOAWidget) | Displays the OA Follow widget |
| [showFunctionButtonWidget](https://docs.zaloplatforms.com/docs/MA/api/widgets/showFunctionButtonWidget) | Displays the Function Button widget |
