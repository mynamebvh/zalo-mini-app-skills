# Page

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/layout/Page

Last updated: October 28, 2026

```ts
import { Page } from "zmp-ui";
```

Used to display the content of a page in the app; must be combined with `ZMPRouter` or `react-router`. Supports settings related to page scrolling.


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | ReactNode | No | The page content |
| resetScroll | boolean | No | When used with React Router, by default the scroll position is preserved when navigating between pages. This property resets the scroll to the top of the page when navigating between pages, similar to the normal page transition mechanism. (default: `true`) |
| hideScrollbar | boolean | No | Hides the page's scrollbar (default: `false`) |
| restoreScroll | boolean | No | Restores the page's scroll position if it was scrolled previously. Unlike `resetScrollOnBack`, this property always restores the scroll position regardless of where the page was navigated from. (default: `false`) |
| restoreScrollOnBack | boolean | No | Restores the page's scroll position when returning from another page (when the user presses the back button, performs an edge-swipe gesture from the screen edge, or calls `navigate(-1)` from code). (default: `false`) |
| name | string | No | The page name, used to distinguish pages from one another.<br>This property can also be used to identify the page's scroll position if `restoreScroll` or `restoreScrollOnBack` is set. |

Tips

- For pages inside Tabs, use `restoreScroll` to restore the position when switching tabs or returning from another page.
- For regular pages, use `restoreScrollOnBack` to restore the position when returning from another page.
- If the page has special states such as a collapsed menu, pagination, infinite scroll, etc., store the data in global state to ensure the previous state is restored correctly and to improve the UX of the mini app.
