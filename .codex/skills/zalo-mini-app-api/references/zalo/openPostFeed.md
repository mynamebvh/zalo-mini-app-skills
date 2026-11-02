# openPostFeed

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openPostFeed
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openPostFeed } from "zmp-sdk";
```

API cho phép ứng dụng mở giao diện chia sẻ để người dùng chia sẻ thông tin lên nhật ký Zalo.

## Ví dụ

### Chia sẻ hình ảnh

```ts
const { status, shareType, numberOfUser } = await openPostFeed({
  type: "image",
  data: {
    imageUrls: ["https://example.com/image.jpg"],
  },
});
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| imageUrl | `string` | No | URL của hình ảnh cần chia sẻ |
| imageUrls | `string[]` | No | URL của các hình ảnh cần chia sẻ |

### Chia sẻ liên kết

```ts
const { status, shareType, numberOfUser } = await openPostFeed({
  type: "link",
  data: {
    link: "http://news.zing.vn/Trung-uong-quyet-dinh-phuong-an-nhan-su-cap-cao-post632739.html",
    title: "Trung ương quyết định phương án nhân sự cấp cao",
    thumb: "https://example.com/thumbnail.jpg",
    description: "description",
  },
});
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| link | `string` | Yes | Liên kết cần chia sẻ |
| thumb | `string` | No | Thumbnail |
| description | `string` | No | Mô tả. Tối đa 400 ký tự |
| title | `string` | No | Tiêu đề của liên kết. Tối đa 100 ký tự |

### Chia sẻ profile

```ts
const { status, shareType, numberOfUser } = await openPostFeed({
  type: "profile",
  data: {
    id: "765465772305886642",
  },
});
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id của OA |

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"image" \| "link" \| "profile"` | Yes | Nhận các giá trị sau: - `image`: Chia sẻ hình ảnh. - `link`: Chia sẻ liên kết. - `profile`: Chia sẻ profile OA. |
| data | `ShareData` | Yes | Nội dung cần chia sẻ, tùy thuộc vào `type`. |

## Kết quả trả về

API trả về `Promise<OpenPostFeedReturns>` chứa chứa thông tin kết quả chia sẻ.

### OpenPostFeedReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| status | `'0' \| '1'` | No | Trạng thái chia sẻ: - `0`: User nhấn hủy/cancel bài viết. - `1`: Đăng bài viết thành công. |
| shareType | `'0' \| '1' \| '2'` | No | Trạng thái bài chia sẻ: - `0`: Công khai. - `1`: Chỉ mình tôi. - `2`: Chia sẻ cho danh sách bạn. |
| numberOfUser | `number` | No | Số lượng user nhận được bài chia sẻ trong trường hợp `shareType=2`. |
