# downloadFile

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/downloadFile
> Last updated: 28/10/2026
> Supported from: SDK 2.44.0

```ts
import { downloadFile } from "zmp-sdk";
```

API that supports downloading files to the device; the file size limits are as follows:

| OS | Maximum size |
| --- | --- |
| Android | no limit |
| iOS | 100Mb |

Supports the `https://` file download protocol with the formats listed below:

## Supported file formats

| Format | File extensions |
| --- | --- |
| Text | pdf, doc, docx, odt, xls, xlsx, ppt, pptx, txt, rtf, csv |
| Images | jpg, jpeg, png, gif, bmp |
| Video | mp4, avi, mkv, mov, wmv |

## Example

Notify once after the file has been downloaded:

```ts
await downloadFile({
  url: "https://stc-zmp.zadn.vn/mini-app/landingpage-banner-new.png",
});
console.log("File downloaded successfully!");
```

Report download progress:

```ts
await downloadFile({
  url: "https://stc-zmp.zadn.vn/mini-app/landingpage-banner-new.png",
  onProgress: (progress) => {
    console.log(`Downloaded ${progress}%...`);
  },
});
console.log("File downloaded successfully!");
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| url | `string` | No | Path of the file to download. |
| fileBase64Data | `string` | No | Base64 data of the file to save (maximum 7,000,000 characters). |
| onProgress | `(progress: number) => void` | No | Callback function for file download progress. `progress` is a number from 0 to 100%. |

If both `url` and `fileBase64Data` are passed, the SDK prioritizes `fileBase64Data`.