# Swiper

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/Swiper

Last updated: 28/10/2026

```ts
import { Swiper } from "zmp-ui";
```

Used to display multiple images in a horizontal sliding format, such as a banner, carousel, and so on.


## Props

### SwiperProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| autoplay | boolean | No | Configures the automatic slide switching mechanism. (default: `false`) |
| afterChange | (currentIndex: number) => void | No | Callback invoked after the slider has moved to a new slide. |
| defaultActive | number | No | The index of the starting slide when the slider is rendered. |
| dots | boolean | No | Displays slide-switching dots below the slider. (default: `true`) |
| children | React.ReactNode | No | Contains the `` components. |
| loop | boolean | No | Configures the slide looping mechanism. After moving to the last slide, the slider returns to the first slide. (default: `false`) |
| duration | number | No | The time for automatic switching between slides (unit: "ms"). Must be used together with `autoplay`. |
| disableSwipe | boolean | No | Disables the slide-switching mechanism when swiping on a mobile device. (default: `false`) |

### SwiperRefObject

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| activeIndex | number | No | The index of the current slide. |
| goTo | (slideIndex: number) => void | No | Go to a specific slide. |
| next | () => void | No | Go to the next slide. |
| prev | () => void | No | Return to the previous slide. |

### SwiperSlideProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | React.ReactNode | No | The content to display in the slide. |
