---
project: fes.js
stars: 1540
description: Fes.js 是一个基于 Vue 3 好用的前端应用解决方案。以约定、配置化、组件化的设计思想，让用户仅仅关心用组件搭建页面内容。技术曲线平缓，上手也简单。在经过多个项目中打磨后趋于稳定。丰富的 Vue 3 生态 和 Fes.js 插件，让业务开发更加简单快捷~
url: https://github.com/WeBankFinTech/fes.js
---

简体中文 | English

一个好用的前端应用解决方案

-   使用文档 - http://fesjs.mumblefe.cn/
-   更新日志 - CHANGELOG.md

痛点
==

在开发一个前端项目之前，我们可能需要做如下准备工作：

-   搭建开发环境
-   约定代码规范
-   封装 API 请求
-   配置路由
-   实现布局、菜单、导航
-   实现登录
-   权限管理
-   ...

除了准备工作之外，还会遇到很多相似的业务类型，比如中后台应用大多都是工作台、增删改查、权限、图表等。如果每次项目都完全手动处理一遍，不仅耗费时间，久而久之可能会存在多种技术栈、开发规范，导致开发流程不统一，历史项目越来越难维护。所以我们需要一套完整的解决方案，管理开发到部署整个流程。

Fes.js 是什么？
-----------

Fes.js 是一个好用的前端应用解决方案。提供覆盖编译构建到代码运行的每个生命周期的插件体系，支持各种功能扩展和业务需求。以 路由为基础，同时支持配置式路由和约定式路由，保证路由的功能完备。整体上以约定、配置化、组件化的设计思想，让用户仅仅关心用组件搭建页面内容。基于 Vue.js3.0，充分利用 Vue 丰富的生态。技术曲线平缓，上手也简单。在经过多个项目中打磨后趋于稳定。

它主要具备以下功能：

-   🚀 **快速** ，内置了路由、开发、构建等，并且提供测试、布局、权限、国际化、状态管理、API 请求、数据字典、SvgIcon 等插件，可以满足大部分日常开发需求。
    
-   🧨 **简单** ，基于 Vue.js 3.0，上手简单。贯彻“约定优于配置”思想，设计插件上尽可能用约定替代配置，同时提供统一的插件配置入口，简单简洁又不失灵活。提供一致性的 API 入口，一致化的体验，学习起来更轻松。
    
-   💪 **健壮** ，只需要关心页面内容，减少写 BUG 的机会！提供单元测试、覆盖测试能力保障项目质量。
    
-   📦 **可扩展** ，借鉴 Umi 实现了完整的生命周期和插件化机制，插件可以管理项目的编译时和运行时，能力均可以通过插件封装进来，在 Fes.js 中协调有序的运行。
    
-   📡 **面向未来** ，在满足需求的同时，我们也不会停止对新技术的探索。已使用 Vue3.0 来提升应用性能，已使用 webpack5 和 vite 提升构建性能和实现微服务。
    

插件
--

插件

介绍

@fesjs/plugin-access

提供对页面资源的权限控制能力

@fesjs/plugin-enums

提供统一的枚举存取及丰富的函数来处理枚举

@fesjs/plugin-icon

svg 文件自动注册为组件

@fesjs/plugin-jest

基于 `Jest`，提供单元测试、覆盖测试能力

@fesjs/plugin-layout

简单的配置即可拥有布局，包括导航以及侧边栏

@fesjs/plugin-locale

基于 `Vue I18n`，提供国际化能力

@fesjs/plugin-model

简易的数据管理方案

@fesjs/plugin-request

基于 `Axios` 封装的 request，内置防止重复请求、请求节流、错误处理等功能

@fesjs/plugin-vuex

基于 `Vuex`, 提供状态管理能力

@fesjs/plugin-qiankun

基于 `qiankun`，提供微服务能力

@fesjs/plugin-sass

样式支持 sass

@fesjs/plugin-monaco-editor

提供代码编辑器能力， 基于`monaco-editor`（VS Code 使用的代码编辑器）

@fesjs/plugin-windicss

基于 `windicss`，提供原子化 CSS 能力

@fesjs/plugin-pinia

pinia，状态处理

@fesjs/plugin-watermark

水印

@fesjs/plugin-swc

webpack构建中使用 swc-loader，构建速度蹭蹭蹭

像数 1, 2, 3 一样容易
---------------

使用 `pnpm`：

# 创建模板
pnpm create @fesjs/fes-app myapp

# 安装依赖
pnpm i

# 运行
pnpm dev

使用 `npm`：

# 创建模板
npx @fesjs/create-fes-app myapp

# 安装依赖
npm install

# 运行
npm run dev

项目样例
----

使用 fes.js 构建的优秀项目，欢迎联系。

项目

描述

三维可视化项目快速落地の开源框架

反馈
--

Github Issue

Fes.js 开源运营小助手

@fesjs/fes.js/issues

参与共建
----

我们非常欢迎社区同学能提交 PR：

1.  fork 项目!
2.  创建你的功能分支: `git checkout -b my-new-feature`
3.  本地提交新代码: `git commit -am 'Add some feature'`
4.  推送本地到服务器分支: `git push origin my-new-feature`
5.  创建一个 PR

如果是发现 Bug 或者期望添加新功能，请提交issue。

社区活动
----

### Fesjs 社区有奖征文活动

为了 Fes.js 开源项目更好的运转，同时回馈开源社区，社区推出有奖征文活动！欢迎大家投递实践经验，给社区用户，更广泛的开发者提供借鉴。

经验输出也可以帮助到你系统沉淀自有项目，梳理工作思路，也能够帮助你的技术博客做宣传。优秀的实践案例将有机会邀请参与项目社区技术会议分享，赶快来参与吧。 请戳：https://mp.weixin.qq.com/s/nV4NG\_OUUrdgtft8g\_IW4g
