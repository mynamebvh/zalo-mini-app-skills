# Tabs

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/layout/Tabs

Last updated: October 28, 2026

```ts
import { Tabs } from "zmp-ui";
```

Used to organize, categorize, and navigate between peer content groups that relate to the same topic.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | React.ReactNode | No | The elements inside `Tabs`; using `Tab` components is recommended |
| items | Tab[] | No | An array configuring the tabs to display. Use instead of `children`. |
| activeKey | string | No | The key of the currently selected tab. Must be used together with `onChange` to update this value when the user requests a tab switch |
| defaultActiveKey | string | No | The key of the tab selected by default when the tabs are initialized. Changing this value after rendering has no effect |
| onChange | (activeKey: string) => void | No | Callback called when the user requests a tab switch. Update the value of `activeKey` to change the selected tab if it is passed in |
| scrollable | boolean | No | Allows horizontal scrolling when there are too many tabs to fit on one line (default: `false`) |
| onTabClick | (activeKey: string, e: React.KeyboardEvent \| React.MouseEvent) => void | No | Callback called when a tab label is clicked |
| renderTabBar | (props: RenderTabBarProps) => React.ReactElement | No | Used to customize the tab control bar's interface instead of using the default `TabBar` component.<br>The function receives the settings needed to render the tab control bar as well as the event handler for when the user requests a tab switch, and returns a ReactElement to display to the user. |
| bottomBar | boolean | No | Displays the tab control bar at the bottom instead of at the top as by default (default: `false`) |
| destroyInactiveTabPane | boolean | No | Automatically cleans up unselected tabs (default: `false`) |

## Design guidelines

##### Tabs

Tabs help organize, categorize, and navigate between peer content groups that relate to the same topic.

###### Anatomy

![Anatomy](https://docs.zaloplatforms.com/assets/MA/img/zaui/tabs/anatomy.png)

- 1

  Container

- Required

- 2

  Active Tab Item

- Required

- 3

  Inactive Tab Item

- Required

- 4

  Divider

- Required

---

###### Usage

- Use when:
- There are 2 or more tab items
- The number of tab items is fixed when the user uses the feature and is not affected by any user input
- The content of each tab item is concise

![Usage](https://docs.zaloplatforms.com/assets/MA/img/zaui/tabs/usage.png)
