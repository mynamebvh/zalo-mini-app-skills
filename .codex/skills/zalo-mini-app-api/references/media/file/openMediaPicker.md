# openMediaPicker

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/openMediaPicker
> Last updated: 08/12/2025
> Supported from: SDK 2.18.11, Android 2.23.2: supports the types `zcamera`, `zcamera_photo`, `zcamera_video`, `zcamera_scan`.

```ts
import { openMediaPicker } from "zmp-sdk";
```

Opens a media picker (camera, photos, files, videos) from the device.

> **Change**
>
> For environments that support [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem), there are the following notable changes:
>
> - Uploading files to the server is no longer required. By default, if the **serverUploadUrl** parameter is not passed, the SDK returns the temporary path (local cache) of the media without automatically uploading it to the server. **Note**: These files are stored temporarily and will be deleted when the app restarts; if you need persistent storage, the app can call [saveFile](https://docs.zaloplatforms.com/docs/MA/api/lfs/saveFile) to convert the file into local data
> - Compress images with various output qualities via the **compressLevel** parameter. If not passed, the SDK defaults to returning uncompressed images (**compressLevel**=0). The app can optimize image storage with a more compact size using progressively higher compression levels (1 to 3) depending on its needs.
>
> To check whether LFS is supported, please use the [isSupportLFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/isSupportLFS) API.

## Example

Open the image picker, compress the image with medium compression, and receive the path to the temporary file

```ts
const { data } = await openMediaPicker({
  type: "photo",
  compressLevel: 2,
});

console.log(data);
```

Open the video picker and receive the path to the temporary file

```ts
const { data } = await openMediaPicker({
  type: "video",
});
console.log(data);
```

Select multiple photos:

```ts
const { data } = await openMediaPicker({
  type: "photo",
  maxSelectItem: 5,
});
```

Select a photo from the Zalo camera:

```ts
const { data } = await openMediaPicker({
  type: "zcamera_photo",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| serverUploadUrl | `string` | No | Media upload path. The server must support uploading media via POST and return the result as JSON. See an example server [here](https://miniapp.zaloplatforms.com/documents/api/openMediaPicker/#upload-l%C3%AAn-server). |
| type | `"photo" \| "file" \| "video" \| "zcamera" \| "zcamera_photo" \| "zcamera_video" \| "zcamera_scan"` | Yes | Type of media to select. Values: |
| maxItemSize | `number` | No | Maximum size (in bytes) of the media allowed to be selected. |
| maxSelectItem | `number` | No | Maximum number of media items that can be selected. (default: 1) |
| silentRequest | `boolean` | No | Show or hide the dialog for handling background tasks: (default: false) |
| editView | `Object` | No | Show the image editing view. |
| compressLevel | `number` | No | Image compression level when the type is `photo` or `zcamera_photo`. Compression levels: - **0**: No compression (original image) - **1**: Low compression - **2**: Medium compression - **3**: High compression (the image may become blurry) (default: 0) |

## Returns

The API returns `Promise<OpenMediaPickerReturns>` containing the result.

### OpenMediaPickerReturns

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| data | `string[] \| string` | No | By default, returns an array of temporary file paths on the device.  If **serverUploadUrl** is passed, data is the entire content returned by the media upload server. |

## Upload to the server

> **Note**
>
> With SDK and Zalo versions that do not support the [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem) feature, media must be uploaded to the server via the **serverUploadUrl** parameter.

After selection, the media is uploaded to your server as `multipart/form-data` data with `fieldname=file`.

### Server

The server must provide an api for uploading media with the `POST` method and return the result as `JSON`. The returned result must contain an `error` field with the following values:

- 0: Upload succeeded
- Non-zero: Upload failed

An example of the result returned by the media upload API:

- Upload succeeded:

```json
{
  "error": 0,
  "message": "Success",
  "data": {
    "urls": [...]
  }
}
```

- Upload failed:

```json
{
  "error": -1,
  "message": "Fail"
}
```

Create a server to upload media with 2 apis:

- `POST` /upload/media - Used to upload media
- `GET` /files/:name - Used to get media by `name`

Refer to the sample code below:

```js
// Call all the required packages
var express = require("express");
var bodyParser = require("body-parser");
var multer = require("multer");
var app = express();
var path = require("path");

var host = "localhost";
var port = 8080;

// Create express app
app.use(bodyParser.urlencoded({ extended: true }));

// Create storage
var storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, "uploads");
  },
  filename: function (req, file, cb) {
    cb(null, file.originalname);
  },
});

var upload = multer({ storage: storage });

// Routes will go here

/**
 * Uploading multiple files with field 'file'
 * @api /upload/media
 * @method POST
 *
 */
app.post("/upload/media", upload.array("file"), (req, res, next) => {
  const files = req.files;
  res.status(200).send({
    data: {
      urls: files.map(
        (item) => `http://${host}:${port}/files/${item.filename}`
      ),
    },
    error: 0,
    message: "Success",
  });
});

/**
 * Getting file with name
 * @api /files/:name
 * @method GET
 *
 */
app.get("/files/:name", (req, res) => {
  const fileName = req.params.name;
  const directoryPath = path.join(__dirname, "uploads/");

  res.sendFile(`${directoryPath}${fileName}`, fileName, (err) => {
    if (err) {
      try {
        res.status(500).send({
          message: "Could not get the file. " + err,
        });
      } catch (e) {}
    }
  });
});

// Server started on port 8080
app.listen(port, () => console.log(`Server started on port ${port}`));
```

### Client

```jsx
import { openMediaPicker } from "zmp-sdk/apis";

openMediaPicker({
  type: "photo",
  serverUploadUrl: "https://<your-domain-api>/upload/media",
  compressLevel: 2, //Optional if you need to compress the image
  success: (res) => {
    // handle the api call success
    const { data } = res;
    const result = JSON.parse(data);
    console.log(result);
  },
  fail: (error) => {
    // handle the api call failure
    console.log(error);
  },
});
```

Or

```jsx
import { openMediaPicker } from "zmp-sdk/apis";

const pickMedia = async () => {
  try {
    const { data } = await openMediaPicker({
      type: "photo",
      serverUploadUrl: "https://<your-domain-api>/upload/media",
      compressLevel: 2, //Optional if you need to compress the image
    });
    const result = JSON.parse(data);
    console.log(result);
  } catch (error) {
    // handle the api call failure
    console.log(error);
  }
};
```