# Colors

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/foundation/Colors

Last updated: 28/10/2026

## Base color palette

These are the 10 base colors in ZaUI Components and their derived colors.

Steel Blue

steelblue-10#F1F4F8

steelblue-15#E2E9F1

steelblue-20#D9E2ED

steelblue-25#C7D5E5

steelblue-30#B2C5DC

steelblue-40#8EABCD

steelblue-50#6991BF

steelblue-55#507FB4

steelblue-60#426D9E

steelblue-70#32547B

steelblue-80#274362

steelblue-85#1F344D

steelblue-90#17283B

steelblue-95#111E2C

steelblue-100#0B141E

Sky Blue

skyblue-10#F0FBFF

skyblue-15#DBF6FF

skyblue-20#C7F1FF

skyblue-25#ADEBFF

skyblue-30#8FE3FF

skyblue-40#5CD6FF

skyblue-50#29C9FF

skyblue-55#00BCFA

skyblue-60#00A8E0

skyblue-70#0082AD

skyblue-80#00678A

skyblue-85#00506B

skyblue-90#003D52

skyblue-95#002E3D

skyblue-100#001F29

Teal

teal-10#F1FEFD

teal-15#DDFDFB

teal-20#CAFCF9

teal-25#B1FBF7

teal-30#94FAF5

teal-40#62F8F1

teal-50#31F6ED

teal-55#08E7DC

teal-60#07D5CA

teal-70#04A9A1

teal-80#038C85

teal-85#026964

teal-90#01514D

teal-95#003D3A

teal-100#002927

Blue

blue-10#F0F7FF

blue-15#DBEBFF

blue-20#C7E0FF

blue-25#ADD1FF

blue-30#8FBFFF

blue-40#5ca0ff

blue-50#297EFF

blue-55#0068FF

blue-60#005AE0

blue-70#0045AD

blue-80#00378A

blue-85#002B6B

blue-90#002152

blue-95#00183D

blue-100#001029

Green

green-10#ECF9F0

green-15#E0F5E7

green-20#D1F0DB

green-25#BEE9CC

green-30#A3E0B8

green-40#7DD49A

green-50#57C77C

green-55#3EBB6C

green-60#32A458

green-70#258344

green-80#1b6935

green-85#135328

green-90#0d3f1e

green-95#092f16

green-100#051F0E

Red

red-10#FFF0F0

red-15#FFDBDB

red-20#FFC7C7

red-25#FFADAD

red-30#FF8F8F

red-40#FF5C5C

red-50#FF3333

red-55#F50000

red-60#DB0000

red-70#AD0000

red-80#840000

red-85#6B0000

red-90#520000

red-95#3D0000

red-100#290000

Orange

orange-10#FFF6F0

orange-15#ffeadb

orange-20#FFDDC7

orange-25#FFCEAD

orange-30#FFBC8F

orange-40#FF9D5C

orange-50#FF7E29

orange-55#FF6905

orange-60#E05A00

orange-70#AD4500

orange-80#8A3700

orange-85#6B2B00

orange-90#522100

orange-95#3D1800

orange-100#291000

Yellow

yellow-10#FFFBF0

yellow-15#FFF7DB

yellow-20#FFF2C7

yellow-25#FFECAD

yellow-30#FFE58F

yellow-40#FFD95C

yellow-50#FFCD29

yellow-55#FAC000

yellow-60#E0A000

yellow-70#AD8500

yellow-80#8A6A00

yellow-85#6B5200

yellow-90#523F00

yellow-95#3D2F00

yellow-100#291F00

Pink

pink-10#FEF0FB

pink-15#FDDDF7

pink-20#FCCAF2

pink-25#FBB1EC

pink-30#F994E5

pink-40#F764D9

pink-50#F434CE

pink-55#E90CBC

pink-60#D50BAD

pink-70#A50986

pink-80#830764

pink-85#660552

pink-90#4E043F

pink-95#3A032F

pink-100#27021F

Purple

purple-10#F6F3FC

purple-15#EAE2F8

purple-20#DDD2F4

purple-25#CEBEEF

purple-30#BCA5E9

purple-40#9D7CDE

purple-50#7E54D4

purple-55#6937CD

purple-60#5A2DB4

purple-70#452388

purple-80#371C6E

purple-85#281556

purple-90#211041

purple-95#180C31

purple-100#100821

## Neutral color palette

gray-10#F7F7F8

gray-15#EBEDEF

gray-20#E0E3E5

gray-25#D3D6DA

gray-30#C2C7CB

gray-40#A9ADB2

gray-50#909498

gray-55#808285

gray-60#6F7071

gray-70#575757

gray-80#3D3D3D

gray-85#2E2E2E

gray-90#212121

gray-95#171717

gray-100#0D0D0D

## Programmatic Usage

```sh
npm install zaui-tokens
```

### CSS

```css
@import "zaui-tokens/variables.css";

.text-primary {
  color: var(--colors-blue-primary);
}
```

### JavaScript

```sh
npm install zaui-tokens
```

```js
import { colors } from "zaui-tokens";

console.log(colors.blue);
console.log(colors.blue.primary);
console.log(colors.blue.DEFAULT);
```

### Tailwind

```js
const config = require("zaui-tokens/tailwind.config.json");

// file: tailwind.config.js

module.exports = {
  theme: {
    extend: {
      colors: config.colors
    }
  }
};
```
