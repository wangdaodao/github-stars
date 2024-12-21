---
project: vue-slider-component
stars: 2425
description: 🌡 A highly customized slider component
url: https://github.com/NightCatSama/vue-slider-component
---

> 🎚 A highly customized slider component

English | 简体中文 | Русский

🍉 Vue3.x
---------

This is still in beta and may contain unexpected bugs, please use with caution.

#### install

$ yarn add vue-slider-component@next
# npm install vue-slider-component@next --save

#### Breaking Changes

-   `value` -> `modelValue`. (Official API Changes)

✨ Features
----------

-   🍖 More customizable
-   👗 Multiple style themes
-   🐳 Support for more sliders
-   📌 Add marks
-   🎉 Support SSR
-   🍒 Support Typescript

📚 Documentation
----------------

Document: https://nightcatsama.github.io/vue-slider-component

Live Demo: https://jsfiddle.net/NightCatSama/2xy72dod/10547/

🎯 install
----------

$ yarn add vue-slider-component
# npm install vue-slider-component --save

🚀 Usage
--------

Vue 2

<template\>
  <vue-slider v-model\="value" />
</template\>

<script\>
import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/antd.css'
export default {
  components: {
    VueSlider,
  },
  data() {
    return {
      value: 0,
    }
  },
}
</script\>

Vue 3

<template\>
  <vue-slider v-model\="value" />
</template\>

<script setup>
import { reactive, toRefs } from 'vue'
import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/antd.css'
export default {
  setup() {
    const data \= reactive({ value: 0 })
    return toRefs(data)
  },
}
</script\>

Changelog
---------

Detailed changes for each release are documented in the release notes.

Support
-------

If my code has helped you, please consider buy me a coffee ☕.

License
-------

MIT
