# ImageViewer

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/ImageViewer

Last updated: 28/10/2026

```ts
import { ImageViewer } from "zmp-ui";
```

Used to create a gallery that lets users view images at full screen size, with support for zooming, switching images, and more.


## Props

### ImageViewerProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| images | ImageType[] | No | An array containing information about the images to display. Each entry includes the image's path and description. See details at . |
| activeIndex | number | No | The index of the image currently being displayed. |
| visible | boolean | No | The display state of the image viewer. Must be used together with `onClose` to close the image viewer. (default: `false`) |
| onClose | () => void | No | Callback invoked when the image viewer is closed. If provided, the state of `visible` must be updated. |
| maskStyle | CSSProperties | No | Inline style for the image viewer's mask. |
| maskClassName | string | No | CSS class for the image viewer's mask. |

### ImageType

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| src | string | No | The image's path. |
| alt | string | No | The image's description. Will be displayed when the image cannot be loaded. |
