# App

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/layout/App

Last updated: October 28, 2026

```ts
import { App } from "zmp-ui";
```

Used as the root tag of the entire app. Provides shared settings that all inner components can use via context and hooks.


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| theme | 'dark' \| 'light' | No | Sets the light / dark interface for components in the app (default: `'light'`) |
| children | React.ReactNode | No |  |
