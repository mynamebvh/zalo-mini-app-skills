# getPhoneNumber

> Source: https://docs.zaloplatforms.com/docs/MA/api/user/user-information/getPhoneNumber
> Last updated: 28/10/2026
> Supported from: SDK 2.13.0

```ts
import { getPhoneNumber } from "zmp-sdk";
```

Get the user's phone number information. When the API is called, a permission request notification will be displayed. The Mini App can only obtain the phone number information if the user agrees to grant permission to share the phone number.

Note that to help Mini App developers use the permission request flow effectively, as well as to comply with [Zalo Mini App policy article 3.3.4](https://mini.zalo.me/documents/zalo-mini-app-developer-program-agreement/#33-api-quy%E1%BB%81n-truy-c%E1%BA%ADp), the Mini App Team has provided some experience design suggestions as below. Developers need to clearly and visually explain the purpose of the permission request so that users can easily understand and agree to provide the information.

### Case where the phone number is only needed for certain features

You should only ask the user to share their phone number when the user starts using those features, such as when placing an order, registering for an event...

![Flow request phone approve](https://docs.zaloplatforms.com/assets/images/infor_permission_phone_21.07-bf0d73376d592c67300fbea0ee4aabf1.png)

### Case where providing a phone number is required to use the app

In this case, you need to display an Onboarding UI that specifically explains why the user needs to provide a phone number. Refer to the illustration:

![Flow request phone approve](https://docs.zaloplatforms.com/assets/images/infor_permission_phone_onboarding-695a9925db0565c7fb76823204561f1b.png)

To ensure a comfortable experience for Mini App users, we will refuse to approve Mini Apps whose permission request flow is unclear and does not state the purpose of the permission request to users. Refer to some violation cases below:

![Flow request location reject](https://docs.zaloplatforms.com/assets/images/dont-343b8088b6b711469a00eaa60b56cfee.png)

## Information retrieval flow description

![getLocation](https://docs.zaloplatforms.com/assets/MA/img/api/flow-request-permission.jpeg)

## Example

1. In the Zalo Mini App, call this API to get the phone number token:

```ts
const { token } = await getPhoneNumber();
```

2. Use fetch or axios to send this token to the server. Otherwise, you will get [an error when calling Server-Server APIs from the Mini App](https://mini.zalo.me/community/9107262438710014159/loi-khi-goi-cac-api-server-server-tu-mini-app).
3. The server converts the token into phone number information and returns it to the Mini App according to the [guide](#token-to-phone).

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Returns

The API returns `Promise<GetPhoneNumberReturns>` containing the token used to retrieve the phone number information.

### GetPhoneNumberReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| token | `string` | No | A string used to retrieve the phone number information through the server. Each token provided can only retrieve the information once and expires after 2 minutes. |

## Guide to converting a token into the user's phone number

Use the **token** just received to retrieve the user's phone number from your **Server** through the Zalo Open API, please refer to the sample code below:

```bash
curl --location --request GET <https://graph.zalo.me/v2.0/me/info>
--header access_token: <user_access_token>
--header **code: <your token>**
--header **secret_key: <your zalo app secret key>**
```

Description of the parameters to use:

- **access\_token**: retrieved through the API sdk.getAccessToken({...})
- **code**: the value is the token you received when calling the phone number retrieval API.
- **secret\_key**: The secret key of the Zalo App, access <https://developers.zalo.me/>, in the corresponding App Management section to retrieve the information

Example of the returned result:

```json
{
  "data": {
    "number": "849123456789"
  },
  "error": 0,
  "message": "Success"
}
```