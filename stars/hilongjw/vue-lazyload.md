---
project: vue-lazyload
stars: 8026
description: A Vue.js plugin for lazyload your Image or Component in your application.
url: https://github.com/hilongjw/vue-lazyload
---

Vue-Lazyload
============

Vue module for lazyloading images in your applications. Some of goals of this project worth noting include:

-   Be lightweight, powerful and easy to use
-   Work on any image type
-   Add loading class while image is loading
-   Supports both of Vue 1.0 and Vue 2.0

For Vue 3
=========

Please use vue-lazyload@3.x, see here

Table of Contents
=================

-   _**Demo**_
-   _**Requirements**_
-   _**Installation**_
-   _**Usage**_
-   _**Constructor Options**_
-   _**Implementation**_
    -   _**Basic**_
    -   _**Css state**_
-   _**Methods**_
    -   **Event hook**
    -   **LazyLoadHandler**
    -   **Performance**
-   _**Authors && Contributors**_
-   _**License**_

Demo
====

_**Demo**_

Requirements
============

-   Vue.js `1.x` or `2.x`

Installation
============

npm
---

$ npm i vue-lazyload -S

yarn
----

$ yarn add vue-lazyload

CDN
---

CDN: https://unpkg.com/vue-lazyload/vue-lazyload.js

<script src\="https://unpkg.com/vue-lazyload/vue-lazyload.js"\></script\>
<script\>
  Vue.use(VueLazyload)
  ...
</script\>

Usage
=====

main.js:

import Vue from 'vue'
import App from './App.vue'
import VueLazyload from 'vue-lazyload'

Vue.use(VueLazyload)

// or with options
const loadimage \= require('./assets/loading.gif')
const errorimage \= require('./assets/error.gif')

Vue.use(VueLazyload, {
  preLoad: 1.3,
  error: errorimage,
  loading: loadimage,
  attempt: 1
})

new Vue({
  el: 'body',
  components: {
    App
  }
})

template:

<ul\>
  <li v-for\="img in list"\>
    <img v-lazy\="img.src" \>
  </li\>
</ul\>

use `v-lazy-container` work with raw HTML

<div v-lazy-container\="{ selector: 'img' }"\>
  <img data-src\="//domain.com/img1.jpg"\>
  <img data-src\="//domain.com/img2.jpg"\>
  <img data-src\="//domain.com/img3.jpg"\>  
</div\>

custom `error` and `loading` placeholder image

<div v-lazy-container\="{ selector: 'img', error: 'xxx.jpg', loading: 'xxx.jpg' }"\>
  <img data-src\="//domain.com/img1.jpg"\>
  <img data-src\="//domain.com/img2.jpg"\>
  <img data-src\="//domain.com/img3.jpg"\>  
</div\>

<div v-lazy-container\="{ selector: 'img' }"\>
  <img data-src\="//domain.com/img1.jpg" data-error\="xxx.jpg"\>
  <img data-src\="//domain.com/img2.jpg" data-loading\="xxx.jpg"\>
  <img data-src\="//domain.com/img3.jpg"\>  
</div\>

Constructor Options
-------------------

key

description

default

options

`preLoad`

proportion of pre-loading height

`1.3`

`Number`

`error`

src of the image upon load fail

`'data-src'`

`String`

`loading`

src of the image while loading

`'data-src'`

`String`

`attempt`

attempts count

`3`

`Number`

`listenEvents`

events that you want vue listen for

`['scroll', 'wheel', 'mousewheel', 'resize', 'animationend', 'transitionend', 'touchmove']`

Desired Listen Events

`adapter`

dynamically modify the attribute of element

`{ }`

Element Adapter

`filter`

the image's listener filter

`{ }`

Image listener filter

`lazyComponent`

lazyload component

`false`

Lazy Component

`dispatchEvent`

trigger the dom event

`false`

`Boolean`

`throttleWait`

throttle wait

`200`

`Number`

`observer`

use IntersectionObserver

`false`

`Boolean`

`observerOptions`

IntersectionObserver options

{ rootMargin: '0px', threshold: 0.1 }

IntersectionObserver

`silent`

do not print debug info

`true`

`Boolean`

### Desired Listen Events

You can configure which events you want vue-lazyload by passing in an array of listener names.

Vue.use(VueLazyload, {
  preLoad: 1.3,
  error: 'dist/error.png',
  loading: 'dist/loading.gif',
  attempt: 1,
  // the default is \['scroll', 'wheel', 'mousewheel', 'resize', 'animationend', 'transitionend'\]
  listenEvents: \[ 'scroll' \]
})

This is useful if you are having trouble with this plugin resetting itself to loading when you have certain animations and transitions taking place

### Image listener filter

dynamically modify the src of image

Vue.use(vueLazy, {
    filter: {
      progressive (listener, options) {
          const isCDN \= /qiniudn.com/
          if (isCDN.test(listener.src)) {
              listener.el.setAttribute('lazy-progressive', 'true')
              listener.loading \= listener.src + '?imageView2/1/w/10/h/10'
          }
      },
      webp (listener, options) {
          if (!options.supportWebp) return
          const isCDN \= /qiniudn.com/
          if (isCDN.test(listener.src)) {
              listener.src += '?imageView2/2/format/webp'
          }
      }
    }
})

### Element Adapter

