# openShareSheet

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openShareSheet
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openShareSheet } from "zmp-sdk";
```

API cho phép ứng dụng mở giao diện chia sẻ để người dùng chia sẻ thông tin với bạn bè Zalo.

## Ví dụ

### Chia sẻ văn bản

```ts
const data = await openShareSheet({
  type: "text",
  data: {
    text: "My Zalo Mini App - HomePage",
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| text | `string` | Yes | Nội dung văn bản cần chia sẻ |
| description | `string` | No | Mô tả thêm cho nội dung cần chia sẻ |
| autoParseLink | `boolean` | No | Với giá trị `true` url trong text sẽ được hiển thị dưới dạng thumbnail (default: false) |

### Chia sẻ hình ảnh

```ts
const data = await openShareSheet({
  type: "image",
  data: {
    imageUrls: ["http://dev.org.zads.zdn.vn/2a16c7fefbbb12e54baa"],
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| imageUrl | `string` | No | URL của hình ảnh cần chia sẻ |
| imageUrls | `string[]` | No | URL của các hình ảnh cần chia sẻ. Tối đa 10 hình ảnh |

### Chia sẻ liên kết

```ts
const data = await openShareSheet({
  type: "link",
  data: {
    link: "http://news.zing.vn/Trung-uong-quyet-dinh-phuong-an-nhan-su-cap-cao-post632739.html",
    chatOnly: false,
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| link | `string` | Yes | Liên kết cần chia sẻ |
| chatOnly | `boolean` | No | Chỉ chia sẻ qua cửa sổ chat (default: false) |

### Chia sẻ Official Account

```ts
const data = await openShareSheet({
  type: "oa",
  data: {
    id: "765465772305886642",
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id của official account |

### Chia sẻ GIF

```ts
const data = await openShareSheet({
  type: "gif",
  data: {
    imageUrl: "http://dev.org.zads.zdn.vn/2a16c7fefbbb12e54baa",
    gifUrl: "http://dev.org.zads.zdn.vn/fc88fe60c2252b7b7234",
    width: 480,
    height: 270,
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| gifUrl | `string` | Yes | Url ảnh động cần chia sẻ |
| imageUrl | `string` | No | Url hình ảnh đại diện |
| width | `number` | No | Chiều rộng |
| height | `number` | No | Chiều cao |

### Chia sẻ video

```ts
const data = await openShareSheet({
  type: "video",
  data: {
    videoThumb: "http://dev.org.zads.zdn.vn/fc88fe60c2252b7b7234",
    videoUrl: "http://dev.org.zads.zdn.vn/fc88fe60c2252b7b7234",
    width: 480,
    height: 270,
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| videoThumb | `string` | Yes | Url thumbnail cho video |
| videoUrl | `string` | Yes | Url video |
| width | `number` | No | Chiều rộng |
| height | `number` | No | Chiều cao |

### Chia sẻ page hiện tại của Zalo Mini App

```ts
const data = await openShareSheet({
  type: "zmp",
  data: {
    title: "My Zalo Mini App - HomePage",
    description: "Home page",
    thumbnail: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| title | `string` | Yes | Tiêu đề cần chia sẻ. Tối đa 100 ký tự |
| description | `string` | No | Mô tả. Tối đa 400 ký tự |
| thumbnail | `string` | Yes | Url thumbnail cho Zalo Mini App |
| path | `string` | No | Đường dẫn cần chia sẻ |

### Chia sẻ page hiện tại của Zalo Mini App thông qua deep link

```ts
const data = await openShareSheet({
  type: "zmp_deep_link",
  data: {
    title: "My Zalo Mini App - HomePage",
    description: "Home page",
    thumbnail: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
  },
});
console.log(data);
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| title | `string` | Yes | Tiêu đề cần chia sẻ. Tối đa 100 ký tự |
| thumbnail | `string` | Yes | Url thumbnail cho Zalo Mini App |
| description | `string` | No | Mô tả. Tối đa 400 ký tự |
| path | `string` | No | Đường dẫn cần chia sẻ, mặc định sẽ lấy theo đường dẫn hiện tại |

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Tham số

Truyền tham số vào API dưới dạng object chứa các thuộc tính:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"text" \| "image" \| "link" \| "oa" \| "gif" \| "video" \| "zmp" \| "zmp_deep_link"` | Yes | Nhận các giá trị sau: - `text`: Chia sẻ văn bản. - `image`: Chia sẻ hình ảnh. - `link`: Chia sẻ liên kết. - `oa`: Chia sẻ Official Account. - `gif`: Chia sẻ ảnh động. - `video`: Chia sẻ video. - `zmp`: Chia sẻ page hiện tại của Zalo Mini App. - `zmp_deep_link`: Chia sẻ page hiện tại của Zalo Mini App thông qua deep link (hỗ trợ từ API 2.25.7). |
| data | `ShareData` | Yes | Nội dung cần chia sẻ, tùy thuộc vào `type`. |

## Kết quả trả về

API trả về `Promise<OpenShareSheetReturns>` chứa Promise chứa thông tin kết quả chia sẻ.

### OpenShareSheetReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| status | `'0' \| '2' \| '1'` | No | Trạng thái chia sẻ: - `0`: User nhấn hủy/cancel bài viết. - `1`: Đăng bài viết thành công lên nhật ký. - `2`: Đăng bài viết thành công qua cửa sổ chat. |
| shareType | `'0' \| '2' \| '1'` | No | Trạng thái bài chia sẻ: - `0`: Công khai. - `1`: Chỉ mình tôi. - `2`: Chia sẻ cho danh sách bạn. |
| numberOfUser | `number` | No | Số lượng user nhận được bài chia sẻ trong trường hợp `shareType=2`. |
