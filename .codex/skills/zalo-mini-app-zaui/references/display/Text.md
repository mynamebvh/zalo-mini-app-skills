# Text

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/Text

Last updated: 28/10/2026

```ts
import { Text } from "zmp-ui";
```

Used to display text data.

## Usage


### Props

#### BodyTextProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| size | 'xLarge' \| 'large' \| 'normal' \| 'small' \| 'xSmall' \| 'xxSmall' \| 'xxxSmall' \| 'xxxxSmall' | No | The size of the text |
| children | React.ReactNode | No | The text content to display inside the text |
| bold | boolean | No | Makes the text bold (default: `false`) |

#### HeaderTextProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| size | 'normal' \| 'small' | No | The size of the header |
| children | React.ReactNode | No | The text content to display inside the header |

#### TitleTextProps

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| size | 'xLarge' \| 'large' \| 'normal' \| 'small' | No | The size of the title |
| children | React.ReactNode | No | The text content to display inside the title |

## Design guidelines

Currently, there is no dedicated font for Zalo.
The default sans-serif font of each OS is used for text in the Zalo interface.

| OS | Font famiy |
| --- | --- |
| iOS | SF Pro Text SF Pro Display SF UI Text SF UI Display |
| Android | Roboto |

---

##### Header Text

Use heading for banners, pop-ups, bottom sheets, and so on.

**xLarge**

Title Text/ xLarge

The deep blue sky stretched endlessly, without a single cloud

Style: xLarge

Size: 22px

Line height: 26px

Font weight: 500

**xLarge**

Title Text/ xLarge

The deep blue sky stretched endlessly, without a single cloud

Style: xLarge

Size: 22px

Line height: 26px

Font weight: 500

**Normal**

Title Text/ Normal

The deep blue sky stretched endlessly, without a single cloud

Style: Normal

Size: 18px

Line height: 24px

Font weight: 500

**Small**

Title Text/ Small

The deep blue sky stretched endlessly, without a single cloud

Style: Small

Size: 15px

Line height: 20px

Font weight: 500

##### Body Text

Body text is the main content portion, typically used to convey content

**xLarge**

Body Text/ xLarge

The deep blue sky stretched endlessly, without a single cloud

Style: xLarge

Size: 18px

Line height: 24px

Font weight: 400

**xLarge M**

Body Text/ xLarge M

The deep blue sky stretched endlessly, without a single cloud

Style: xLarge M

Size: 18px

Line height: 24px

Font weight: 500

**Large**

Body Text/ Large

The deep blue sky stretched endlessly, without a single cloud

Style: Large

Size: 16px

Line height: 22px

Font weight: 400

**Large M**

Body Text/ Large M

The deep blue sky stretched endlessly, without a single cloud

Style: Large M

Size: 16px

Line height: 22px

Font weight: 500

**Normal**

Body Text/ Normal

The deep blue sky stretched endlessly, without a single cloud

Style: Normal

Size: 15px

Line height: 20px

Font weight: 400

**Normal M**

Body Text/ Normal M

The deep blue sky stretched endlessly, without a single cloud

Style: Normal M

Size: 15px

Line height: 20px

Font weight: 500

**Small**

Body Text/ Small

The deep blue sky stretched endlessly, without a single cloud

Style: Small

Size: 14px

Line height: 18px

Font weight: 400

**Small M**

Body Text/ Small M

The deep blue sky stretched endlessly, without a single cloud

Style: Small M

Size: 14px

Line height: 18px

Font weight: 500

**xSmall**

Body Text/ xSmall

The deep blue sky stretched endlessly, without a single cloud

Style: xSmall

Size: 13x

Line height: 18px

Font weight: 400

**xSmall M**

Body Text/ xSmall M

The deep blue sky stretched endlessly, without a single cloud

Style: xSmall M

Size: 13x

Line height: 18px

Font weight: 500

**xxSmall**

Body Text/ xxSmall

The deep blue sky stretched endlessly, without a single cloud

Style: xxSmall

Size: 12x

Line height: 16px

Font weight: 400

**xxSmall M**

Body Text/ xxSmall M

The deep blue sky stretched endlessly, without a single cloud

Style: xxSmall M

Size: 12x

Line height: 16px

Font weight: 500

**xxxSmall**

Body Text/ xxxSmall

The deep blue sky stretched endlessly, without a single cloud

Style: xxxSmall

Size: 11x

Line height: 16px

Font weight: 400

**xxxSmall M**

Body Text/ xxxSmall M

The deep blue sky stretched endlessly, without a single cloud

Style: xxxSmall M

Size: 11x

Line height: 16px

Font weight: 500

**xxxxSmall**

Body Text/ xxxxSmall

The deep blue sky stretched endlessly, without a single cloud

Style: xxxxSmall

Size: 10x

Line height: 14px

Font weight: 400

**xxxxSmall M**

Body Text/ xxxxSmall M

The deep blue sky stretched endlessly, without a single cloud

Style: xxxxSmall M

Size: 10x

Line height: 14px

Font weight: 500
