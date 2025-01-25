---
project: vue-masonry
stars: 682
description: 💠 Vue.js directive for masonry blocks layouting ✅
url: https://github.com/shershen08/vue-masonry
---

vue-masonry
===========

**Current version: 0.16.0**

Vue.js directive for masonry blocks layouting. Original masonry library.

Plugin DEMO available 🎉, JSFiddle DEMO

The plugin can be easily integrated with different CSS Frameworks. Check this Tailwind CSS DEMO.

You can also clone the basic demo repository vue-masonry + vue-cli webpack.

Usage
-----

### Install via NPM

-   Get from npm: `npm install vue-masonry --save`
    
    or from bower `bower install vue-masonry`
    
-   Make sure that the masonry library is included; for example using cdn link: `<script async defer src="https://cdnjs.cloudflare.com/ajax/libs/masonry/4.0.0/masonry.pkgd.min.js"></script>` or in other convenient way.
    

### Usage with build tools

-   In your Vue app you'll have the following code:
    
    ```
    import Vue from 'vue'
    
    // import ES6 style
    import {VueMasonryPlugin} from 'vue-masonry';
    
    // or using CJS 
    // const VueMasonryPlugin = require('vue-masonry').VueMasonryPlugin
    
    Vue.use(VueMasonryPlugin)
    
    <div v-masonry="containerId" transition-duration="0.3s" item-selector=".item">
        <div v-masonry-tile class="item" v-for="(item, index) in blocks">
           <!-- block item markup -->
        </div>
    </div>
    ```
    

### Usage with Vue 3

-   Use version >= `0.14.0`
    
-   or of using **earlier** version: Dependencies: mitt package In your Vue 3 app, you'll have the following code
    
    ```
    import { createApp } from 'vue'
    import mitt from 'mitt'
    
    import { VueMasonryPlugin } from "vue-masonry";
    
    const emitter = mitt()
    let app = createApp(App)
    app.config.globalProperties.emitter = emitter
    app.use(VueMasonryPlugin)
    app.mount('#app')
    
    const containerId = 42 // optional, if you need multiple containers on page
    const blocks = [1,2,3,4,5,6]
    
    <div v-masonry="containerId" transition-duration="0.3s" item-selector=".item">
      <div v-masonry-tile class="item" v-for="(item, index) in blocks">
        <!-- block item markup -->
      </div>
    </div>
    ```
    

### Usage directly in the browser

Since v 0.11.3 in-browser usage is available using a direct script inclusion on the page like so:

```
<script src="https://unpkg.com/vue-masonry@0.11.3/dist/vue-masonry-plugin-window.js"></script>
```

```
var VueMasonryPlugin = window["vue-masonry-plugin"].VueMasonryPlugin
Vue.use(VueMasonryPlugin)
```

### Properties

Properties that are currently available reproduce most of those on the original masonry plugin:

-   `item-selector=".item"` - list element DOM item selector;
-   `transition-duration="0.3s` - duration of transitions;
-   `column-width="#test"` - element selector for column width. Can be a selector string or a number;
-   `origin-left="false"` - set to group elements to the right instead of left by default;
-   `origin-top="false"` - set to group elements to the bottom instead of top by default;
-   `stamp=".stamp"` - specifies which elements are stamped within the layout;
-   `gutter=".gutter-block-selector"` - specifies \[horizontal space between item elements\]. Can be a selector string or a number. (https://masonry.desandro.com/options.html#gutter). Set gutter to an Element or Selector String to use the outer width of the element;
-   `fit-width="true"` - sets the width of the container to fit the available number of columns;
-   `horizontal-order="true"` - lays out items to (mostly) maintain horizontal left-to-right order;
-   `stagger="0.03s"` - Staggers item transitions, so items transition incrementally after one another. Set as a CSS time format, '0.03s', or as a number in milliseconds, 30.
-   `destroy-delay="0"` - Amount of time (in milliseconds) to wait before unloading masonry via `masonry.destroy()` when the container is destroyed. This is useful during page/route transitions to ensure the layout is consistent while the transition takes place.

If you need to manually trigger masonry layout redraw (for example in case if your tile elements amount or content has changed) you can now use `this.$redrawVueMasonry('containerId')` method. As of 0.11.8 your can pass id of the block where you want to trigger the redraw.

(If you use **old version** `< 0.10.11` it can still be `Vue.redrawVueMasonry()`, but please consider to upgrade)

### NUXT ssr implementation

The best way to implement this is to use the vue-client-only plugin. This project is previously known as `vue-no-ssr`.

1.  Create a file in your plugins folder called vue-masonry.js with the following contents:

```
import Vue from 'vue'
import {VueMasonryPlugin} from 'vue-masonry'

Vue.use(VueMasonryPlugin)
```

1.  Add this plugin to your `nuxt.config.js`

```
  plugins: [
    { src: '~/plugins/vue-masonry', ssr: false }
  ]
```

(NB make sure ssr is set to false)

1.  Add `client-only` wrapper and the markup for your vue-masonry to a component:

HTML:

```
    <client-only>
      <div v-masonry transition-duration="3s" item-selector=".item" class="masonry-container">
        <div v-masonry-tile class="item" :key="index" v-for="(item, index) in blocks">
          <p>{{item}} - {{index}}</p>
        </div>
      </div>
    </client-only>
```

JS:

```
  import ClientOnly from 'vue-client-only'

  export default {
    components: {
      ClientOnly
    },
    mounted () {
      if (typeof this.$redrawVueMasonry === 'function') {
        this.$redrawVueMasonry()
      }
    }
  }
```

An example implementation of vue-no-ssr old version + vue-masonry with nuxt can be found here - https://github.com/richlloydmiles/example-vue-masonry-ssr

### Contributing

Thanks to all the contributors for making the plugin better!

### Questions, bugs

-   Check the original masonry library docs
-   Create an issue or ping me on twitter @legkoletat

### Known issues

-   Minor API change (JAN 2018). If you suddenly see error: `Uncaught TypeError: _vue2.default.redrawVueMasonry is not a function` - please upgrade your usage of the plugin's method `redrawVueMasonry` in component methods from `Vue.redrawVueMasonry()` to `this.$redrawVueMasonry();`. See more details in #31 issue

### License

MIT
