# openSMS

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/contact/openSMS
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openSMS } from "zmp-sdk";
```

API that opens the messaging app with a specific content and phone number.

## Example

Open the messaging app with a specific content and phone number:

```ts
await openSMS({
  content: "text",
  phoneNumber: "+84123456789",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| content | `string` | Yes | Message content. |
| phoneNumber | `string` | Yes | Phone number that receives the message. |