# minimizeApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/minimizeApp
> Last updated: 28/10/2026
> Supported from: SDK 2.26.1

```ts
import { minimizeApp } from "zmp-sdk";
```

API that proactively minimizes the app. When the API is called, the Mini App is minimized into a floating icon at the corner of the screen, allowing users to temporarily use other Zalo features and return to your Mini App without reloading from the beginning.

![Minimize app](https://docs.zaloplatforms.com/assets/MA/img/ZMA-Floating.png) The app has been minimized

## Example

Minimize the app:

```ts
await minimizeApp();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).