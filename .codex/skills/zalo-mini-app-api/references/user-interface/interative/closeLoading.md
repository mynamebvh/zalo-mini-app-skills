# closeLoading

> Source: https://docs.zaloplatforms.com/docs/MA/api/user-interface/interative/closeLoading
> Last updated: 28/10/2026
> Supported from: SDK 2.17.0

```ts
import { closeLoading } from "zmp-sdk";
```

When the user opens the Zalo Mini App, a loading screen is displayed while the Mini App is loading. This screen is called Splash Loading.
By default, Splash Loading automatically closes when the Mini App finishes loading. However, the integration side can choose the appropriate time to close the loading by:

- Adding the setting `selfControlLoading: true` in `app-config.json`. See [Zalo Mini App Configuration](https://docs.zaloplatforms.com/docs/MA/devtools/app-config#app).
- Calling `closeLoading` at the appropriate time to close Splash Loading.

Note:

- If `selfControlLoading: true` is set but this API is not called, **the Mini App will be stuck on the Splash Loading screen**.
- Since the code calling this API is only executed after the Mini App has finished loading, Splash Loading will close later than usual. Only use this mechanism when necessary (to reduce layout shift or when you do not want users to see incomplete content).

## Example

Close the loading after HomePage has finished rendering:

```ts
function HomePage() {
  useEffect(() => {
    closeLoading();
  }, []);
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).