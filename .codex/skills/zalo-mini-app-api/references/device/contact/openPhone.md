# openPhone

> Source: https://docs.zaloplatforms.com/docs/MA/api/device/contact/openPhone
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openPhone } from "zmp-sdk";
```

API that allows opening the call screen with a specific phone number.

## Example

Open the call screen with a specific phone number:

```ts
await openPhone({
  phoneNumber: "0123456789",
});
```

The phone number can start with an international code:

```ts
await openPhone({
  phoneNumber: "+84123456789",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| phoneNumber | `string` | Yes | The phone number to call. |