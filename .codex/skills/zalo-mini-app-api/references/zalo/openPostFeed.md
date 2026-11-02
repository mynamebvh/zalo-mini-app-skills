# openPostFeed

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/openPostFeed
> Last updated: 28/10/2026
> Supported from: SDK 2.5.3

```ts
import { openPostFeed } from "zmp-sdk";
```

API that allows the app to open the share interface so users can share information to their Zalo journal.

## Example

### Share images

```ts
const { status, shareType, numberOfUser } = await openPostFeed({
  type: "image",
  data: {
    imageUrls: ["https://example.com/image.jpg"],
  },
});
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| imageUrl | `string` | No | URL of the image to share |
| imageUrls | `string[]` | No | URLs of the images to share |

### Share a link

```ts
const { status, shareType, numberOfUser } = await openPostFeed({
  type: "link",
  data: {
    link: "http://news.zing.vn/Trung-uong-quyet-dinh-phuong-an-nhan-su-cap-cao-post632739.html",
    title: "Central Committee decides on senior personnel plan",
    thumb: "https://example.com/thumbnail.jpg",
    description: "description",
  },
});
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| link | `string` | Yes | Link to share |
| thumb | `string` | No | Thumbnail |
| description | `string` | No | Description. Maximum 400 characters |
| title | `string` | No | Title of the link. Maximum 100 characters |

### Share a profile

```ts
const { status, shareType, numberOfUser } = await openPostFeed({
  type: "profile",
  data: {
    id: "765465772305886642",
  },
});
```

#### ShareData

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | Id of the OA |

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"image" \| "link" \| "profile"` | Yes | Accepts the following values: - `image`: Share images. - `link`: Share a link. - `profile`: Share an OA profile. |
| data | `ShareData` | Yes | Content to share, depending on `type`. |

## Returns

Returns `Promise<OpenPostFeedReturns>` containing the share result information.

### OpenPostFeedReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| status | `'0' \| '1'` | No | Share status: - `0`: User pressed cancel on the post. - `1`: Post published successfully. |
| shareType | `'0' \| '1' \| '2'` | No | Shared post status: - `0`: Public. - `1`: Only me. - `2`: Shared to a friend list. |
| numberOfUser | `number` | No | Number of users who receive the shared post when `shareType=2`. |