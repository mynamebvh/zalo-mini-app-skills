# openMiniApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/routing/openMiniApp
> Last updated: 28/10/2026
> Supported from: SDK 2.7.0

```ts
import { openMiniApp } from "zmp-sdk";
```

API used to open another Zalo Mini App. It can open a specific path inside that Mini App, or attach additional parameters.

## Example

Open the "ZaUI Coffee" Mini App:

```ts
openMiniApp({
  appId: "194839900003483517",
});
```

Open the "Profile" tab inside "ZaUI Coffee":

```ts
openMiniApp({
  appId: "194839900003483517",
  path: "/profile",
});
```

Open "ZaUI Coffee" with `utm_campaign` tracking:

```ts
openMiniApp({
  appId: "194839900003483517",
  params: {
    utm_campaign: "spring_promo",
  },
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| appId | `string` | Yes | ID of the Zalo Mini App to open. |
| path | `string` | No | Path to a specific page inside the Zalo Mini App to open. |
| params | `Record<string, string>` | No | Object containing additional parameters to attach to the path. |