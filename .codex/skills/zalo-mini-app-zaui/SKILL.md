---
name: zalo-mini-app-zaui
description: Build, modify, or debug Zalo Mini App UI with ZAUI components from zmp-ui. Use for installation, app/router layout, forms, data display, overlays, navigation, Snackbar, theming, and component props in a Zalo Mini App React project.
---

# Zalo Mini App — ZAUI Components

This skill package bundles the official documentation for **ZaUI Components** (Zalo Mini App) and verified API examples from the `zmp-ui` package.

- Documentation source: <https://docs.zaloplatforms.com/docs/MA/zaui>
- Crawl date: 2026-11-02; the documentation states it was updated on October 28, 2026
- Reference package: `zmp-ui@1.11.15-2`
- The original documentation is in Vietnamese; component/prop names are in English.

## How to use this skill

1. Identify the component or group of tasks you need to work on.
2. Read the corresponding reference file in `references/` **before** writing code. Each file includes a complete props table and design guidelines.
3. For patterns that combine multiple components (app shell, forms, modals, snackbars...), read `references/examples.md`.
4. If you are not sure which file to use, open `references/INDEX.md`.
5. Do not invent props or APIs. If the documentation does not cover something, state clearly that it is not documented.

## Installation

```bash
npm install zmp-ui
```

Import the stylesheet once at the app entry/root:

```js
import "zmp-ui/zaui.css";
```

You can import each component's individual stylesheet, but the simplest and safest approach is to use `zmp-ui/zaui.css`.

## App shell

```jsx
import React from "react";
import { App, SnackbarProvider, ZMPRouter, AnimationRoutes, Route } from "zmp-ui";
import HomePage from "./HomePage";

export default function Root() {
  return (
    <App>
      <SnackbarProvider>
        <ZMPRouter>
          <AnimationRoutes>
            <Route path="/" element={<HomePage />} />
          </AnimationRoutes>
        </ZMPRouter>
      </SnackbarProvider>
    </App>
  );
}
```

- `App`: the application root, holds the theme and shared context.
- `SnackbarProvider`: required when using `useSnackbar`.
- `ZMPRouter` + `AnimationRoutes`: navigation and page transition effects.
- `Route`: from `zmp-ui` or `react-router-dom` (re-exported by zmp-ui).
- Each screen should wrap its content in `Page`.

## Import conventions

```js
import {
  App, Page, Header, BottomNavigation, Tabs, List, Avatar,
  Button, Input, Select, Picker, DatePicker, Checkbox, Radio, Switch,
  Modal, Sheet, SnackbarProvider, useSnackbar, useNavigate, useTheme,
  Box, Stack, Center, Cluster, Grid, ZBox, Text, Icon,
} from "zmp-ui";
```

Verified sub-components in the package:

| Component | Sub-components |
| --- | --- |
| `BottomNavigation` | `BottomNavigation.Item` |
| `Tabs` | `Tabs.Tab` |
| `List` | `List.Item` |
| `Select` | `Select.Option`, `Select.OtpGroup` (the exact export name in the package) |
| `Checkbox` | `Checkbox.Group` |
| `Radio` | `Radio.Group` |
| `Input` | `Input.Password`, `Input.Search`, `Input.TextArea`, `Input.OTP` |
| `Sheet` | `Sheet.Actions` (ActionSheet) |
| `Avatar` | `Avatar.Group` |

Available hooks: `useNavigate`, `useSnackbar`, `useTheme`, `useLocation`, `useParams`, `useSearchParams`, `useRouteError`.

## Component map

| Group | Component | Reference |
| --- | --- | --- |
| Layout | `App`, `Page`, `Header`, `BottomNavigation`, `Tabs`, `ZMPRouter`, `AnimationRoutes` | `references/layout/` |
| Form | `Button`, `Input`, `Select`, `Picker`, `DatePicker`, `Checkbox`, `Radio`, `Switch`, `Slider` | `references/form/` |
| Data display | `Avatar`, `Calendar`, `Icon`, `ImageViewer`, `List`, `Progress`, `Spinner`, `Swiper`, `Text` | `references/display/` |
| Container | `Box`, `Center`, `Cluster`, `Grid`, `Stack`, `ZBox` | `references/container/` |
| Overlay | `Modal`, `Sheet`, `Sheet.Actions`, `SnackbarProvider` | `references/overlay/` |
| Foundation | Colors, CornerRadius, Icons, Level, Logo, Shadow, Spacing, Typography | `references/foundation/` |

