# openDocument

> Source: https://docs.zaloplatforms.com/docs/MA/api/media/file/openDocument
> Last updated: 22/12/2025
> Supported from: SDK 2.48.0, Android 25.09.01 (842), IOS 25.06.02 (666)

```ts
import { openDocument } from "zmp-sdk";
```

API that allows the app to view documents (PDF) directly from a URL or a local file in [LFS](https://docs.zaloplatforms.com/docs/MA/api/lfs/localFileSystem).

## Example

Open a PDF document from a URL:

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf"
});
```

Open a PDF document from a URL with a custom title:

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf",
  title: "Sample document"
});
```

Open a PDF document from a URL with a custom title and enable the download feature:

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf",
  title: "Sample document",
  download: true
});
```

Open a PDF document from a URL with a custom title and enable the edit feature (supported on ios only):

```ts
openDocument({
  url: "https://pdfobject.com/pdf/sample.pdf",
  title: "Sample document",
  edit: true
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| url | `string` | Yes | URL of the document to open. Currently only the PDF document format is supported. |
| title | `string` | No | Title of the document on the header bar. Defaults to the name taken from the URL. |
| share | `boolean` | No | Requests that the document sharing feature be enabled. The SDK only forwards this value on Android when the supporting conditions are met. (default: false) |
| download | `boolean` | No | Enables the document download feature. Defaults to false. (default: false) |
| edit | `boolean` | No | Enables the document edit feature (supported on ios only). Defaults to false. (default: false) |