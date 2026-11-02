# chooseImage

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/chooseImage
> Last updated: 28/10/2026
> Supported from: SDK 2.23.4

```ts
import { chooseImage } from "zmp-sdk";
```

API for choosing images from the album or camera.

## Example

Take a photo with the front camera:

```ts
const { filePaths } = await chooseImage({
  sourceType: ["camera"],
  cameraType: "front",
});
```

Take a photo with the back camera:

```ts
const { filePaths } = await chooseImage({
  sourceType: ["camera"],
  cameraType: "back",
});
```

Choose multiple images to write a product review:

```ts
const { filePaths } = await chooseImage({
  sourceType: ["album", "camera"],
  count: 5,
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| sourceType | `("album" \| "camera")[]` | No | Source for choosing images. You can choose from the album/files (`album`), take a new photo with the camera (`camera`), or both. |
| cameraType | `"back" \| "front"` | No | Specifies whether the front or back camera should be opened. |
| count | `number` | No | Maximum number of images that can be selected. |

## Returns

The API returns `Promise<ChooseImageReturns>` containing the paths to the selected images.

### ChooseImageReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| filePaths | `string[]` | No | Paths of the selected files. |
| tempFiles | `TempFile[]` | No | Information about the temp files. |

### TempFile

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| path | `string` | No | Paths of the selected temp files. |
| size | `number` | No | Sizes of the selected temp files. |