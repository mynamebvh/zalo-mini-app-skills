# refreshAd

> Source: https://docs.zaloplatforms.com/docs/MA/api/advertising/refreshAd
> Last updated: 28/10/2026
> Supported from: SDK 2.37.0

```ts
import { refreshAd } from "zmp-sdk";
```

Clears the ad in the current session.

## Example

Clear the ZMA\_Middle ad:

```ts
refreshAd({ id: "ZMA_Middle" });
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | No | ID of the ad type to clear. |
