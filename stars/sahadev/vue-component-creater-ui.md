---
project: vue-component-creater-ui
stars: 795
description: 拖拽式Vue组件代码生成编辑器（VCC）
url: https://github.com/sahadev/vue-component-creater-ui
---

VCC 3
=====

VCC(Vue Compontent Creator)是 Low Code Generator 中独立的 Vue 组件代码编辑器。可以独立运行。当前你看到的是基于 Vue3 的 VCC 3 版本。

**通过它可以通过拖拽快速完成 Vue 组件代码骨架的搭建。详见后文视频介绍链接。**

> 点击这里快速预览效果：https://vcc3.surge.sh/ 当前已经升级至 Vue3 + Vite。

#### 使用示例

请移步至使用 Demo：https://github.com/sahadev/vcc3-use-demo

本地如何运行此项目
---------

首先进行安装:

npm i

再进行启动(Vite):

```
npm run dev
```

运行完成后，就可以访问http://localhost:9818/预览效果了.

使用介绍
----

此前在 B 站上录了两段视频。可以通过这两段视频简单了解如何使用它: \[【拖拽式Vue组件代码生成平台(LCG)介绍视频】 https://www.bilibili.com/video/BV17h411f7g2/) \[【拖拽式Vue组件代码生成平台(LCG)介绍视频】 https://www.bilibili.com/video/BV17h411f7g2/)

### 说明文档

https://vcc3-docs.surge.sh/#/

### 功能更新日志

-   2022 年 03 月 16 日 支持生成单页 Html，支持 Vue2 以及 Vue3，并支持一键部署至 VCC 服务器。
-   2023 年 12 月 06 日 更新 Element 组件库版本、更新 Vue 框架版本。

### 核心仓库

VCC 依赖于一个核心的代码转换库：vue-component-code-creater，通过这个库来完成 Vue 文件的解析和 Vue 文件的生成。如果需要更改核心实现，可通过此库提供的源码进行修改。

贡献
--

1.  Fork 仓库
2.  创建分支 (`git checkout -b my-new-feature`)
3.  提交修改 (`git commit -am 'Add some feature'`)
4.  推送 (`git push origin my-new-feature`)
5.  创建 PR

欢迎 fork 和反馈
-----------

如有建议或意见，欢迎在 github issues 区提问

协议
--

本仓库遵循 MIT 协议

有疑问？
----

可以通过sahadev@foxmail.com给我发送邮件，我会及时回复的。

或者加群和大家一起讨论吧! 可以加我微信：SAHADEV-smile，我拉你入群。加我微信时请备注 VCC。

另外我也特别希望可以和大家一起做这个项目。这个项目目前主要面对的是前端开发者。后期可以面向后端开发者与产品与 UE。
