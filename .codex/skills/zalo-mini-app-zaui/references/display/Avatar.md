# Avatar

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/Avatar

Last updated: 28/10/2026

```ts
import { Avatar } from "zmp-ui";
```

Used to display a user's profile picture, supporting a circular shape and a fallback when there is no image.


## Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| online | boolean | No | Displays the Avatar's online status (default: `false`) |
| story | StoryStatus | No | Accepts the values: `default`, `seen` |
| size | number | No | Avatar size |
| src | string | No | `src` for the avatar's `img` tag |
| backgroundColor | 'BLUE-BLUELIGHT' \| 'PURPLE-BLUE' \| 'SKYBLUE-GREEN' \| 'GREEN-GREENLIGHT' | No | The avatar's background color. Valid values include:<br>- `BLUE-BLUELIGHT`: Dark blue<br>- `PURPLE-BLUE`: Purple-blue<br>- `SKYBLUE-GREEN`: Light sky blue-green<br>- `GREEN-GREENLIGHT`: Dark green-light green<br>If not specified in advance and the Avatar is a string, the value will be precomputed based on the Avatar content. |
| blocked | boolean | No | The avatar's blocked state. If true, the avatar will display a locked state. (default: `false`) |
| onClick | React.MouseEventHandler | No | Callback invoked when the user clicks on the avatar. |
| children | React.ReactNode | No |  |
