---
project: easy-monitor
stars: 3110
description: 企业级 Node.js 应用性能监控与线上故障定位解决方案
url: https://github.com/hyj1991/easy-monitor
---

Easy-Monitor 3.0
================

点击 Easy-Monitor 2.0 分支 可以访问旧的 2.x 分支查看以前的版本。

点击 Easy-Monitor 3.0 部署样例 对 3.0 版本的控制台部署和应用接入效果以及功能进行预览。

3.0 简介
------

全新的企业级 Node.js 应用性能监控与线上故障定位解决方案。

旨在 Node.js 的开源生态工具链上做一些微小的事情，希望能帮助到想使用和正在使用 Node.js 的开发者更好地感知自己的 Node.js 应用状态，来面对性能和稳定性方面的挑战。

扫钉钉二维码码可以进入本项目的开源官方讨论钉钉群：

### \- 新特性

-   Linux / MacOS / Windows 全平台支持
-   针对 Node.js 进程与系统指标的性能监控
-   错误日志展示与依赖 Npm 模块安全风险提示
-   自定义智能运维告警与线上进程实时状态导出

### \- 使用指南

Easy-Monitor 3.0 使用文档部署在语雀上，详细内容参见 Easy-Monitor 3.0 使用指南。

### \- 项目地址

因为架构整体变动巨大，Easy-Monitor 3.0 划分了多个子模块存放于组织 X-Profiler 中，地址为：https://github.com/X-Profiler

项目具体拆分的各个子模块功能简述与仓库地址：

-   3.0 版本展示控制台：xprofiler-console
-   xtransit 管理服务：xtransit-manager
-   xtransit 长连接服务：xtransit-server
-   性能日志生成插件：xprofiler
-   性能日志采集器：xtransit

### \- 设计架构

### \- 技术栈

控制台前端基于 Vue.js + iView UI 框架编写，监控服务端部分则是基于 Egg.js 框架编写，UI 部分整体参考了 AliNode 控制台。

联系我
---

如果你在使用 Easy-Monitor 3.0 项目中遇到了问题，欢迎加入钉钉群 **35149528** 一起讨论。

希望本项目能帮助开发者解决更多开发遇到的问题，构建对大家对 Node.js 技术栈的信心，愿天下没有难用的 Node.js！

如果您觉得本项目对您有帮助，请我喝一杯咖啡吧。
