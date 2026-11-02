# SnackbarProvider

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/overlay/SnackbarProvider

Last updated: 28/10/2026

```ts
import { SnackbarProvider } from "zmp-ui";
```

Used to create quick notifications displayed over the application's interface, using notifications about additional information, success or error states that occur when using an action, download progress, connection status, and so on.


## Props

### SnackbarProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | ReactNode | No | The content to display in the snackbar |
| zIndex | number | No | Customizes the depth of the snackbar, used when multiple overlay elements stack on top of each other. |

### SnackbarContext

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| openSnackbar | (options: SnackbarOptions) => void | No | Function to create and open a Snackbar. The Snackbar can be opened with the |
| closeSnackbar | () => void | No | Function to close a Snackbar, which can be used to close it quickly before the display time has elapsed. |
| setDownloadProgress | (completed: number) => void | No | Updates the download progress percentage (0 - 100) when used with `type` set to `download`. |

### SnackbarAction

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| close | boolean | No |  |
| text | string | No |  |
| onClick | (event: React.MouseEvent) => void | No |  |

### SnackbarOptions

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| position | SnackbarPosition | No |  |
| duration | number | No |  |
| text | string | No |  |
| type | SnackbarType | No |  |
| action | SnackbarAction | No |  |
| prefixIcon | ReactNode | No |  |
| icon | boolean | No |  |
| verticalAction | boolean | No |  |
| zIndex | number | No |  |
| onClose | () => void | No |  |
