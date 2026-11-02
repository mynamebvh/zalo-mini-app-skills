# Progress

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/Progress

Last updated: 28/10/2026

```ts
import { Progress } from "zmp-ui";
```

Used to report the progress of a long-running task.


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| maxCompleted | number | No | The maximum value of the progress bar, which is also the completion threshold. (default: `100`) |
| completed | number | No | The current value of the progress bar. (default: `0`) |
| formatLabel | (current: number, maxCompleted: number) => React.ReactNode | No | Function used to customize the content displayed on the label. Must be used together with `showLabel`. |
| showLabel | boolean | No | The progress label, displayed to the right of the progress bar. (default: `false`) |
| strokeWidth | number | No | The thickness of the progress bar, in px. (default: `4`) |
| strokeColor | string | No | The color of the completed portion of the progress bar. |
| trailColor | string | No | The color of the incomplete portion of the progress bar. |
