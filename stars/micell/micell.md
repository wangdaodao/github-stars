---
project: micell
stars: 23
description: A collection of functions for front-end development
url: https://github.com/micell/micell
---

micell
======

**English** | **简体中文**

A collection of functions for web development.

-   Base64 encoding and decoding a string or binary data
-   Character range checking
-   Cookie manipulation
-   Date diff and format
-   DOM computing and manipulation
-   Easing functions
-   Deciding the type of Javascript value
-   File path operation
-   Querystring parse and stringify
-   Common regular expressions
-   String manipulation
-   UserAgent detection
-   Ajax, css, jsonp, random string, uuid and more.

Install
-------

**Npm**

npm i -S micell

**Yarn**

yarn add micell

**Pnpm**

pnpm add micell

**CDN**

If you want use micell with `<script>` directly, you can use jsDelivr.

The latest version:

<script src\="https://cdn.jsdelivr.net/npm/micell"\></script\>

The specific version:

<script src\="https://cdn.jsdelivr.net/npm/micell@0.15.2/dist/micell.js"\></script\>

The ES Modules version:

<script src\="https://cdn.jsdelivr.net/npm/micell@0.15.2/dist/micell.esm.browser.js"\></script\>

The micell also exists in unpkg.

Usage
-----

import micell from 'micell'

// Generate a random string
micell.randomString();

// Get a cookie value
micell.cookie.get('name')

More functions see the Docs.

### Reduce the bundle size

You can use the babel-plugin-lodash to bundle the methods as you needed.

**.babelrc**

{
  "plugins": \[
    \["lodash", { "id": \["micell"\] }\]
  \]
}

Docs
----

See Docs.

Compatibility
-------------

-   Chrome
-   Firefox
-   Safari
-   Edge
-   IE >= 11
-   iOS >= 10
-   Android >= 5

Changelog
---------

See Release notes.

Contributing
------------

If you have a bug or feature request or document improvement about micell, you can open an issue or create a pull request to main branch.

Also, you can read the CONTRIBUTING guide.

License
-------

MIT

Copyright (c) 2019-preset, Alex Chao