## Key API points

### Layout and navigation

- `Page` supports `resetScroll`, `restoreScroll`, `restoreScrollOnBack`, `hideScrollbar`.
- `BottomNavigation` uses `activeKey` + `onChange` (controlled) or `defaultActiveKey` (uncontrolled); items use `key`, `label`, `icon`, `activeIcon`.
- `Tabs` uses `Tabs.Tab` with `key` + `label`, or the `items` prop.
- `useNavigate` accepts `navigate(to, options)` or `navigate(delta)`. Options include `replace`, `state`, `animate`, `direction` (`"forward"` / `"backward"`).

### Form

- `Button`: `variant` (`primary` / `secondary` / `tertiary`), `type` (`highlight` / `danger` / `neutral`), `size`, `loading`, `disabled`, `fullWidth`, `prefixIcon`, `suffixIcon`, `icon`.
- `Input`: `value` + `onChange`; `status="error"` displays `errorText`, otherwise displays `helperText`; includes `Input.Password`, `Input.Search`, `Input.TextArea`, `Input.OTP`.
- `Select`: controlled via `value` + `onChange`; enable `multiple` to select multiple items; children are `Select.Option` (and `Select.OtpGroup` if grouping is needed).
- `DatePicker`: `value` is a `Date`, `onChange(date, pickerValue)`; constrain with `startDate` / `endDate`.
- `Checkbox.Group` and `Radio.Group` accept `options` as `{ label, value, disabled }`.

### Overlay

- `Modal`, `Sheet`, `Sheet.Actions`, and `ImageViewer` are all controlled: pass `visible` and update it in `onClose`.
- `Modal` has `description`, `actions`, `verticalActions`, `actionsDivider`; actions have `text`, `highLight`, `danger`, `close`, `disabled`, `onClick`.
- `Sheet` has `handler`, `autoHeight`, `swipeToClose`, `snapPoints`, `defaultSnapPoint`.
- `Sheet.Actions` accepts `actions` as an array of actions or an array of action groups.

### Snackbar

`useSnackbar` must be used inside `SnackbarProvider`:

```jsx
const { openSnackbar, closeSnackbar, setDownloadProgress } = useSnackbar();

openSnackbar({ text: "Saved", type: "success", duration: 3000 });
openSnackbar({ text: "An error occurred", type: "error" });
```

The `type` values supported by the package: `default`, `success`, `info`, `error`, `warning`, `loading`, `download`, `countdown`, `wifi-connected`, `wifi-disconnected`.

### Theme

`App` accepts `theme="light" | "dark"`. In child components, use:

```jsx
const [theme, setTheme] = useTheme();
setTheme({ mode: "dark" });
```

## Code rules

- Prefer ZAUI components over building your own HTML/CSS for basic elements.
- Always check the reference before using an uncommon prop; the props table in the reference is the primary source.
- For controlled components, always update state in `onChange` / `onClose`; otherwise the component will not change state.
- Do not place `BottomNavigation` inside a scroll area if you want it fixed; use `fixed`.
- Use `Box` / `Stack` / `Cluster` / `Grid` to build layouts according to the spacing system instead of arbitrary margins.
- For screens with tabs or long lists, consider `Page`'s `restoreScroll` / `restoreScrollOnBack`.
- Do not add other UI libraries if ZAUI already has an equivalent component.

## Pre-finish checklist

- [ ] Imports are correct from `zmp-ui` and `zmp-ui/zaui.css` is included.
- [ ] Every overlay component has `visible` + `onClose` wired to state.
- [ ] `useSnackbar` is inside `SnackbarProvider`.
- [ ] Props used in the code exist in the corresponding reference.
- [ ] Screen content is inside `Page` and uses an appropriate layout container.
