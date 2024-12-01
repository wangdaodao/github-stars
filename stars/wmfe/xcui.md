---
project: xcui
stars: 88
description: :fork_and_knife: A Vue.js 2.x desktop components colletion
url: https://github.com/wmfe/xcui
---

About
-----

XCUI 是基于`Vue2.0`的**桌面端组件库**。

XCUI的目标是：

-   满足桌面端页面大部分基础组件需求。
-   快速开发基于 `Vue2.0` 构建的项目。
-   保持小体积, 无其他js库依赖(No jquery, No Bootstrap, etc)
-   简洁优雅。

组件展示
----

XCUI主页

版本支持
----

在使用`Vue 2.x` 版本时，推荐使用 `Vue 2.0.8` 以上版本。

安装
--

通过`npm`安装。

npm install xcui

具体的安装方式请见这里。

快速上手
----

`xcui`使用`umd`方式打包，支持各种模块加载器。

在页面根实例中引入：

import Vue from 'vue'
import xcui from 'xcui'
import 'xcui/lib/xcui.css'
Vue.use(xcui);

在页面中声明标签，即可使用。

> **说明** XCUI在使用`Vue.use(xcui)`后，会默认以`x-`前缀注册所有组件，在Vue实例中可直接使用而**不用在`components`中声明**。举例：

<x-button type\="primary"\>start</x-button\>

更多详细信息请见这里。

开发
--

### Clone the repo

```
$ git clone git@github.com:wmfe/xcui.git
```

### 安装依赖

```
$ npm i
```

### Run dev server

```
$ npm run dev
```

### Build components

```
$ npm run build
```
