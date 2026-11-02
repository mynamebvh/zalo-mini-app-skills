# openMediaPicker

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker
> Last updated: 08/12/2025
> Supported from: SDK 2.18.11, Android 2.23.2: hỗ trợ các type `zcamera`, `zcamera_photo`, `zcamera_video`, `zcamera_scan`.

```ts
import { openMediaPicker } from "zmp-sdk";
```

Mở cửa sổ chọn media (camera, ảnh, file, video) từ thiết bị.

> **Change**
>
> Với môi trường hỗ trợ [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem), có những thay đổi đáng chú ý sau:
>
> - Không còn bắt buộc upload file lên server. Mặc định nếu không truyền tham số **serverUploadUrl**, SDK sẽ trả về đường dẫn tạm thời (local cache) của media mà không tự động upload lên server. **Lưu ý**: Các file này được lưu tạm thời và sẽ được xóa khi app khởi động lại, nếu cần lưu bền app có thể gọi [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) để chuyển file thành local data
> - Nén ảnh với các chất lượng đầu ra qua tham số **compressLevel**. Nếu không truyền, SDK sẽ mặc định trả về ảnh không nén (**compressLevel**=0). App có thể tối ưu việc lưu trữ ảnh với kích thước nhỏ gọn hơn với mức nén cao dần (1 đến 3) tùy vào nhu cầu sử dụng.
>
> Để kiểm tra LFS có được hỗ trợ hay không, vui lòng sử dụng API [isSupportLFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS).

## Ví dụ

Mở cửa sổ chọn ảnh, nén ảnh với mức nén vừa, nhận kết quả trả về đường dẫn đến file tạm

```ts
const { data } = await openMediaPicker({
  type: "photo",
  compressLevel: 2,
});

console.log(data);
```

Mở cửa sổ chọn video, nhận kết quả trả về đường dẫn đến file tạm

```ts
const { data } = await openMediaPicker({
  type: "video",
});
console.log(data);
```

Chọn nhiều ảnh:

```ts
const { data } = await openMediaPicker({
  type: "photo",
  maxSelectItem: 5,
});
```

Chọn ảnh từ camera Zalo:

```ts
const { data } = await openMediaPicker({
  type: "zcamera_photo",
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| serverUploadUrl | `string` | No | Đường dẫn upload media. Server phải hỗ trợ upload media qua POST và trả về kết quả dạng JSON. Xem ví dụ về server tại [đây](https://miniapp.zaloplatforms.com/documents/api/openMediaPicker/#upload-l%C3%AAn-server). |
| type | `"photo" \| "file" \| "video" \| "zcamera" \| "zcamera_photo" \| "zcamera_video" \| "zcamera_scan"` | Yes | Loại media cần chọn. Các giá trị: |
| maxItemSize | `number` | No | Giới hạn kích thước (byte) tối đa của media được phép chọn. |
| maxSelectItem | `number` | No | Giới hạn số lượng tối đa media được chọn. (default: 1) |
| silentRequest | `boolean` | No | Hiển thị hoặc ẩn dialog xử lý các tác vụ ngầm: (default: false) |
| editView | `Object` | No | Hiển thị view chỉnh sửa ảnh. |
| compressLevel | `number` | No | Mức nén ảnh khi chọn type là `photo` hoặc `zcamera_photo`. Các mức nén: - **0**: Không nén (ảnh gốc) - **1**: Nén thấp - **2**: Nén trung bình - **3**: Nén cao (ảnh có thể bị rỗ) (default: 0) |

## Kết quả trả về

API trả về `Promise<OpenMediaPickerReturns>` chứa kết quả trả về.

### OpenMediaPickerReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| data | `string[] \| string` | No | Mặc định trả về mảng đường dẫn file tạm trên thiết bị.  Nếu truyền **serverUploadUrl** thì data là toàn bộ nội dung trả về của server upload media. |

## Upload lên server

> **Note**
>
> Với các phiên bản SDK và Zalo không hỗ trợ tính năng [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem), cần upload media lên server qua tham số **serverUploadUrl**.

Media sau khi chọn sẽ được tải lên server của bạn dưới dạng dữ liệu `multipart/form-data`, `fieldname=file`.

### Server

Server phải cung cấp một api dùng để upload media với method `POST` và trả về kết quả dạng `JSON`. Kết quả trả về phải chứa trường `error` với các giá trị:

- 0: Tải lên thành công
- Khác 0: Tải lên thất bại

Một ví dụ về kết quả trả về của API dùng để upload media:

- Tải lên thành công:

```json
{
  "error": 0,
  "message": "Success",
  "data": {
    "urls": [...]
  }
}
```

- Tải lên thất bại:

```json
{
  "error": -1,
  "message": "Fail"
}
```

Tạo một server để upload media với 2 api:

- `POST` /upload/media - Dùng để upload media
- `GET` /files/:name - Dùng để lấy media theo `name`

Tham khảo code mẫu dưới đây:

```js
// Call all the required packages
var express = require("express");
var bodyParser = require("body-parser");
var multer = require("multer");
var app = express();
var path = require("path");

var host = "localhost";
var port = 8080;

// Create express app
app.use(bodyParser.urlencoded({ extended: true }));

// Create storage
var storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, "uploads");
  },
  filename: function (req, file, cb) {
    cb(null, file.originalname);
  },
});

var upload = multer({ storage: storage });

// Routes will go here

/**
 * Uploading multiple files with field 'file'
 * @api /upload/media
 * @method POST
 *
 */
app.post("/upload/media", upload.array("file"), (req, res, next) => {
  const files = req.files;
  res.status(200).send({
    data: {
      urls: files.map(
        (item) => `http://${host}:${port}/files/${item.filename}`
      ),
    },
    error: 0,
    message: "Success",
  });
});

/**
 * Getting file with name
 * @api /files/:name
 * @method GET
 *
 */
app.get("/files/:name", (req, res) => {
  const fileName = req.params.name;
  const directoryPath = path.join(__dirname, "uploads/");

  res.sendFile(`${directoryPath}${fileName}`, fileName, (err) => {
    if (err) {
      try {
        res.status(500).send({
          message: "Could not get the file. " + err,
        });
      } catch (e) {}
    }
  });
});

// Server started on port 8080
app.listen(port, () => console.log(`Server started on port ${port}`));
```

### Client

```jsx
import { openMediaPicker } from "zmp-sdk/apis";

openMediaPicker({
  type: "photo",
  serverUploadUrl: "https://<your-domain-api>/upload/media",
  compressLevel: 2, //Tùy chọn nếu cần nén ảnh
  success: (res) => {
    // xử lý khi gọi api thành công
    const { data } = res;
    const result = JSON.parse(data);
    console.log(result);
  },
  fail: (error) => {
    // xử lý khi gọi api thất bại
    console.log(error);
  },
});
```

Hoặc

```jsx
import { openMediaPicker } from "zmp-sdk/apis";

const pickMedia = async () => {
  try {
    const { data } = await openMediaPicker({
      type: "photo",
      serverUploadUrl: "https://<your-domain-api>/upload/media",
      compressLevel: 2, //Tùy chọn nếu cần nén ảnh
    });
    const result = JSON.parse(data);
    console.log(result);
  } catch (error) {
    // xử lý khi gọi api thất bại
    console.log(error);
  }
};
```
