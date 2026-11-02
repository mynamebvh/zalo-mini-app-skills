# setNavigationBarTitle

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/view/setNavigationBarTitle
> Last updated: 28/10/2026

```ts
import { setNavigationBarTitle } from "zmp-sdk";
```

API that sets the title on the navigation bar of the current page.

## Example

When the user visits the Cart page:

```ts
function CartPage() {
  useEffect(() => {
    setNavigationBarTitle({ title: "Cart" });
  }, []);
}
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| title | `string` | Yes | The new title to set for the page. |