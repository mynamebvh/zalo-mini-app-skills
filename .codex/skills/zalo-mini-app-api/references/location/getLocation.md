# getLocation

> Source: https://docs.zaloplatforms.com/docs/MA/api/location/getLocation
> Last updated: 28/10/2026

```ts
import { getLocation } from "zmp-sdk";
```

API to retrieve the user's current location. When the API is called, a permission request notification will be displayed. The Mini App can only obtain location information if the user agrees to grant location sharing permission.

Note, to help Mini App developers use the permission request flow effectively, as well as in accordance with [Zalo Mini App policy section 3.3.4](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp), the Mini App Team has provided some experience design suggestions as described below. Developers need to clearly and visually explain the purpose of the permission request so that users can easily understand and agree to provide information.

![Flow request location](https://docs.zaloplatforms.com/assets/images/do-00707feac8c7ccfeacb3b41f4134ad10.png)

To ensure a comfortable experience for Mini App users, we will reject approval for Mini Apps whose permission request flow is unclear and does not state the purpose of the permission request to users. Refer to some violation cases below:

![Flow request location reject](https://docs.zaloplatforms.com/assets/images/dont-875685f550af13319c676137ac0ed2ee.png)

## Information retrieval flow description

![getLocation](https://docs.zaloplatforms.com/assets/MA/img/api/flow-request-permission.jpeg)

## Example

1. In the Zalo Mini App, call this API to get the location token:

```ts
const { token } = await getLocation();
```

2. Use fetch or axios to send this token to the server. Otherwise, you will get [errors when calling Server-Server APIs from the Mini App](https://mini.zalo.me/community/9107262438710014159/loi-khi-goi-cac-api-server-server-tu-mini-app).
3. The server converts the token into location information and returns it to the Mini App according to the [instructions](#token-to-location).

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

Returns `Promise<GetLocationReturns>` containing the location token.

### GetLocationReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| token | `string` | No | A string used to retrieve location information through the server. For each Token provided, you can retrieve the information once, with an expiration time after 2 minutes. |

## Guide to converting a token into user location information

Use the **token** you just received to retrieve the user's location information from your **Server** through the Zalo Open API; please refer to the sample code below:

```bash
curl --location --request GET <https://graph.zalo.me/v2.0/me/info>
--header access_token: <user_access_token>
--header **code: <your token>**
--header **secret_key: <your zalo app secret key>**
```

Description of the parameters to use:

- **access\_token**: retrieved through the [sdk.getAccessToken](https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getAccessToken) API
- **code**: the value is the token you received when calling the location retrieval API on the Zalo version
- **secret\_key**: The secret key of the Zalo App; go to <https://developers.zalo.me/>, the corresponding App Management section, to retrieve the information

Example returned result:

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