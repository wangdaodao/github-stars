---
project: v-lazy-show
stars: 497
description: Compile-time directive to lazy initialize v-show for Vue
url: https://github.com/antfu/v-lazy-show
---

v-lazy-show
===========

A compile-time directive to lazy initialize v-show for Vue. It makes components mount after first truthy value (`v-if`), and the DOM keep alive when toggling (`v-show`).

Install
-------

npm i -D v-lazy-show

This package is completely compile-time, installed it as a `nodeTransformer` in Vue's compiler options.

For example in Vite:

// vite.config.ts
import { transformLazyShow } from 'v-lazy-show'
import { defineConfig } from 'vite'

export default defineConfig({
  plugins: \[
    Vue({
      template: {
        compilerOptions: {
          nodeTransforms: \[
            transformLazyShow, // <--- add this
          \],
        },
      },
    }),
  \]
})

In Nuxt:

// nuxt.config.ts
export default defineNuxtConfig({
  modules: \[
    'v-lazy-show/nuxt'
  \]
})

Usage
-----

You can use it as a directive. Both `v-lazy-show` and `v-show.lazy` are supported and equivalent.

<script setup lang="ts">
const show \= ref(false)
</script\>

<template\>
  <div v-lazy-show\="show"\>
    <MyComponent />
  </div\>
</template\>

With it, `<MyComponent />` will not be mounted for the first render. Until the first time `show.value = true`, it will be mounted and the DOM will be kept alive. Later if you switch `show.value` back to `false`, `<MyComponent />` will not be unmounted, instead, `display: none` will be applied to the DOM just like `v-show`.

Use Cases
---------

It can be helpful to use with some component that is expensive to create/mount. For example, if you have a tabs component, that some tab contains a heavy component. Using `v-if`, it will get the component destroyed and re-created when switching tabs. Using `v-show`, you will need to pay the mounting cost on the initial render even you haven't switch to that tab yet.

With `v-lazy-show`, you can have the best of both worlds. You can think it as a `v-show` that lazy initializes, or a `v-if` that caches the DOM.

Similarly, this can be helpful for `<details>`, `<dialog>`, `<tabs>`, `<popups>` and other components that you want to keep the DOM alive when toggling.

How does it work?
-----------------

Like how `v-if` works, when you use this directive, it hint the compiler to do some transformation to the generated vnodes.

<template\>
  <div v-lazy-show\="foo"\>
    Hello
  </div\>
</template\>

will be compiled to

import { createCommentVNode as \_createCommentVNode, createElementBlock as \_createElementBlock, createElementVNode as \_createElementVNode, Fragment as \_Fragment, openBlock as \_openBlock, vShow as \_vShow, withDirectives as \_withDirectives } from 'vue'

export function render(\_ctx, \_cache) {
  return (\_cache.\_lazyshow1 || \_ctx.foo)
    ? (\_cache.\_lazyshow1 \= true, (\_openBlock(),
      \_withDirectives(\_createElementVNode('div', null, ' Hello ', 512 /\* NEED\_PATCH \*/), \[
        \[\_vShow, \_ctx.foo\]
      \])))
    : \_createCommentVNode('v-show-if', true)
}

Sponsors
--------

License
-------

MIT License © 2022 Anthony Fu
