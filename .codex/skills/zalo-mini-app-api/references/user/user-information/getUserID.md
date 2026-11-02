# getUserID

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getUserID
> Last updated: 28/10/2026
> Supported from: SDK 2.32.2

```ts
import { getUserID } from "zmp-sdk";
```

API cho phép truy xuất ID người dùng. Với ID là chuỗi định danh người dùng theo Zalo App. Chuỗi này là duy nhất cho mỗi người dùng trên mỗi ID Zalo App. Các Mini App cùng chung một ID Zalo App sẽ có thể dùng chuỗi này để định danh người dùng. (API này sẽ không cần yêu cầu người dùng xác nhận).

## Ví dụ

Truy xuất ID người dùng:

```ts
const userID = await getUserID({});
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<string>` chứa ID người dùng.
