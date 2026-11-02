# saveImageToGallery

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/saveImageToGallery
> Last updated: 28/10/2026
> Supported from: SDK 2.16.0

```ts
import { saveImageToGallery } from "zmp-sdk";
```

Saves an image to the device's media library.

## Example

Notify once after the image has been saved:

```ts
await saveImageToGallery({
  imageUrl: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
});
console.log("Image saved successfully!");
```

Handle errors when saving the image:

```ts
try {
  await saveImageToGallery({
    imageUrl: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
  });
} catch (error) {
  console.error(error);
}
```

Report saving progress:

```ts
await saveImageToGallery({
  imageUrl: "https://sample-videos.com/img/Sample-jpg-image-50kb.jpg",
  onProgress: (progress) => {
    console.log(`Saved ${progress}%...`);
  },
});
console.log("Image saved successfully!");
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| imageBase64Data | `string` | No | Base64 value of the image to save. |
| imageUrl | `string` | No | Path of the image to save. |
| onProgress | `(progress: number) => void` | No | Callback function for file download progress. `progress` is a number from 0 to 100%. |