# ZAUI Reference Index

> All documentation was crawled from https://docs.zaloplatforms.com/docs/MA/zaui (current version, updated October 28, 2026).

## Guides

- [overview](overview.md) — Introduction to ZaUI Components and links to the component groups.
- [installation](installation.md) — Installing zmp-ui and importing the zmp-ui/zaui.css stylesheet.
- [examples](examples.md) — Verified app shell, navigation, form, modal, sheet, snackbar, and theme examples with zmp-ui@1.11.15-2.
- [principles](principles.md) — Good UI gives users a sense of control, making it easy for them to understand and master the product.
- [release-notes](release-notes.md) — The source page currently has no content (only the update date).

## Foundation

- [Colors](foundation/Colors.md) — These are the 10 base colors in ZaUI Components and their derived colors.
- [CornerRadius](foundation/CornerRadius.md) — The corner radius values used in the Zalo Mini App UI Components.
- [Icons](foundation/Icons.md) — The Zi icon set and icon codes used with the Icon component.
- [LevelSpecification](foundation/LevelSpecification.md) — The Mini App UI structure; basic layers are divided into 4 levels.
- [MiniAppLogo](foundation/MiniAppLogo.md) — The basic composition of the Mini App Avatar.
- [Shadow](foundation/Shadow.md) — Used when you want the shadow to sit below the object; used for most cases.
- [Spacing](foundation/Spacing.md) — Spacing is used to separate elements in the interface. Multiples of 4 are used to define spacing values.
- [Typography](foundation/Typography.md) — Currently, there is no dedicated font for Zalo.
- [Header (foundation)](foundation/header.md) — Design guidelines for the Mini App header.

## Container

- [Box](container/Box.md) — Used as a wrapper around elements to easily add spacing between them according to the Zalo Mini App spacing system, or to quickly create a flex layout.
- [Center](container/Center.md) — Used to center an element horizontally.
- [Cluster](container/Cluster.md) — Used to group elements together with control over the spacing between them.
- [Grid](container/Grid.md) — Used to create a grid layout.
- [Stack](container/Stack.md) — Used to make it easier to arrange elements vertically in the app interface.
- [ZBox](container/ZBox.md) — Used to manage layouts that can be regarded as fixed for each element. Styles that are not specified, inherited, or inferred from the composite layouts for a specific element.

## Display

- [Avatar](display/Avatar.md) — Used to display a user's profile picture, supporting a circular shape and a fallback when there is no image.
- [Calendar](display/Calendar.md) — Used to display a calendar by time ranges.
- [Icon](display/Icon.md) — Used to display an icon illustrating an action or state.
- [ImageViewer](display/ImageViewer.md) — Used to create a gallery that lets users view images at screen size, with interactions such as zooming and swiping between images...
- [List](display/List.md) — Used to display data as a list.
- [Progress](display/Progress.md) — Used to report the progress of a long-running task.
- [Spinner](display/Spinner.md) — Used to show a loading state for content that is not yet ready to display.
- [Swiper](display/Swiper.md) — Used to display multiple images in a horizontal sliding format, such as banners, carousels...
- [Text](display/Text.md) — Used to display text data.

## Form

- [Button](form/Button.md) — Used to create buttons that let users interact to perform an action.
- [Checkbox](form/Checkbox.md) — Used to select one or more items in a group of options.
- [DatePicker](form/DatePicker.md) — Used to let users select a date.
- [Input](form/Input.md) — Used to create an input field that lets users enter text and captures the data.
- [OTP](form/OTP.md) — Used to enter an OTP code.
- [Password](form/Password.md) — Used to enter a password.
- [Picker](form/Picker.md) — Used to create an interface that lets users select one option from each data column.
- [Radio](form/Radio.md) — Used to let users select a single item in a group of options.
- [Search](form/Search.md) — Used to enter search content.
- [Select](form/Select.md) — Used to let users select one or more items across groups of options.
- [Slider](form/Slider.md) — Used to let users select a value or a range of values within a limit.
- [Switch](form/Switch.md) — Used to create a toggle that lets users turn a feature on or off.
- [TextArea](form/TextArea.md) — Used to enter long or multi-line content.

## Layout

- [AnimationRoutes](layout/AnimationRoutes.md) — Used to declare a route to a page in the app while adding a page transition effect.
- [App](layout/App.md) — Used as the root tag of the entire app. Provides shared settings that all inner components can use via context and hooks.
- [BottomNavigation](layout/BottomNavigation.md) — Used to display a fixed navigation bar at the bottom of the screen. Helps users easily navigate to other pages.
- [Header (component)](layout/Header.md) — A component that displays fixed information at the top of the screen.
- [Page](layout/Page.md) — Used to display the content of a page in the app; must be combined with `ZMPRouter` or `react-router`. Supports settings related to page scrolling.
- [Tabs](layout/Tabs.md) — Used to organize, categorize, and navigate between peer content groups that relate to the same topic.
- [ZMPRouter](layout/ZMPRouter.md) — Used to navigate between pages in a Mini App, in combination with `useNavigate`.

## Overlay

- [ActionSheet](overlay/ActionSheet.md) — Used to display a list of actions the user can choose from in the form of a [Sheet](https://docs.zaloplatforms.com/docs/MA/zaui/overlay/Sheet).
- [Modal](overlay/Modal.md) — Used to display important content or require the user to perform a specific action before continuing to use an app feature.
- [Sheet](overlay/Sheet.md) — Used to display supplementary information or let the user perform secondary actions related to the main content on the screen, or continue using an app feature.
- [SnackbarProvider](overlay/SnackbarProvider.md) — Used to create quick notifications displayed over the app interface, including notifications about additional information, success or error states when performing an action, download progress, connection status, and so on.
