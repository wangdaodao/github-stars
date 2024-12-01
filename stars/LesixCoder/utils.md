---
project: utils
stars: 47
description: 用js封装的常用工具方法
url: https://github.com/LesixCoder/utils
---

baselib
=======

最好用的 `JS|TS` 第三方库脚手架

⭐ 特性
----

-   支持ES6+或TypeScript编写源码，编译生成生产代码
-   多环境支持（支持浏览器原生，支持AMD，CMD，支持Webpack，Rollup，fis等，支持Node）
-   集成jsmini

> 注意: 如果不同时使用 `export` 与 `export default` 可打开 `legacy模式`，`legacy模式` 下的模块系统可以兼容 `ie6-8`，见rollup配置文件

💊 兼容性
------

单元测试保证支持如下环境：

IE

CH

FF

SF

OP

IOS

Android

Node

6+

29+

55+

9+

50+

9+

4+

4+

**注意：编译代码依赖ES5环境，对于ie6-8需要引入es5-shim才可以兼容，可以查看demo/demo-global.html中的例子**

📂 目录介绍
-------

```
.
├── demo 使用demo
├── dist 编译产出代码
├── doc 项目文档
├── src 源代码目录
├── test 单元测试
├── CHANGELOG.md 变更日志
└── TODO.md 计划功能
```

🚀 使用者指南
--------

通过npm下载安装代码

$ npm install --save baselib

如果你是node环境

var base \= require('baselib');

如果你是webpack等环境

import base from 'baselib';

如果你是requirejs环境

requirejs(\['node\_modules/baselib/dist/index.aio.js'\], function (base) {
    // xxx
})

如果你是浏览器环境

<script src\="node\_modules/baselib/dist/index.aio.js"\></script\>

📑 文档
-----

API

😘 贡献者指南
--------

首次运行需要先安装依赖

$ npm install

一键打包生成生产代码

$ npm run build

运行单元测试:

$ npm test

> 注意：浏览器环境需要手动测试，位于`test/browser`

修改 package.json 中的版本号，修改 README.md 中的版本号，修改 CHANGELOG.md，然后发布新版

$ npm run release

将新版本发布到npm

$ npm publish

贡献者列表
-----

contributors

⚙️ 更新日志
-------

CHANGELOG.md

✈️ 计划列表
-------

TODO.md
