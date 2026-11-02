# ZMPRouter

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/layout/ZMPRouter

Last updated: October 28, 2026

```ts
import { ZMPRouter } from "zmp-ui";
```

Used to navigate between pages in a Mini App, in combination with `useNavigate`.

#### useNavigate

`useNavigate` (hook) works like `react-router`'s `useNavigate`, but adds options to customize page transition effects when used together with `zmp-ui`'s `ZMPRouter` and `AnimationRoutes`.

`useNavigate` returns a function that navigates to a specific route path:

```ts
(delta: number) => void
```

or

```ts
(to: string | Path, options?: ZMPNavigationOptions) => void
```

Where:

- **delta** – *number*, the number of steps to move in the history stack. For example, `navigate(-1)` is equivalent to the back button.
- **to** – *string | Path*, the path to the destination page.
- **Path** – *object*, with the following fields:

  - **pathname** – *string*
  - **search** – *string*
  - **hash** – *string*
- **ZMPNavigationOptions** – *object*, with the following fields:

  - **replace** - *boolean*, set to true to replace the current entry in the history stack instead of adding a new one.
  - **state** - *any*, used to pass extra data between pages.
  - **animate** - *boolean*, set to false to transition without animation (when using AnimationRoutes).
  - **direction** - *"forward" | "backward"*, transition with a specific page transition effect (when using AnimationRoutes).

info

- `ZMPRouter` is a wrapper around `BrowserRouter`. You can use `BrowserRouter` directly from `react-router`, but make sure `basename` is set correctly.
- `MemoryRouter` is the new router in `react-router@6`. `MemoryRouter` does not use browser history like `BrowserRouter`; instead it manages its own history stack — suitable when you want to control navigation history yourself.
- Using `MemoryRouter` means there is no default back button on the header. In this case, hide the default `actionbar` and create your own header.


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | React.ReactNode | No | Accepts `<Routes>` or `<AnimationRoutes>` directly. |
| memoryRouter | boolean | No | Use `MemoryRouter` instead of `BrowserRouter` (the default). (default: `false`) |
