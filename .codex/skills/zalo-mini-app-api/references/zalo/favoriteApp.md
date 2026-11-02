# favoriteApp

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/favoriteApp
> Last updated: 28/10/2026
> Supported from: SDK 2.27.1

```ts
import { favoriteApp } from "zmp-sdk";
```

API that adds the app to the user's favorites list in the Zalo Mini Apps Store.

![Favorites list in the Zalo Mini Apps Store](https://docs.zaloplatforms.com/assets/MA/img/api/favoriteApp/favorite_screen.jpeg)

## Example

Add the app to the favorites list:

```ts
await favoriteApp();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).