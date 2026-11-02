# getContextAsync

> Source: https://docs.zaloplatforms.com/docs/MA/api/basics/getContextAsync
> Last updated: 28/10/2026
> Supported from: SDK 2.22.0, Android 22.06.02

```ts
import { getContextAsync } from "zmp-sdk";
```

API trả về thông tin ngữ cảnh của người dùng hoặc nhóm khi Mini App được mở từ Menu mở rộng trong cửa sổ chat Zalo.
Nếu ngữ cảnh không hợp lệ hoặc phiên bản Zalo không hỗ trợ, giá trị trả về sẽ rỗng.

## Ví dụ

Kiểm tra ngữ cảnh hợp lệ và trả về thông tin ngữ cảnh:

```ts
const contextInfo = await getContextAsync();
if (contextInfo) {
  // Ngữ cảnh hợp lệ
  const { id, type } = contextInfo;
}
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<ContextInfo>` chứa ngữ cảnh hiện tại.

### ContextInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `'USER_CHAT' \| 'GROUP_CHAT' \| ''` | No | Ngữ cảnh hiện tại là người dùng hoặc nhóm chat. |
| id | `string` | No | ID của người dùng hoặc nhóm chat tương ứng. |
