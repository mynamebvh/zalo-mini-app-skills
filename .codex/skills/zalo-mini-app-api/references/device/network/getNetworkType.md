# getNetworkType

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/network/getNetworkType
> Last updated: 28/10/2026

```ts
import { getNetworkType } from "zmp-sdk";
```

API truy xuất kiểu kết nối mạng hiện tại.

## Ví dụ

Lấy kiểu kết nối mạng hiện tại:

```ts
const { networkType } = await getNetworkType();
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<GetNetworkTypeReturns>` chứa chứa kiểu kết nối mạng hiện tại.

### GetNetworkTypeReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| networkType | `"none" \| "wifi" \| "cellular" \| "unknown"` | No | Kiểu kết nối mạng hiện tại với các giá trị: - `none`: Không có mạng. - `wifi`: Mạng Wi-Fi. - `cellular`: Mạng di động (2g/3g/4g). - `unknown`: Mạng không xác định (Android). |
