# saveVideoToGallery

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/saveVideoToGallery
> Last updated: 28/10/2026
> Supported from: SDK 2.44.0

```ts
import { saveVideoToGallery } from "zmp-sdk";
```

Saves a video to the device's media library; the file size limits are as follows:

| OS | Maximum size |
| --- | --- |
| Android | no limit |
| iOS | 100Mb |

## Example

Notify once after the video has been saved:

```ts
await saveVideoToGallery({
  videoUrl:
    "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/360/Big_Buck_Bunny_360_10s_1MB.mp4",
});
console.log("Video saved successfully!");
```

Handle errors when saving the video:

```ts
try {
  await saveVideoToGallery({
    videoUrl:
      "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/360/Big_Buck_Bunny_360_10s_1MB.mp4",
  });
} catch (error) {
  console.error(error);
}
```

Report saving progress:

```ts
await saveVideoToGallery({
  videoUrl:
    "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/360/Big_Buck_Bunny_360_10s_1MB.mp4",
  onProgress: (progress) => {
    console.log(`Saved ${progress}%...`);
  },
});
console.log("Video saved successfully!");
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| videoUrl | `string` | No | Path of the video to save. |
| videoBase64Data | `string` | No | Base64 data of the video to save (maximum 7,000,000 characters). |
| onProgress | `(progress: number) => void` | No | Callback function for file download progress. `progress` is a number from 0 to 100%. |

If both `videoUrl` and `videoBase64Data` are passed, the SDK prioritizes `videoBase64Data`.