# Local file overview

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

> **Info**
>
> To check whether LFS is supported, please use the [isSupportLFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS) API.

During the use of APIs (e.g. [openMediaPicker](https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker), [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile)), local files are generated. Based on the purpose of use, local files are divided into the following 2 types:

•
Local cache file:
Format:

- Android: `https://miniprogram/MPStorage/LFS/caches/[file name+extension]`
- iOS: `miniappres://miniprogram/MPStorage/LFS/caches/[file name+extension]`

Files generated when calling APIs such as [openMediaPicker](https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker). These files are stored temporarily and will be deleted when the app restarts. If the app needs to keep a file for later use, use the [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) API to convert it into a local data file.

•
Local data file:
Format:

- Android: `https://miniprogram/MPStorage/LFS/data/[file name+extension]`
- iOS: `miniappres://miniprogram/MPStorage/LFS/data/[file name+extension]`

Files generated when calling the [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) API to download files from the internet or temporary files (local cache) to local storage (local data). The maximum storage capacity for local data files is 10MB per app. Exceeding this limit will report error -300. The app proactively removes unnecessary files to free up storage by using the [removeSavedFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile) API.