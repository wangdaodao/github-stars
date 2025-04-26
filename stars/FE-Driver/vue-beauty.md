---
project: vue-beauty
stars: 2111
description: Beautiful  UI components build with vue and ant design
url: https://github.com/FE-Driver/vue-beauty
---

vue-beauty
==========

Beautiful UI components build with vue and ant design

特性
--

-   丰富的组件，涵盖常用场景
-   基于vue组件化开发，数据驱动视图
-   封装复杂性，提供简单友好的api
-   基于ant design样式优化

引入
--

使用npm或者yarn

```
npm install vue-beauty -S  OR  yarn add vue-beauty

import Vue from 'vue'
//import css
import 'vue-beauty/package/style/vue-beauty.min.css'

//import components
import vueBeauty from 'vue-beauty'
Vue.use(vueBeauty)

//OR
import {alert} from 'vue-beauty'
Vue.use(alert)
```

或使用 <script> 全局引用

```
<link rel="stylesheet" href="vue-beauty.min.css"> 
<script type="text/javascript" src="vue-beauty.min.js"></script> 
```

更多说明，请查看我们的在线文档。

浏览器支持
-----

chrome、firefox、暂不支持IE(计划支持IE11+)。

Polyfill
--------

本组件库内置了一些es最新实例方法的垫片，请查看Polyfill。

更新日志
----

欢迎查看详细的更新日志。

参与贡献
----

我们欢迎任何形式的贡献，请阅读贡献指南了解详细的情况。

链接
--

-   Vue官网
-   Ant.Design官网
