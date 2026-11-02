# openShareSheet

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openShareSheet
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openShareSheet } from "zmp-sdk";
```

API that allows the app to open the share interface so users can share information with Zalo friends.

## Example

### Share text

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
| text | `string` | Yes | Text content to share |
| description | `string` | No | Additional description for the content to share |
| autoParseLink | `boolean` | No | When `true`, URLs in the text are displayed as thumbnails (default: false) |

### Share images

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
| imageUrl | `string` | No | URL of the image to share |
| imageUrls | `string[]` | No | URLs of the images to share. Maximum 10 images |

### Share a link

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
| link | `string` | Yes | Link to share |
| chatOnly | `boolean` | No | Share only via the chat window (default: false) |

### Share an Official Account

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
| id | `string` | Yes | Id of the official account |

### Share a GIF

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
| gifUrl | `string` | Yes | URL of the animated image to share |
| imageUrl | `string` | No | URL of the cover image |
| width | `number` | No | Width |
| height | `number` | No | Height |

### Share a video

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
| videoThumb | `string` | Yes | Thumbnail URL for the video |
| videoUrl | `string` | Yes | Video URL |
| width | `number` | No | Width |
| height | `number` | No | Height |

### Share the current Zalo Mini App page

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
| title | `string` | Yes | Title to share. Maximum 100 characters |
| description | `string` | No | Description. Maximum 400 characters |
| thumbnail | `string` | Yes | Thumbnail URL for the Zalo Mini App |
| path | `string` | No | Path to share |

### Share the current Zalo Mini App page via deep link

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
| title | `string` | Yes | Title to share. Maximum 100 characters |
| thumbnail | `string` | Yes | Thumbnail URL for the Zalo Mini App |
| description | `string` | No | Description. Maximum 400 characters |
| path | `string` | No | Path to share; defaults to the current path |

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"text" \| "image" \| "link" \| "oa" \| "gif" \| "video" \| "zmp" \| "zmp_deep_link"` | Yes | Accepts the following values: - `text`: Share text. - `image`: Share images. - `link`: Share a link. - `oa`: Share an Official Account. - `gif`: Share an animated image. - `video`: Share a video. - `zmp`: Share the current Zalo Mini App page. - `zmp_deep_link`: Share the current Zalo Mini App page via deep link (supported from API 2.25.7). |
| data | `ShareData` | Yes | Content to share, depending on `type`. |

## Returns

Returns `Promise<OpenShareSheetReturns>`, a Promise containing the share result information.

### OpenShareSheetReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| status | `'0' \| '2' \| '1'` | No | Share status: - `0`: User pressed cancel on the post. - `1`: Post published successfully to the journal. - `2`: Post published successfully via the chat window. |
| shareType | `'0' \| '2' \| '1'` | No | Shared post status: - `0`: Public. - `1`: Only me. - `2`: Shared to a friend list. |
| numberOfUser | `number` | No | Number of users who receive the shared post when `shareType=2`. |