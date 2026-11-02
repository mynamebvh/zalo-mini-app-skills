# chooseImage

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/chooseImage
> Last updated: 28/10/2026
> Supported from: SDK 2.23.4

```ts
import { chooseImage } from "zmp-sdk";
```

API chọn hình ảnh từ album hoặc camera.

## Ví dụ

Chụp hình ảnh từ camera trước:

```ts
const { filePaths } = await chooseImage({
  sourceType: ["camera"],
  cameraType: "front",
});
```

Chụp hình ảnh từ camera sau:

```ts
const { filePaths } = await chooseImage({
  sourceType: ["camera"],
  cameraType: "back",
});
```

Chọn nhiều hình ảnh để viết đánh giá sản phẩm:

```ts
const { filePaths } = await chooseImage({
  sourceType: ["album", "camera"],
  count: 5,
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| sourceType | `("album" \| "camera")[]` | No | Nguồn chọn hình ảnh. Có thể chọn từ album/tệp (`album`), chụp ảnh mới từ camera (`camera`), hoặc cả hai. |
| cameraType | `"back" \| "front"` | No | Xác định camera cần mở là camera trước hay sau. |
| count | `number` | No | Số lượng hình ảnh tối đa có thể chọn. |

## Kết quả trả về

API trả về `Promise<ChooseImageReturns>` chứa chứa đường dẫn tới hình ảnh đã chọn.

### ChooseImageReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| filePaths | `string[]` | No | Đường dẫn các file đã chọn. |
| tempFiles | `TempFile[]` | No | Thông tin các temp files. |

### TempFile

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| path | `string` | No | Đường dẫn các temp file đã chọn. |
| size | `number` | No | Kích thước các temp file đã chọn. |
