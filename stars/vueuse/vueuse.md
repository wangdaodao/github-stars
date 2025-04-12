---
project: vueuse
stars: 20939
description: Collection of essential Vue Composition Utilities for Vue 3
url: https://github.com/vueuse/vueuse
---

  
Collection of essential Vue Composition Utilities

  

🚀 Features
-----------

-   🎪 **Interactive docs & demos**
-   ⚡ **Fully tree shakeable**: Only take what you want, bundle size
-   🦾 **Type Strong**: Written in TypeScript, with TS Docs
-   🔋 **SSR Friendly**
-   🌎 **No bundler required**: Usable via CDN
-   🔩 **Flexible**: Configurable event filters and targets
-   🔌 **Optional Add-ons**: Router, Firebase, RxJS, etc.

🦄 Usage
--------

import { useLocalStorage, useMouse, usePreferredDark } from '@vueuse/core'

const { x, y } \= useMouse()

// if user prefers dark theme
const isDark \= usePreferredDark()

// persist state in localStorage
const store \= useLocalStorage(
  'my-storage',
  {
    name: 'Apple',
    color: 'red',
  },
)

Refer to functions list or documentations for more details.

📦 Install
----------

> From v12.0, VueUse no longer supports Vue 2. Please use v11.x for Vue 2 support.

npm i @vueuse/core

Add ons | Nuxt Module

###### Demos

-   Vite + Vue 3
-   Nuxt 3 + Vue 3
-   Webpack + Vue 3

### CDN

<script src="https://unpkg.com/@vueuse/shared"></script\>

<script src="https://unpkg.com/@vueuse/core"></script\>

It will be exposed to global as `window.VueUse`

🪴 Project Activity
-------------------

🧱 Contribute
-------------

See the **Contributing Guide**

🌸 Thanks
---------

This project is heavily inspired by the following awesome projects.

-   streamich/react-use
-   u3u/vue-hooks
-   logaretm/vue-use-web
-   kripod/react-hooks

And thanks to all the contributors on GitHub!

👨‍🚀 Contributors
------------------

### Financial Contributors on Open Collective

📄 License
----------

MIT License © 2019-PRESENT Anthony Fu
