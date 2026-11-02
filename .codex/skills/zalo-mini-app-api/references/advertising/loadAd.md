# loadAd

> Source: https://docs.zaloplatforms.com/docs/MA/api/advertising/loadAd
> Last updated: 28/10/2026
> Supported from: SDK 2.37.0

```ts
import { loadAd } from "zmp-sdk";
```

Loads ads. The following ad types are available:

| ID | Size |
| --- | --- |
| `ZMA_Masthead` | 480x270 |
| `ZMA_Middle` | 300x250 |
| `ZMA_Fullscreen` | Full screen |
| `ZMA_Reward` | Full screen |
| `ZMA_Bottom` | Custom |

By default, an ad is displayed after it finishes loading. The ad is rendered at the position of the element with the matching ID. For example:

```html
<div id="ZMA_Masthead">
```

## Example

Load a ZMA\_Middle ad:

```ts
import React, { useEffect } from "react";
import { loadAd } from "zmp-sdk/apis";

function HomePage() {
  useEffect(() => {
    loadAd({ ids: ["ZMA_Middle"] });
  }, []);

  return (
    <>
      ...
      <div id="ZMA_Middle">
    </>
  );
}

export default HomePage;
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| ids | `string \| string[]` | Yes | ID of the ad type to load on the page. |
| config | `AdConfig` | No | Additional configuration. |

### AdConfig

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| zoneId | `string` | Yes | Ad ID provided by Adtima |
| type | `string` | No | Special ad format. Supported formats: 'masthead', 'reward', 'fullscreen' |
| size | `[number, number]` | Yes | Ad size [width, height] |
| attrs | `Object` | No | Additional ad configuration. Contact Adtima to configure it for the ad placement. |
| singleRequest | `boolean` | No | Ad placements with `true` are merged into a single ad request to avoid duplicates (default: false) |
| plugins | `string[]` | No | List of supported plugins to optimize ad display:  - swiper: optimizes ads displayed in a slider using the swiper library |
| display | `boolean` | No | Accepts the following values:  - true: display the ad after loading - false: do not display the ad after loading  (default: true) |
| onLoad | `function` | No | Returns whether an ad is available: true/false |
| onShow | `function` | No | Returns whether the ad was displayed successfully: true/false |
| onClose | `function` | No | Called after `ZMA_Reward` closes and returns the ad's reward token. See [Verify reward token](#verify-reward-token) |
| rewardConfig | `RewardConfig` | No | Display configuration for Reward ads |

### RewardConfig

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| displayType | `string` | No | Display type. Two values: "inline" or "popup" (default: "popup") |
| screenMode | `string` | No | Landscape or portrait display; only applies when `displayType: "popup"`. Two values: "portrait" or "landscape" (default: "portrait") |

## Verify reward token

This API verifies the token returned in `onClose` when a `ZMA_Reward` ad is opened.

### Request

- URL: `https://h5.zalo.me/openapi/ads/verify-token`
- Method: GET
- Parameters

  | Name | Type | Required | Description |
  | --- | --- | --- | --- |
  | token | string | yes | Reward token |
  | appId | string | yes | Mini App ID |

### Response

- Status: `200 OK`
- Body: JSON

  ```json
{
  "msg": "Success",
  "err": 0,
  "data": {
    "result": true
  }
}
```

  - Field "data":

    | Name | Type | Description |
    | --- | --- | --- |
    | result | boolean | Verification result |
