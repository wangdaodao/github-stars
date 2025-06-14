---
project: element3
stars: 3280
description: A Vue.js 3.0 UI Toolkit for IT Education. Build with JS&TS
url: https://github.com/hug-sun/element3
---

Introduction
------------

A Vue.js 3.0 UI Toolkit for Web.

Install
-------

npm install element3 -S

Quick Start
-----------

import { createApp } from 'vue'
import App from './App.vue'
// import style
import 'element3/lib/theme-chalk/index.css'
import Element3 from 'element3'

// global import
createApp(App).use(Element3).mount('#app')

// or according to the need to import
import {
  ElLink,
  ElButton
  // ...
} from 'element3'

createApp(App).use(ElLink).use(ElButton)

About
-----

-   base on element-ui
-   Table Component base on element-plus
    -   rewrite Table is WIP

Documentation
-------------

To check out live docs, visit website

Questions
---------

TODO

Issues
------

Please make sure to read the Issue Reporting Checklist before opening an issue. Issues not conforming to the guidelines may be closed immediately.

Changelog
---------

Detailed changes for each release are documented in the CHANGELOG.

Contribution ✨
--------------

use yarn instead of npm

Please make sure to read the Contributing Guide before making a pull request. If you have a Element3-related project/component/tool, add it with a pull request to this curated list!

Thank you to all the people who already contributed to Element3!

  
**shengxinjing**  
💻🎬

  
**cuixiaorui**  
💻

  
**大帅ezshine**  
🧩📺

  
**blackNezha**  
💻

  
**村长**  
🎬💻

  
**全栈然叔**  
🚌

  
**轩姐JustAMan**  
💻

Join Discussion Group
---------------------

Scan the QR code using Dingtalk App to join in discussion group :

@todo
-----

1.  table
2.  table-simple
3.  description
4.  Result
5.  Empty
6.  Statistic
7.  progress barl
8.  Skeleton
9.  Space
10.  other ...

License
-------

MIT
