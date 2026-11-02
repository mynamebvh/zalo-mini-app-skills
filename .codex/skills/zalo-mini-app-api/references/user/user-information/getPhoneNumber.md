# getPhoneNumber

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getPhoneNumber
> Last updated: 28/10/2026
> Supported from: SDK 2.13.0

```ts
import { getPhoneNumber } from "zmp-sdk";
```

Lấy thông tin số điện thoại của người dùng. Khi gọi API, một thông báo xin cấp quyền sẽ được hiển thị. Mini App chỉ lấy được thông tin số điện thoại nếu người dùng đồng ý cấp quyền chia sẻ số điện thoại.

Lưu ý, để giúp các nhà phát triển Mini App sử dụng flow xin quyền một cách hiệu quả, cũng như phù hợp với [chính sách của Zalo Mini App điều 3.3.4](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp), Mini App Team đã đưa ra một số gợi ý thiết kế trải nghiệm như thông tin bên dưới. Nhà phát triển cần giải thích rõ ràng và trực quan mục đích xin quyền để người dùng dễ dàng hiểu và đồng ý cung cấp thông tin.

### Trường hợp chỉ cần số điện thoại cho một số tính năng nhất định

Chỉ nên yêu cầu người dùng chia sẻ số điện thoại khi người dùng bắt đầu sử dụng các tính năng đó như khi tiến hành đặt hàng, đăng ký tham sự kiện...

![Flow request phone approve](https://docs.zaloplatforms.com/assets/images/infor_permission_phone_21.07-bf0d73376d592c67300fbea0ee4aabf1.png)

### Trường bắt buộc phải cung cấp số điện thoại để sử dụng ứng dụng

Với trường hợp này cần hiển thị UI Onboarding giải thích cụ thể lý do người dùng cần phải cung cấp số điện thoại. Tham khảo hình minh họa:

![Flow request phone approve](https://docs.zaloplatforms.com/assets/images/infor_permission_phone_onboarding-695a9925db0565c7fb76823204561f1b.png)

Nhằm đảm bảo trải nghiệm thoải mái của người dùng Mini App, chúng tôi sẽ từ chối xét duyệt cho những Mini App có luồng xin cấp quyền chưa rõ ràng, không nêu được mục đích xin quyền đến người dùng. Tham khảo một số trường hợp vi phạm như bên dưới:

![Flow request location reject](https://docs.zaloplatforms.com/assets/images/dont-343b8088b6b711469a00eaa60b56cfee.png)

## Mô tả luồng truy xuất thông tin

![getLocation](https://docs.zaloplatforms.com/assets/MA/img/api/flow-request-permission.jpeg)

## Ví dụ

1. Ở Zalo Mini App, gọi API này để lấy token số điện thoại:

```ts
const { token } = await getPhoneNumber();
```

2. Dùng fetch hoặc axios để gửi token này lên server. Nếu không, bạn sẽ bị [lỗi khi gọi các API Server-Server từ Mini App](https://mini.zalo.me/community/9107262438710014159/loi-khi-goi-cac-api-server-server-tu-mini-app).
3. Server chuyển đổi token thành thông tin số điện thoại và trả về cho Mini App theo [hướng dẫn](#token-to-phone).

> Xem hướng dẫn xử lý lỗi và bảng mô tả chi tiết mã lỗi [tại đây](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Kết quả trả về

API trả về `Promise<GetPhoneNumberReturns>` chứa chứa token để truy xuất thông tin số điện thoại.

### GetPhoneNumberReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| token | `string` | No | Là một chuỗi ký tự dùng để truy xuất thông tin số điện thoại thông qua server. Mỗi token được cung cấp chỉ có thể truy xuất thông tin được 1 lần với thời gian hết hạn sau 2 phút. |

## Hướng dẫn chuyển đổi token thành số điện thoại người dùng

Sử dụng **token** vừa nhận được để truy xuất số điện thoại của người dùng từ **Server** của bạn thông qua Zalo Open API, vui lòng tham khảo code mẫu bên dưới:

```bash
curl --location --request GET <https://graph.zalo.me/v2.0/me/info>
--header access_token: <user_access_token>
--header **code: <your token>**
--header **secret_key: <your zalo app secret key>**
```

Mô tả các tham số cần sử dụng:

- **access\_token**: truy xuất thông qua API sdk.getAccessToken({...})
- **code**: giá trị là token bạn nhận được khi gọi API lấy số điện thoại.
- **secret\_key**: Khoá bí mật của Zalo App, truy cập <https://developers.zalo.me/>, phần Quản lý ứng dụng tương ứng để truy xuất thông tin

Ví dụ kết quả trả về:

```json
{
  "data": {
    "number": "849123456789"
  },
  "error": 0,
  "message": "Success"
}
```
