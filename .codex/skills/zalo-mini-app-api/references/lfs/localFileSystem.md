# Tổng quan về local file

> Source: https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem
> Last updated: 22/12/2025
> Supported from: SDK 2.51.0, Android 25.11.02, IOS 25.12.02

> **Info**
>
> Để kiểm tra LFS có được hỗ trợ hay không, vui lòng sử dụng API [isSupportLFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS).

Trong quá trình sử dụng các API (vd: [openMediaPicker](https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker), [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile)) sẽ sinh ra các local file (file cục bộ). Dựa vào mục đích sử dụng, local file được chia làm 2 loại sau:

•
Local cache file:
Format:

- Android: `https://miniprogram/MPStorage/LFS/caches/[file name+extension]`
- iOS: `miniappres://miniprogram/MPStorage/LFS/caches/[file name+extension]`

File sinh ra khi gọi API như [openMediaPicker](https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker). Các file này được lưu tạm thời và sẽ được xóa khi app khởi động lại. Nếu app có nhu cầu lưu lại file để sử dụng cho lần sau thì dùng api [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) để chuyển thành local data file.

•
Local data file:
Format:

- Android: `https://miniprogram/MPStorage/LFS/data/[file name+extension]`
- iOS: `miniappres://miniprogram/MPStorage/LFS/data/[file name+extension]`

File sinh ra khi gọi API [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) để tải file từ internet hoặc file tạm (local cache) về vùng nhớ cục bộ (local data). Dung lượng lưu trữ tối đa cho local data files là 10MB cho mỗi ứng dụng. Quá giới hạn này sẽ báo lỗi -300. App chủ động việc xóa bớt file không cần thiết để giải phóng dung lượng lưu trữ bằng API [removeSavedFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/removeSavedFile).
