# openProfilePicker

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openProfilePicker
> Last updated: 28/10/2026
> Supported from: SDK 2.16.1

```ts
import { openProfilePicker } from "zmp-sdk";
```

API mở cửa sổ chọn bạn bè trong Zalo, API sẽ trả về danh sách những người được chọn.

![openProfilePicker](https://docs.zaloplatforms.com/assets/images/profilePicker-27e8f2a55289e5d654d5ed556c4a1119.png)

## Ví dụ

Chọn tối đa 2 bạn bè trong danh sách bạn bè của người dùng:

```ts
const { users } = await openProfilePicker({
  maxProfile: 2,
});
console.log(users);
```

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| maxProfile | `number` | No | Số lượng bạn bè tối đa được chọn. Giới hạn trong khoảng 1 đến 10. (default: 1) |

## Kết quả trả về

API trả về `Promise<OpenProfilePickerReturns>` chứa chứa danh sách những bạn bè được chọn.

### OpenProfilePickerReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| users | `PickedProfile[]` | No | Danh sách những bạn bè được chọn. |

### PickedProfile

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | No | Mã người dùng. Chuỗi này là duy nhất cho mỗi người dùng trên mỗi ứng dụng Zalo App. Các Zalo Mini App cùng chung một Zalo App sẽ dùng được mã người dùng của nhau. |
| profile | `ProfileInfo` | No | Thông tin của người dùng. |
| code | `number` | No | Mã lỗi: - 0: Lấy thông tin của người dùng thành công. - -1: Lấy thông tin người dùng thất bại. |
| message | `string` | No | Thông báo lỗi. |

### ProfileInfo

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| name | `string` | No | Tên hiển thị của người dùng. |
| avatar | `string` | No | Ảnh đại diện người dùng. |
