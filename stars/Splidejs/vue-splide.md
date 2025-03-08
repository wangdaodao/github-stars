---
project: vue-splide
stars: 332
description: The Splide component for Vue.
url: https://github.com/Splidejs/vue-splide
---

Vue Splide
==========

Vue Splide is the Vue component for the Splide slider/carousel.

Getting Started  
Demo  
Discussions

Caveat
------

The latest version only supports **Vue 3**. You have to use the old version (0.3.5) for Vue 2, but the Splide version is also outdated.

Quick Start
-----------

Get the latest version from NPM:

```
$ npm install @splidejs/vue-splide
```

Import CSS and components:

<template\>
  <Splide :options\="{ rewind: true }" aria-label\="Vue Splide Example"\>
    <SplideSlide\>
      <img src\="image1.jpg" alt\="Sample 1"\>
    </SplideSlide\>
    <SplideSlide\>
      <img src\="image2.jpg" alt\="Sample 2"\>
    </SplideSlide\>
  </Splide\>
</template\>

<script\>
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import { defineComponent } from 'vue';
import '@splidejs/vue-splide/css';
export default defineComponent( {
  components: { Splide, SplideSlide },
} );
</script\>

Visit here for more details.

Support Splide
--------------

Please support the project if you like it!

-   GitHub Sponsors

License
-------

Vue Splide and Splide are released under the MIT license. © 2022 Naotoshi Fujita
