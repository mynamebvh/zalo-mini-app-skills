# Calendar

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/Calendar

Last updated: 28/10/2026

```ts
import { Calendar } from "zmp-ui";
```

Used to display a calendar by date ranges.

Tips

If you need to select a date, please use [DatePicker](https://docs.zaloplatforms.com/docs/MA/zaui/form/DatePicker).


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| disabledDate | (date: Date) => boolean | No | Function called to check whether the specified date can be selected |
| cellRender | CellRender | No | Function called to render the content inside each date cell, excluding the header |
| fullCellRender | CellRender | No | Function called to render the content inside each date cell, including the header |
| daysOfWeekRender | (date: Date, info: CellRenderInfo) => React.ReactElement | No | Function called to render each day of the week in fullscreen mode |
| headerRender | HeaderRender | No | Function called to render the component's header |
| value | Date | No |  |
| defaultValue | Date | No | The default value of the date |
| locale | string | No | The language used for the component |
| fullscreen | boolean | No | The display style of the component |
| startOfWeek | '0' \| '1' \| '2' \| '3' \| '4' \| '5' \| '6' | No | The starting day of the week (from 0 to 6, corresponding to Sunday through Monday) (default: `0`) |
| numberOfWeek | 'auto' \| number | No | The number of weeks displayed in the month (default is "auto") (default: `"auto"`) |
| dayOfWeekNameFormat | 'short' \| 'long' | No | The format of the day-of-week names (default is "short") (default: `"short"`) |
| dayOfWeekNameRender | (day: number) => string \| React.ReactElement | No | Function called to render the day-of-week names |
| onPanelChange | (date: Date, mode: CalendarMode) => void | No | Function called when the component's value and display mode change |
| onSelect | (date: Date, selectInfo: SelectInfo) => void | No | Function called when the user selects a date |
| autoHeight | boolean | No | The Calendar's height will follow the current panel |
