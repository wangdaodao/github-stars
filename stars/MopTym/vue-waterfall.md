---
project: vue-waterfall
stars: 2195
description: A waterfall layout component for Vue.js
url: https://github.com/MopTym/vue-waterfall
---

vue-waterfall
=============

A waterfall layout component for Vue.js .

Branch 0.x (version 0.x.x) is compatible with Vue 1 .

Demo
----

-   Vertical line
-   Horizontal line
-   Vertical line with grow

Installation
------------

npm install --save vue-waterfall

Usage
-----

Vue-waterfall is a UMD module, which can be used as a module in both CommonJS and AMD modular environments. When in non-modular environment, `Waterfall` will be registered as a global variable.

### Import

#### ES6

/\* in xxx.vue \*/

import Waterfall from 'vue-waterfall/lib/waterfall'
import WaterfallSlot from 'vue-waterfall/lib/waterfall-slot'

/\*
 \* or use ES5 code (vue-waterfall.min.js) :
 \* import { Waterfall, WaterfallSlot } from 'vue-waterfall'
 \*/

export default {
  ...
  components: {
    Waterfall,
    WaterfallSlot
  },
  ...
}

#### ES5

var Vue \= require('vue')
var Waterfall \= require('vue-waterfall')

var YourComponent \= Vue.extend({
  ...
  components: {
    'waterfall': Waterfall.waterfall,
    'waterfall-slot': Waterfall.waterfallSlot
  },
  ...
})

#### Browser

<script src\="path/to/vue/vue.min.js"\></script\>
<script src\="path/to/vue-waterfall/vue-waterfall.min.js"\></script\>

new Vue({
  ...
  components: {
    'waterfall': Waterfall.waterfall,
    'waterfall-slot': Waterfall.waterfallSlot
  },
  ...
})

### HTML structure

<waterfall :line-gap\="200" :watch\="items"\>
  <!-- each component is wrapped by a waterfall slot -->
  <waterfall-slot
    v-for\="(item, index) in items"
    :width\="item.width"
    :height\="item.height"
    :order\="index"
    :key\="item.id"
  \>
    <!--
      your component
    -->
  </waterfall-slot\>
</waterfall\>

Props
-----

### waterfall

Name

Default

Description

line

`v`

`v` or `h` . Line direction.

line-gap

\-

Required. The standard space (px) between lines.

min-line-gap

\= line-gap

The minimal space between lines.

max-line-gap

\= line-gap

The maximal space between lines.

single-max-width

\= max-line-gap

The maximal width of slot which is single in horizontal direction.

fixed-height

`false`

Fix slot height when line = `v` .

grow

\-

Number Array. Slot flex grow factors in horizontal direction when line = `v` . Ignore `*-gap` .

align

`left`

`left` or `right` or `center` . Alignment.

auto-resize

`true`

Reflow when window size changes.

interval

`200`

The minimal time interval (ms) between reflow actions.

watch

`{}`

Watch something, reflow when it changes.

### waterfall-slot

Name

Default

Description

width

\-

Required. The width of slot.

height

\-

Required. The height of slot.

order

`0`

The order of slot, often be set to `index` in `v-for` .

key

`''`

The unique identification of slot, required for transition.

move-class

\-

Class for transition. see vue-animated-list .

Transition
----------

Inspired by vue-animated-list , vue-waterfall supports moving elements with `translate` in transition, click on the demo page to see it.

vue-waterfall has not supported `<transition-group>` in Vue 2 ( #10 ) .

Events
------

ON ( 'reflow' ) {
  reflow
}
// trigger reflow action: waterfallVm.$emit('reflow')

AFTER ( reflow ) {
  emit 'reflowed'
}
// waterfallVm.$on('reflowed', () => { console.log('reflowed') })

Reactivity
----------

WHEN ( layout property changes ) { /\* line, line-gap, etc. \*/
  reflow
}

WHEN ( slot changes ) { /\* add, remove, etc. \*/
  reflow
}

License
-------

Released under the MIT License.
