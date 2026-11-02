# scanQRCode

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/qr/scanQRCode
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { scanQRCode } from "zmp-sdk";
```

Cho phép ứng dụng mở tính năng quét QR Code của Zalo App và trả về kết quả sau khi người dùng quét thành công.

## Ví dụ

Lấy nội dung của QR đã quét

```ts
const { content } = await scanQRCode({});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<ScanQRCodeReturns>` chứa object với thuộc tính `content` là nội dung của QR đã quét.
