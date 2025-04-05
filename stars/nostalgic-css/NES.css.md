---
project: NES.css
stars: 21018
description: NES-style CSS Framework | ファミコン風CSSフレームワーク
url: https://github.com/nostalgic-css/NES.css
---

日本語 / 简体中文 / Español / Português / Русский / Français

NES.css is a **NES-style(8bit-like)** CSS Framework.

Installation
------------

### Styles

NES.css is available via either npm (preferred), Yarn, or a CDN.

#### via package manager

npm install nes.css
# or
yarn add nes.css

Our `package.json` contains some additional metadata under the following keys:

-   `sass` - path to our main Sass source file
-   `style` - path to our non-minified CSS

##### AltCSS(sass, scss...)

// style.scss
@import "./node\_modules/nes.css/css/nes.css"

##### JavaScript

// script.js
import "nes.css/css/nes.min.css";

You need to install css-loader.

##### HTML

<!-- index.html -->
<html\>
  <head\>
    <link rel\="stylesheet" href\="./node\_modules/nes.css/css/nes.min.css"\>
  </head\>
  <body\></body\>
</html\>

#### via CDN

Import the CSS via a `<link />` element:

<!-- minify -->
<link href\="https://unpkg.com/nes.css@2.3.0/css/nes.min.css" rel\="stylesheet" />
<!-- latest -->
<link href\="https://unpkg.com/nes.css@latest/css/nes.min.css" rel\="stylesheet" />
<!-- core style only -->
<link href\="https://unpkg.com/nes.css/css/nes-core.min.css" rel\="stylesheet" />

### Fonts

NES.css doesn't provide any fonts, but we do maintain the following list of fonts that we recommend for usage alongside the library.

Language

Font

(Default)

Press Start 2P

English

Kongtext

Japanese

美咲フォント

Japanese

Nu もち

Korean

둥근모꼴

Chinese

Zpix (最像素)

Usage
-----

NES.css only provides components. You will need to define your own layout.

The recommended font for NES.css is Press Start 2P. However, Press Start 2P only supports English characters. When you're using this framework with any language other than English, please use another font. Follow the Google Fonts instructions about how to include them, or simply include it as below:

<head\>
    <link href\="https://fonts.googleapis.com/css?family=Press+Start+2P" rel\="stylesheet"\>
    <link href\="https://unpkg.com/nes.css/css/nes.css" rel\="stylesheet" />

    <style\>
      html, body, pre, code, kbd, samp {
          font-family: "font-family you want to use";
      }
    </style\>
</head\>

CSS Only
--------

NES.css only requires CSS and doesn't depend on any JavaScript.

Browser Support
---------------

NES.css is compatible with the newest version of the following browsers:

-   Chrome
-   Firefox
-   Safari

Untested

-   IE/Edge

Copyright and license
---------------------

Code and documentation copyright 2018 B.C.Rikko. Code released under the MIT License. Docs released under Creative Commons.

Development
-----------

If you'd like to help us out with the project, we welcome contributions of all types! Check out our `CONTRIBUTING.md` for more details on how you can help make NES.css amazing!