Vue.use(vueLazy, {
    adapter: {
        loaded ({ bindType, el, naturalHeight, naturalWidth, $parent, src, loading, error, Init }) {
            // do something here
            // example for call LoadedHandler
            LoadedHandler(el)
        },
        loading (listender, Init) {
            console.log('loading')
        },
        error (listender, Init) {
            console.log('error')
        }
    }
})

### IntersectionObserver

use Intersection Observer to to improve performance of a large number of nodes.

Vue.use(vueLazy, {
  // set observer to true
  observer: true,

  // optional
  observerOptions: {
    rootMargin: '0px',
    threshold: 0.1
  }
})

### Lazy Component

Vue.use(VueLazyload, {
  lazyComponent: true
});

<lazy-component @show\="handler"\>
  <img class\="mini-cover" :src\="img.src" width\="100%" height\="400"\>
</lazy-component\>

<script\>
  {
    ...
    methods: {
      handler (component) {
        console.log('this component is showing')
      }
    }

  }
</script\>

Use in list

<lazy-component v-for\="(item, index) in list" :key\="item.src" \>
  <img class\="mini-cover" :src\="item.src" width\="100%" height\="400"\>
</lazy-component\>

Implementation
--------------

### Basic

vue-lazyload will set this img element's `src` with `imgUrl` string

<script\>
export default {
  data () {
    return {
      imgObj: {
        src: 'http://xx.com/logo.png',
        error: 'http://xx.com/error.png',
        loading: 'http://xx.com/loading-spin.svg'
      },
      imgUrl: 'http://xx.com/logo.png' // String
    }
  }
}
</script\>

<template\>
  <div ref\="container"\>
     <img v-lazy\="imgUrl"/>
     <div v-lazy:background-image\="imgUrl"\></div\>

     <!-- with customer error and loading -->
     <img v-lazy\="imgObj"/>
     <div v-lazy:background-image\="imgObj"\></div\>

     <!-- Customer scrollable element -->
     <img v-lazy.container ="imgUrl"/>
     <div v-lazy:background-image.container\="img"\></div\>

    <!-- srcset -->
    <img v-lazy\="'img.400px.jpg'" data-srcset\="img.400px.jpg 400w, img.800px.jpg 800w, img.1200px.jpg 1200w"\>
    <img v-lazy\="imgUrl" :data-srcset\="imgUrl' + '?size=400 400w, ' + imgUrl + ' ?size=800 800w, ' + imgUrl +'/1200.jpg 1200w'" />
  </div\>
</template\>

### CSS state

There are three states while img loading

`loading` `loaded` `error`

<img src\="imgUrl" lazy\="loading"\>
<img src\="imgUrl" lazy\="loaded"\>
<img src\="imgUrl" lazy\="error"\>

<style\>
  img\[lazy\=loading\] {
    /\*your style here\*/
  }
  img\[lazy\=error\] {
    /\*your style here\*/
  }
  img\[lazy\=loaded\] {
    /\*your style here\*/
  }
  /\*
  or background-image
  \*/
  .yourclass\[lazy\=loading\] {
    /\*your style here\*/
  }
  .yourclass\[lazy\=error\] {
    /\*your style here\*/
  }
  .yourclass\[lazy\=loaded\] {
    /\*your style here\*/
  }
</style\>

Methods
-------

### Event Hook

`vm.$Lazyload.$on(event, callback)` `vm.$Lazyload.$off(event, callback)` `vm.$Lazyload.$once(event, callback)`

-   `$on` Listen for a custom events `loading`, `loaded`, `error`
-   `$once` Listen for a custom event, but only once. The listener will be removed once it triggers for the first time.
-   `$off` Remove event listener(s).

#### `vm.$Lazyload.$on`

#### Arguments:

-   `{string} event`
-   `{Function} callback`

#### Example

vm.$Lazyload.$on('loaded', function ({ bindType, el, naturalHeight, naturalWidth, $parent, src, loading, error }, formCache) {
  console.log(el, src)
})

#### `vm.$Lazyload.$once`

#### Arguments:

-   `{string} event`
-   `{Function} callback`

#### Example

vm.$Lazyload.$once('loaded', function ({ el, src }) {
  console.log(el, src)
})

#### `vm.$Lazyload.$off`

If only the event is provided, remove all listeners for that event

#### Arguments:

-   `{string} event`
-   `{Function} callback`

#### Example

function handler ({ el, src }, formCache) {
  console.log(el, src)
}
vm.$Lazyload.$on('loaded', handler)
vm.$Lazyload.$off('loaded', handler)
vm.$Lazyload.$off('loaded')

### LazyLoadHandler

`vm.$Lazyload.lazyLoadHandler`

Manually trigger lazy loading position calculation

#### Example

this.$Lazyload.lazyLoadHandler()

### Performance

this.$Lazyload.$on('loaded', function (listener) {
  console.table(this.$Lazyload.performance())
})

### Dynamic switching pictures

 <img v-lazy\="lazyImg" :key\="lazyImg.src"\>

Authors && Contributors
=======================

-   hilongjw
-   imcvampire
-   darrynten
-   biluochun
-   whwnow
-   Leopoldthecoder
-   michalbcz
-   blue0728
-   JounQin
-   llissery
-   mega667
-   RobinCK
-   GallenHu

License
=======

The MIT License
