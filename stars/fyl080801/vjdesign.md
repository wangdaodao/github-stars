---
project: vjdesign
stars: 596
description: Vue 界面可视化设计器，支持任何 html 标签以及项目中引用的组件，可实现仅通过配置文件就能增加支持的组件和组件属性
url: https://github.com/fyl080801/vjdesign
---

Vue Json Design
===============

Vue 界面可视化设计器，基于 vjform

本设计器特色功能就是可以支持任何 vue 项目中被引用的组件，不需要二次开发就可以定义支持的组件以及组件的属性，并且对组件的属性和数据的关系以及表单的交互行为也可以通过设计器配置实现

特性
--

-   可视化拖拽布局
-   支持任何 html 元素和 vue 项目中引用的组件
-   支持数据关联和交互行为的编辑
-   通过 json 格式数据就可扩展编辑器支持的组件和属性
-   组件在设计器上呈现形式和属性编辑器支持二次开发

Getting Start
-------------

### 运行项目

克隆项目，执行

npm install

之后

npm run dev

### 使用 npm 包

npm i vjdesign

import Vue from 'vue'
import vjdesign from 'vjdesign'
import 'vjdesign/dist/vjdesign.css'

Vue.use(vjdesign)

相关链接
----

在线示例 已追加导出功能，速度慢可访问 国内环境

使用文档 完善中...

动态表单呈现 jformer

> 使用 `jformer` 组件可直接用设计器元数据中的 json 定义来呈现界面

动态表单呈现 vjform

> 如果使用 `vjform` 作为呈现组件，则需要在 vjform 中引用 表达式支持库、vue 作用域转换、设计器编辑转换

import vjform from 'vjform'
import expression from 'jpresent-transform-expression'

vjform.use(expression)

依赖
--

### vjform 以及相关库

-   vjform

可视化布局基于 vjform 扩展

-   jpresent-transform-modern

基于属性名的简易转换模板 `"$:text": "model.text1"`

-   jpresent-transform-expression

为了适应类似 excel 的习惯，将属性值是表达式的情况下直接作为转换来处理 `"text": "$:model.text"`

-   jpresent-vue-extends

使组件支持设置 scopedSlot 属性，实现转换获取父级组件 scopedSlot 的作用域对象

### Lodash

使用了 `get` `set` `forEach` 等 API

### Vue

基于 `v2.5.9` 测试，理论上支持高于 `v2.4.0` 版本

### vuedraggable

实现拖拽布局

### codemirror

实现直接编辑配置数据
