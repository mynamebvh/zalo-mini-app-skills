# openDocument

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/openDocument
> Last updated: 22/12/2025
> Supported from: SDK 2.48.0, Android 25.09.01 (842), IOS 25.06.02 (666)

```ts
import { openDocument } from "zmp-sdk";
```

API cho phép ứng dụng xem trực tiếp tài liệu (PDF) từ URL hoặc local file [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem).

## Ví dụ

Mở tài liệu PDF từ URL:

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf"
});
```

Mở tài liệu PDF từ URL với tiêu đề tùy chỉnh:

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf",
  title: "Tài liệu mẫu"
});
```

Mở tài liệu PDF từ URL với tiêu đề tùy chỉnh và mở tính năng tải xuống:

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf",
  title: "Tài liệu mẫu",
  download: true
});
```

Mở tài liệu PDF từ URL với tiêu đề tùy chỉnh và mở tính năng chỉnh sửa (chỉ hỗ trợ trên ios):

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf",
  title: "Tài liệu mẫu",
  edit: true
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| url | `string` | Yes | URL của tài liệu cần mở. Hiện chỉ hỗ trợ định dạng tài liệu PDF. |
| title | `string` | No | Tiêu đề của tài liệu trên header bar. Mặc định lấy tên từ URL. |
| share | `boolean` | No | Yêu cầu bật tính năng chia sẻ tài liệu. SDK chỉ chuyển tiếp giá trị này trên Android khi điều kiện hỗ trợ được đáp ứng. (default: false) |
| download | `boolean` | No | Bật tính năng tải tài liệu. Mặc định là false. (default: false) |
| edit | `boolean` | No | Bật tính năng chỉnh sửa tài liệu (chỉ hỗ trợ trên ios). Mặc định là false. (default: false) |
