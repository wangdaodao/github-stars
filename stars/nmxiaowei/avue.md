---
project: avue
stars: 2290
description: Avue.js2.0是基于现有的element-ui库进行的二次封装，简化一些繁琐的操作，核心理念为数据驱动视图,主要的组件库针对table表格和form表单场景，同时衍生出更多企业常用的组件，达到高复用，容易维护和扩展的框架，同时内置了丰富了数据展示组件，让开发变得更加容易
url: https://github.com/nmxiaowei/avue
---

Avue.js
=======

Avue.js 是基于现有的 element-plus 库进行的二次封装，从而简化一些繁琐的操作，核心理念为**数据驱动视图**。主要的组件库针对 table 表格和 form 表单场景，同时衍生出更多企业常用的组件，达到高复用，容易维护和扩展的框架，同时内置了丰富的数据展示组件，让开发变得更加容易。

✨ 特性
----

-   🚀 **高效开发**：基于数据驱动视图的理念，大大减少了代码量
-   📦 **开箱即用**：丰富的表格、表单配置及多种常用组件
-   🛠️ **强大定制**：高度灵活的配置项，满足各种复杂场景需求
-   🔌 **扩展性强**：支持自定义组件和多种交互方式
-   📚 **详尽文档**：完善的文档和示例，快速上手无烦恼

🔧 安装
-----

# 使用 pnpm 安装（推荐）
pnpm add @smallwei/avue

# 或使用 npm 安装
npm install @smallwei/avue

# 或使用 yarn 安装
yarn add @smallwei/avue

📦 使用
-----

// 完整引入
import { createApp } from 'vue'
import Avue from '@smallwei/avue'
import '@smallwei/avue/dist/avue.css'
import App from './App.vue'

const app \= createApp(App)
app.use(Avue)
app.mount('#app')

📄 文件说明
-------

文件名

用途

说明

avue.min.js

生产环境

压缩优化版本，体积更小

avue.js

开发环境

包含完整的调试信息

📚 文档与示例
--------

要查看详细文档和在线示例，请访问：官方文档

🌈 相关产品
-------

除了核心框架外，我们还提供以下解决方案：

-   **数据大屏** - 专业的可视化数据大屏解决方案
-   **数据组态** - 工业物联网数据组态平台
-   **AI大模型** - 智能AI应用解决方案

🤝 参与贡献
-------

1.  Fork 本仓库
2.  新建 Feature 分支
3.  提交代码
4.  创建 Pull Request

❓ 问答与支持
-------

有关问题和支持，请使用issues。我们会尽快为您解答。

> **注意**：提交问题前，请务必提供详细的问题过程和截图，不符合准则的问题将会被拒绝。

📄 开源协议
-------

MIT

Copyright (c) 2017-present, Smallwei
