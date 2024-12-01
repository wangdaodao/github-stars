---
project: vue-cesium-v2
stars: 67
description: 🎉 Vue 2.x & Vue 3.x components for CesiumJS.
url: https://github.com/zouyaoji/vue-cesium-v2
---

VUE CESIUM
==========

VueCesium, a Vue 2.x & Vue 3.x based component library of CesiumJS for GISer.

Highlight Moments
-----------------

-   🌎 2022-06-08 The moon project developed with vue-cesium was featured in the CCTV News Broadcast on June 8, 2022, at 21 minutes and 52 seconds. Screenshot.
-   🚀 2022-12-10 Joined the Cesium Certified Developer Program.
-   🎉 2023-04-25 The GitHub project `vue-cesium` has reached over 1000 stars! Thank you all for your support and contributions.

Notice
------

**This is the Vue2 version of VueCesium! Go to new version to get the updated version!**

**This project has stopped maintenance, it is recommended to use the Vue3 version of VueCesium.**

Languages
---------

-   中文
    
-   English
    
-   中文 for vue 3.x
    
-   English for vue 3.x
    

Links
-----

-   Documentation
-   Official Demo
-   More examples

Get Start
---------

VueCesium, a Vue 2.x & Vue 3.x based component library of CesiumJS for GISer.

Support loading official CesiumJS, or third-party platforms based on CesiumJS:

-   CesiumJS
-   SuperMap iClient3D for WebGL
-   Earth SDK
-   Mars3D
-   DC-SDK

### Installation

npm i --save vue-cesium@2.4.2

### Usage

// main.js
import Vue from 'vue'
import VueCesium from 'vue-cesium@2.4.2'
import lang from 'vue-cesium/lang/zh-hans'
// import lang from 'vue-cesium/lang/en-us'
Vue.use(VueCesium, {
  cesiumPath: 'https://unpkg.com/cesium@1.100/Build/Cesium/Cesium.js'
})

<template\>
  <div class\="viewer"\>
    <vc-viewer\></vc-viewer\>
  </div\>
</template\>

<style\>
  .viewer {
    width: 100%;
    height: 400px;
  }
</style\>

### Configuration

// main.js
import lang from 'vue-cesium/lang/zh-hans'
// import lang from 'vue-cesium/lang/en-us'

Vue.use(VueCesium, {
  // cesiumPath is the web service address that guides the use of Cesium.js, which can be a local or CDN address such as
  // cesiumPath: /static/Cesium/Cesium.js
  // cesiumPath: 'https://unpkg.com/cesium/Build/Cesium/Cesium.js'
  // cesiumPath: 'https://cdn.jsdelivr.net/npm/cesium@latest/Build/Cesium/Cesium.js'
  cesiumPath: 'https://cdn.jsdelivr.net/npm/cesium@1.100/Build/Cesium/Cesium.js',
  // If you need to use Cesium ion resources, you need to specify it. Go to https://cesium.com/ion/ to apply for an account and get Access Token. If it is not specified, it may cause the loading of CesiumIon's online images and terrain to fail.
  accessToken: 'Your Cesium Ion defaultAccessToken',
  lang: lang // 2.0.3+ //  zh-hans
})

License
-------

MIT License

Copyright (c) 2018-present, zouyaoji 370681295@qq.com

Sponsors
--------

See

Contributors
------------

This project wouldn't exist without our amazing contributors

QQGroup
-------

16533444

Reference
---------

Two good vue components projects: vue-baidu-map and vuelayers.
