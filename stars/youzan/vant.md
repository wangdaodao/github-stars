---
project: vant
stars: 23401
description: A lightweight, customizable Vue UI library for mobile web apps.
url: https://github.com/youzan/vant
---

Vant
====

A lightweight, customizable Vue UI library for mobile web apps.

Documentation   ·   Documentation (backup)   ·   中文介绍

* * *

Features
--------

-   🚀 1KB Component average size (min+gzip)
-   🚀 80+ High quality components
-   🚀 Zero third-party dependencies
-   💪 90%+ Unit test coverage
-   💪 Written in TypeScript
-   📖 Extensive documentation and demos
-   📖 Provide Sketch and Axure design resources
-   🍭 Support Vue 2 & Vue 3
-   🍭 Support Nuxt 2 & Nuxt 3, provide Vant Module for Nuxt
-   🍭 Support Tree Shaking
-   🍭 Support Custom Theme
-   🍭 Support Accessibility (still improving)
-   🍭 Support Dark Mode
-   🍭 Support SSR
-   🌍 Support i18n, built-in 30+ languages

Install
-------

Using `npm` to install:

# install latest Vant for Vue 3 project
npm i vant

# install Vant 2 for Vue 2 project
npm i vant@latest-v2

Using `yarn`, `pnpm`, or `bun`:

# with yarn
yarn add vant

# with pnpm
pnpm add vant

# with Bun
bun add vant

Scaffold
--------

It is recommended to use Rsbuild to create a scaffold project.

Rsbuild is a build tool based on Rspack, developed by the author of Vant, with first-class build speed and development experience, providing first-priority support for Vant.

You can create a Rsbuild project with the following command:

npm create rsbuild@latest

Please visit the Rsbuild repository for more information.

Quickstart
----------

import { createApp } from 'vue';
// 1. Import the components you need
import { Button } from 'vant';
// 2. Import the components style
import 'vant/lib/index.css';

const app \= createApp();

// 3. Register the components you need
app.use(Button);

See more in Quickstart.

Browser Support
---------------

Vant 2 supports modern browsers and Android >= 4.0、iOS >= 8.0.

Vant 3/4 supports modern browsers and Chrome >= 51、iOS >= 10.0 (same as Vue 3).

Official Ecosystem
------------------

Project

Description

vant-weapp

WeChat MiniProgram UI

vant-demo

Collection of Vant demos

vant-cli

Scaffold for UI library

vant-icons

Vant icons

vant-touch-emulator

Using vant in desktop browsers

vant-nuxt

Vant module for Nuxt

Community Ecosystem
-------------------

Project

Description

3lang3/react-vant

React mobile UI Components based on Vant

vant-aliapp

Alipay MiniProgram UI

vant-theme

Online theme preview built on Vant UI

@antmjs/vantui

Mobile UI Components based on Vant, supporting Taro and React

Taroify

Taroify is the Taro version of Vant

vant-playground

Vant Playground

sfc-playground-vant

Vant Playground

vue3-h5-template

Mobile project template based on Vant

vue3-vant-mobile

Mobile project template based on Vant

vscode-common-intellisense

A VS Code extension that provides better intellisense to Vant developers

Links
-----

-   Documentation
-   Documentation (backup)
-   Changelog
-   Discussions

Preview
-------

You can scan the following QR code to access the demo：

Core Team
---------

Core contributors of Vant and Vant Weapp:

chenjiahan

cookfront

wangnaiyi

pangxie

rex-zsd

nemo-shen

Lindysen

JakeLaoyu

landluck

wjw-gavin

inottn

zhousg

All Contributors
----------------

Thanks to the following friends for their contributions to Vant:

Contribution Guide
------------------

Please make sure to read the Contributing Guide before making a pull request.

Start On Web IDE
----------------

https://github.dev/youzan/vant

LICENSE
-------

Vant is MIT licensed.
