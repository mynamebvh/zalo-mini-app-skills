# downloadFile

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile
> Last updated: 28/10/2026
> Supported from: SDK 2.44.0

```ts
import { downloadFile } from "zmp-sdk";
```

API hỗ trợ tải file về thiết bị, kích thước file được quy định như sau:

| Hệ máy | Kích thước tối đa |
| --- | --- |
| Android | không quy định |
| iOS | 100Mb |

Hỗ trợ giao thức tải file `https://` với các định dạng được liệt kê bên dưới:

## Định dạng file được hỗ trợ

| Định dạng | Đuôi file |
| --- | --- |
| Văn bản | pdf, doc, docx, odt, xls, xlsx, ppt, pptx, txt, rtf, csv |
| Hình ảnh | jpg, jpeg, png, gif, bmp |
| Video | mp4, avi, mkv, mov, wmv |

## Ví dụ

Thông báo một lần sau khi tải file xong:

```ts
await downloadFile({
  url: "https://stc-zmp.zadn.vn/mini-app/landingpage-banner-new.png",
});
console.log("Tải file thành công!");
```

Báo cáo tiến độ tải file:

```ts
await downloadFile({
  url: "https://stc-zmp.zadn.vn/mini-app/landingpage-banner-new.png",
  onProgress: (progress) => {
    console.log(`Đã tải được ${progress}%...`);
  },
});
console.log("Tải file thành công!");
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| url | `string` | No | Đường dẫn của file muốn download. |
| fileBase64Data | `string` | No | Dữ liệu base64 của file muốn lưu (tối đa 7.000.000 ký tự). |
| onProgress | `(progress: number) => void` | No | Callback function tiến độ tải file. Với `progress` là số từ 0 đến 100%. |

Nếu truyền đồng thời `url` và `fileBase64Data`, SDK sẽ ưu tiên `fileBase64Data`.
