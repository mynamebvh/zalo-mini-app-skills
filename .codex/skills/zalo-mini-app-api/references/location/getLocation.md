# getLocation

> Source: https://docs.zaloplatforms.com/docs/MA/api/location/getLocation
> Last updated: 28/10/2026

```ts
import { getLocation } from "zmp-sdk";
```

API truy xuất vị trí hiện tại của người dùng. Khi gọi API, một thông báo xin cấp quyền sẽ được hiển thị. Mini App chỉ lấy được thông tin vị trí nếu người dùng đồng ý cấp quyền chia sẻ vị trí.

Lưu ý, để giúp các nhà phát triển Mini App sử dụng flow xin quyền một cách hiệu quả, cũng như phù hợp với [chính sách của Zalo Mini App điều 3.3.4](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp), Mini App Team đã đưa ra một số gợi ý thiết kế trải nghiệm như thông tin bên dưới. Nhà phát triển cần giải thích rõ ràng và trực quan mục đích xin quyền để người dùng dễ dàng hiểu và đồng ý cung cấp thông tin.

![Flow request location](https://docs.zaloplatforms.com/assets/images/do-00707feac8c7ccfeacb3b41f4134ad10.png)

Nhằm đảm bảo trải nghiệm thoải mái của người dùng Mini App, chúng tôi sẽ từ chối xét duyệt cho những Mini App có luồng xin cấp quyền chưa rõ ràng, không nêu được mục đích xin quyền đến người dùng. Tham khảo một số trường hợp vi phạm như bên dưới:

![Flow request location reject](https://docs.zaloplatforms.com/assets/images/dont-875685f550af13319c676137ac0ed2ee.png)

## Mô tả luồng truy xuất thông tin

![getLocation](https://docs.zaloplatforms.com/assets/MA/img/api/flow-request-permission.jpeg)

## Ví dụ

1. Ở Zalo Mini App, gọi API này để lấy token vị trí:

```ts
const { token } = await getLocation();
```

2. Dùng fetch hoặc axios để gửi token này lên server. Nếu không, bạn sẽ bị [lỗi khi gọi các API Server-Server từ Mini App](https://mini.zalo.me/community/9107262438710014159/loi-khi-goi-cac-api-server-server-tu-mini-app).
3. Server chuyển đổi token thành thông tin vị trí và trả về cho Mini App theo [hướng dẫn](#token-to-location).

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<GetLocationReturns>` chứa chứa token vị trí.

### GetLocationReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| token | `string` | No | Là một chuỗi ký tự dùng để truy xuất thông tin vị trí thông qua server. Mỗi Token được cung cấp, bạn sẽ có thể truy xuất thông tin được 1 lần với thời gian hết hạn sau 2 phút. |

## Hướng dẫn chuyển đổi token thành thông tin vị trí người dùng

Sử dụng **token** vừa nhận được để truy xuất thông tin vị trí người dùng từ **Server** của bạn thông qua Zalo Open API, vui lòng tham khảo code mẫu bên dưới:

```bash
curl --location --request GET <https://graph.zalo.me/v2.0/me/info>
--header access_token: <user_access_token>
--header **code: <your token>**
--header **secret_key: <your zalo app secret key>**
```

Mô tả các tham số cần sử dụng:

- **access\_token**: truy xuất thông qua API [sdk.getAccessToken](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getAccessToken)
- **code**: giá trị là token bạn nhận được khi gọi API lấy vị trí trên phiên bản Zalo
- **secret\_key**: Khoá bí mật của Zalo App, truy cập <https://developers.zalo.me/>, phần Quản lý ứng dụng tương ứng để truy xuất thông tin

Ví dụ kết quả trả về:

```json
{
  "data": {
    "provider": "gps",
    "latitude": "10.758341",
    "longitude": "106.745863",
    "timestamp": "1666249171003"
  },
  "error": 0,
  "message": "Success"
}
```
