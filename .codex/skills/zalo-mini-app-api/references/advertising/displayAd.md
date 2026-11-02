# displayAd

> Source: https://docs.zaloplatforms.com/docs/MA/api/advertising/displayAd
> Last updated: 28/10/2026
> Supported from: SDK 2.37.0

```ts
import { displayAd } from "zmp-sdk";
```

Displays an ad after it has loaded. The ad position is determined by the ID of each ad type.

## Example

Display a ZMA\_Middle ad:

```ts
import React from "react";
import { createRoot } from "react-dom/client";
import { setupAd, loadAd, displayAd } from "zmp-sdk/apis";

function App() {
  useEffect(() => {
    displayAd({ id: "ZMA_Middle" });
  }, []);

  return (
    <>
      ...
      <div id='ZMA_Middle' />
      ...
    </>
  );
}

setupAd();
loadAd({
  ids: ["ZMA_Middle"],
  config: {
    display: false
  }
});

const root = createRoot(document.getElementById("app"));
root.render(React.createElement(App));
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | ID of the ad type to display on the page. |
