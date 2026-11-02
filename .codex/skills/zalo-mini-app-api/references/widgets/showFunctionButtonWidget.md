# showFunctionButtonWidget

> Source: https://docs.zaloplatforms.com/docs/MA/api/widgets/showFunctionButtonWidget
> Last updated: 28/10/2026
> Supported from: SDK 2.39.0

```ts
import { showFunctionButtonWidget } from "zmp-sdk";
```

Function Button Widget: When the user taps this button, the Mini App will receive 1 interact token (valid for 1 hour).

From version `2.52.2` and above, `showFunctionButtonWidget` supports displaying multiple Function Button Widgets on the same page; each widget needs an element with a separate `id`.

![Widget FunctionButton](https://docs.zaloplatforms.com/assets/images/function_button_widget-a4f5805d306239f21aae8e631fd02460.png)

## Example

Display the Function Button Widget:

```ts
import React, { useEffect } from "react";
import { showFunctionButtonWidget } from "zmp-sdk/apis";

function HomePage() {
  useEffect(() => {
    showFunctionButtonWidget({
      id: "orderButton",
      type: "ORDER",
      text: "Order",
      color: "#0068FF",
      textColor: "#FFFFFF",
      borderRadius: "48px",
      onDataReceived: (interactToken) => {
        console.log(interactToken);
      },
      onError: (error) => {
        console.error("onError:", error.code, error.message);
      },
    });
  }, []);

  return (
    <>
      ...
      <div id="orderButton" />
      ...
    </>
  );
}

export default HomePage;
```

> See the error handling guide and the detailed error code table [here](https://docs.zaloplatforms.com/docs/MA/api/errorCode).

## Parameters

Pass parameters to the API as an object with the following properties:

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| id | `string` | Yes | The ID of the element where the widget should be displayed. Each widget on the same page needs to use an element with a separate ID. |
| type | `"ORDER"` | Yes | The type of the button, currently only the value `ORDER` is supported. |
| text | `string` | Yes | The string displayed in the button. - The following values will return an `interactToken`: `Pay`, `Confirm and pay`, `Book a ride`, `Order`, `Subscribe to a plan` |
| fontSize | `string` | No | The font size. The minimum value is 14px. (default: "16px") |
| color | `string` | No | The primary color of the widget. The value must be a hex string. (default: "#0068FF") |
| textColor | `string` | No | The text color in the button. The value must be a hex string. (default: "#FFFFFF") |
| borderRadius | `string` | No | Border radius (rounds the corners of the button). (default: "48px") |
| disabled | `boolean` | No | The disabled state of the widget. |
| onDataReceived | `(interactToken: string, type: string, context: { callAction: (actionName: string, actionData: any) => void }) => void` | No | Callback called when the user taps the widget. The callback receives an `interactToken` valid for 1 hour, the widget `type`, and `context` containing the `callAction(actionName, actionData)` function. |
| onError | `(error: AppError) => void` | No | Callback called when an error occurs while the user taps the widget. This callback contains `error`, which is the error information. |