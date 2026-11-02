# saveVideoToGallery

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/saveVideoToGallery
> Last updated: 28/10/2026
> Supported from: SDK 2.44.0

```ts
import { saveVideoToGallery } from "zmp-sdk";
```

Lưu video vào thư viện media của thiết bị, kích thước file được quy định như sau:

| Hệ máy | Kích thước tối đa |
| --- | --- |
| Android | không quy định |
| iOS | 100Mb |

## Ví dụ

Thông báo một lần sau khi lưu video xong:

```ts
await saveVideoToGallery({
  videoUrl:
    "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/360/Big_Buck_Bunny_360_10s_1MB.mp4",
});
console.log("Lưu video thành công!");
```

Xử lý lỗi khi lưu video:

```ts
try {
  await saveVideoToGallery({
    videoUrl:
      "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/360/Big_Buck_Bunny_360_10s_1MB.mp4",
  });
} catch (error) {
  console.error(error);
}
```

Báo cáo tiến độ lưu video:

```ts
await saveVideoToGallery({
  videoUrl:
    "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/360/Big_Buck_Bunny_360_10s_1MB.mp4",
  onProgress: (progress) => {
    console.log(`Đã lưu được ${progress}%...`);
  },
});
console.log("Lưu video thành công!");
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| videoUrl | `string` | No | Đường dẫn của video cần lưu. |
| videoBase64Data | `string` | No | Dữ liệu base64 của video cần lưu (tối đa 7.000.000 ký tự). |
| onProgress | `(progress: number) => void` | No | Callback function tiến độ tải file. Với `progress` là số từ 0 đến 100%. |

Nếu truyền đồng thời `videoUrl` và `videoBase64Data`, SDK sẽ ưu tiên `videoBase64Data`.
