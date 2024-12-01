---
project: vue2-flip-countdown
stars: 231
description: A countdown timer with flip effect for Vue 2.x
url: https://github.com/philipjkim/vue2-flip-countdown
---

vue2-flip-countdown
===================

A simple flip countdown timer component for Vue 2.x

Demo

Notes on v1.0.0+
----------------

`1.x.x` versions are based on Webpack 5.x, whereas `0.x.x` versions are based on Webpack 3.x. If you have any trouble when upgrading to `1.x.x`, please roll back version to `0.x.x`.

Installation
------------

```
npm i vue2-flip-countdown --save
```

### Running Demo on Local Machine

```
cd demo
npm i
npm run serve
```

Then open http://localhost:8080 on a browser.

Usage
-----

<template\>
  <div\>
    <flip-countdown deadline\="2018-12-25 00:00:00"\></flip-countdown\>
  </div\>
</template\>

<script\>
  import FlipCountdown from 'vue2-flip-countdown'
  export default {
    components: { FlipCountdown }
  }
</script\>

-   If you want to remove days section, set `showDays` prop to `false` (available since v0.10.0)
    
-   If you want to remove hours/minutes/seconds section, set `showHours`/`showMinutes`/`showSeconds` prop to `false` (available since v0.11.0)
    
    <flip-countdown deadline\="2018-12-25 00:00:00" :showDays\="false"\></flip-countdown\>
    
-   To notify if timer has elapsed, bind a handler to `timeElapsed` event emitted by component
    
    <flip-countdown deadline\="2018-12-25 00:00:00" @timeElapsed\="timeElapsedHandler"\></flip-countdown\>
    

Please refer to `/demo` directory for examples.

If you're using Nuxt.js, use `<no-ssr>` to avoid server-side rendering. (You will get error if you don't use `<no-ssr>`)

<template\>
  <div\>
    <no-ssr\>
      <flip-countdown deadline\="2018-12-25 00:00:00"\></flip-countdown\>
    </no-ssr\>
  </div\>
</template\>

References
==========

-   vuejs-countdown
-   Demo for 'Flip clock & countdown, Vue'
