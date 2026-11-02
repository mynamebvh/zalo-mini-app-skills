# setupAd

> Source: https://docs.zaloplatforms.com/docs/MA/api/advertising/setupAd
> Last updated: 28/10/2026
> Supported from: SDK 2.37.0

```ts
import { setupAd } from "zmp-sdk";
```

Configures the information used to serve ads. Call this API when the app initializes.

> **Info**
>
> This feature is in a trial phase and is available only to selected partners.

## Example

Inside `app.ts`:

```ts
import React from "react";
import { createRoot } from "react-dom/client";
import { setupAd } from "zmp-sdk/apis";

import "zmp-ui/zaui.css";
import "./css/app.scss";

// Setup advertising
setupAd();

const root = createRoot(document.getElementById("app"));
root.render(React.createElement(App));
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).
