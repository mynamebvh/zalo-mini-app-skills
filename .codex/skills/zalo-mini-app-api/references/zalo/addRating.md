# addRating

> Source: https://docs.zaloplatforms.com/docs/MA/api/zalo/addRating
> Last updated: 28/10/2026
> Supported from: SDK 2.28.0

```ts
import { addRating } from "zmp-sdk";
```

API that opens the app rating dialog, supporting the recording of user feedback ratings about the quality of the Mini App.

> **Warning**
>
> The rating dialog can only be displayed once per week for each user. Exceeding the above limit will return an [error](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

![App rating dialog](https://docs.zaloplatforms.com/assets/MA/img/api/addRating/addRating_screen.jpg)

## Example

Open the app rating dialog:

```ts
await addRating();
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).