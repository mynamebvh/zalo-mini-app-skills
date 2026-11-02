# saveImageToGallery

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/saveImageToGallery
> Last updated: 28/10/2026
> Supported from: SDK 2.16.0

```ts
import { saveImageToGallery } from "zmp-sdk";
```

Lưu ảnh vào thư viện media của thiết bị.

## Ví dụ

Thông báo một lần sau khi lưu ảnh xong:

```ts
await saveImageToGallery({
  imageUrl: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
});
console.log("Lưu ảnh thành công!");
```

Xử lý lỗi khi lưu ảnh:

```ts
try {
  await saveImageToGallery({
    imageUrl: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
  });
} catch (error) {
  console.error(error);
}
```

Báo cáo tiến độ lưu ảnh:

```ts
await saveImageToGallery({
  imageUrl: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
  onProgress: (progress) => {
    console.log(`Đã lưu được ${progress}%...`);
  },
});
console.log("Lưu ảnh thành công!");
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| imageBase64Data | `string` | No | Giá trị base64 của ảnh cần lưu. |
| imageUrl | `string` | No | Đường dẫn của ảnh cần lưu. |
| onProgress | `(progress: number) => void` | No | Callback function tiến độ tải file. Với `progress` là số từ 0 đến 100%. |
