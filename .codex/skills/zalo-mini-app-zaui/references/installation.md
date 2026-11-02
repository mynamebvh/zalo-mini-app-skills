# Installation

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/installation

Last updated: October 28, 2026

```sh
npm install zmp-ui
```

---

## Usage

**HomePage.jsx**

```js
import React from "react";
import { Button } from "zmp-ui";

const HomePage = (props) => {
  return Button;
};
export default HomePage;
```

Add stylesheets:

**App.js**

```js
import React from "react";
import { createRoot } from "react-dom/client";
/**
 * Add shared stylesheets
 * Or you can add styles for each component
 *
 * import "zmp-ui/button/styles/button.css";
 */
import "zmp-ui/zaui.css";


const root = createRoot(document.getElementById("app"));
root.render(React.createElement(HomePage));
```

---
