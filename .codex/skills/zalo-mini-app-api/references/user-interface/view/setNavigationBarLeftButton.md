# setNavigationBarLeftButton

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarLeftButton
> Last updated: 28/10/2026

```ts
import { setNavigationBarLeftButton } from "zmp-sdk";
```

API that sets the left button on the navigation bar of the current page.

## Example

Show the back arrow:

```ts
await setNavigationBarLeftButton({
  type: "back",
});
```

Show the go-to-home button:

```ts
await setNavigationBarLeftButton({
  type: "home",
});
```

Show both the back button and the go-to-home button:

```ts
await setNavigationBarLeftButton({
  type: "both",
});
```

Do not show the left button:

```ts
await setNavigationBarLeftButton({
  type: "none",
});
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| type | `"none" \| "back" \| "home" \| "both"` | No | The type of the left button. (default: "back") |