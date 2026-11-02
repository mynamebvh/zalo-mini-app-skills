# onNetworkStatusChange

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/network/onNetworkStatusChange
> Last updated: 28/10/2026

```ts
import { onNetworkStatusChange } from "zmp-sdk";
```

Callback để lắng nghe sự kiện thay đổi mạng.

## Ví dụ

Lắng nghe sự kiện thay đổi mạng:

```ts
onNetworkStatusChange(function (data) {
  const { isConnected, networkType } = data;
  console.log(`Kết nối mạng: ${isConnected}, Loại mạng: ${networkType}`);
});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền trực tiếp một hàm callback vào API:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| callback | `(data: NetworkStatusChangeData) => void` | Yes | Callback function được gọi khi mạng thay đổi. |

### NetworkStatusChangeData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| isConnected | `boolean` | No | Trạng thái kết nối mạng. |
| networkType | `"none" \| "wifi" \| "cellular" \| "unknown"` | No | Kiểu kết nối mạng hiện tại với các giá trị: - `none`: Không có mạng. - `wifi`: Mạng Wi-Fi. - `cellular`: Mạng di động (2g/3g/4g). - `unknown`: Mạng không xác định (Android). |
