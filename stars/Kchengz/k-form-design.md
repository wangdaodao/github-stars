---
project: k-form-design
stars: 1238
description: 基于vue Ant-Design 的表单设计器，快速开发
url: https://github.com/Kchengz/k-form-design
---

表单设计器 k-form-design
===================

**感谢您的支持！由于已经将项目的重心转向 Vue 3 版本设计器，对于k-form-design项目决定暂停维护更新，欢迎您使用全新的 Vue3 版本设计器 epic-designer，以便享受到更多优化和功能！**

简介
--

基于vue和ant-design-vue实现的表单设计器，样式使用less作为开发语言，主要功能是能通过简单操作来生成配置表单，生成可保存的JSON数据，并能将JSON还原成表单，使表单开发更简单更快速

-   github
-   码云
-   项目预览
-   项目文档
-   项目文档(备用地址)

特性
--

-   可视化配置页面
-   提供栅格、表格等布局
-   布局嵌套使用
-   提供预览、保存、生成json、生成可执行代码等操作
-   支持表单验证
-   快速获取表单数据
-   自定义组件插入
-   自定义主题色

组件
--

-   KFormDesign 表单设计器（基于可视化操作快速设计出表单页面，生成配置json或页面）
-   KFormBuild 表单构建器（根据设计器中获取的配置json数据，快速构建出表单页面）

安装
--

> 安装表单设计器

npm i k-form-design --save
 
# OR
yarn add k-form-design

> 安装 ant-design-vue UI ，推荐 vue2 版本最新的 1.7.8版本

npm i ant-design-vue@1.7.8 --save

# OR
yarn add ant-design-vue@1.7.8

引入组件
----

// 在main.js引入

// 注：useComponents 需放最上面，优先注册懒加载组件
import { useAntd } from 'k-form-design/packages/core/useComponents'
import KFormDesign from 'k-form-design/packages/use.js'
import 'k-form-design/lib/k-form-design.css'

useAntd(Vue)
Vue.use(KFormDesign)

使用组件
----

<template\>
  <div\>
   <k-form-design />
  </div\>
</template\>

交流
--

点击链接加入qq群聊

-   【k-form-desgin交流群：1020643215】
-   【k-form-desgin交流二群：727396923】

License
-------

MIT Copyright (c) 2019 Kchengz
