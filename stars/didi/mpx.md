---
project: mpx
stars: 3783
description: Mpx，一款具有优秀开发体验和深度性能优化的增强型跨端小程序框架
url: https://github.com/didi/mpx
---

Mpx, 一款具有优秀开发体验和深度性能优化的增强型跨端小程序框架。

官网及文档
-----

欢迎访问https://mpxjs.cn，跟随我们提供的文档指南使用Mpx进行跨端小程序开发。

近期更新
----

基于 Mpx 的移动端基础组件库 mpx-cube-ui 已经开源，更多详情查看这里。

Mpx 2.9 版本正式发布，支持原子类、SSR和构建产物体积优化，更多详情查看这里，迁移指南查看这里，相关指南及 API 参考文档已更新。

简介
--

Mpx是一款致力于提升小程序开发体验和用户体验的增强型小程序跨端框架，通过Mpx，我们能够以类Vue的开发体验高效优雅地构筑出高性能跨端小程序应用，在所有开放的小程序平台及web平台中运行。

Mpx具有以下功能特性：

-   数据响应 (赋值响应 / watch / computed)
-   组合式 API
-   增强模板语法 (动态组件 / 样式绑定 / 类名绑定 / 内联事件函数 / 双向绑定 / refs)
-   极致性能 (运行时性能优化 / 包体积优化 / 框架运行时体积14KB)
-   高效强大的编译构建 (基于webpack5 / 支持持久化缓存 / 兼容webpack生态 / 兼容原生小程序 / 完善支持npm场景下的分包输出 / 高效调试)
-   单文件组件开发
-   渐进接入 / 原生组件支持
-   状态管理 (Vuex规范 / 支持多实例Store)
-   跨团队开发 (packages)
-   逻辑复用 (mixins)
-   周边能力 (fetch / api增强 / mock / webview-bridge)
-   脚手架支持
-   多平台增强 (支持在微信、支付宝、百度、qq、头条小程序平台中进行增强开发)
-   跨平台编译 (一套代码跨端输出到微信、支付宝、百度、字节、QQ、京东、快应用(web) 和 web平台 中运行)
-   TypeScript支持 (基于ThisType实现了完善的类型推导)
-   I18n国际化
-   单元测试
-   E2E测试
-   原子类
-   SSR
-   运行时渲染方案
-   跨端输出RN（即将到来）

快速开始
----

# 安装mpx脚手架工具
npm i -g @mpxjs/cli

# 初始化项目
mpx create mpx-project

# 进入项目目录
cd mpx-project

# 安装依赖
npm i

# development
npm run serve

# production
npm run build

使用小程序开发者工具打开项目文件夹下dist中对应平台的文件夹即可预览效果。

使用示例
----

<template\>
  <!--动态样式-->
  <view class\="container" wx:style\="{{dynamicStyle}}"\>
    <!--数据绑定-->
    <view class\="title"\>{{title}}</view\>
    <!--计算属性数据绑定-->
    <view class\="title"\>{{reversedTitle}}</view\>
    <view class\="list"\>
      <!--循环渲染，动态类名，事件处理内联传参-->
      <view wx:for\="{{list}}" wx:key\="id" class\="list-item" wx:class\="{{ {active:item.active} }}"
            bindtap\="handleTap(index)"\>
        <view\>{{item.content}}</view\>
        <!--循环内部双向数据绑定-->
        <input type\="text" wx:model\="{{list\[index\].content}}"/>
      </view\>
    </view\>
    <!--自定义组件获取实例，双向绑定，自定义双向绑定属性及事件-->
    <custom-input wx:ref\="ci" wx:model\="{{customInfo}}" wx:model-prop\="info" wx:model-event\="change"/>
    <!--动态组件，is传入组件名字符串，可使用的组件需要在json中注册，全局注册也生效-->
    <component is\="{{current}}"\></component\>
    <!--显示/隐藏dom-->
    <view class\="bottom" wx:show\="{{showBottom}}"\>
      <!--模板条件编译，\_\_mpx\_mode\_\_为框架注入的环境变量，条件判断为false的模板不会生成到dist-->
      <view wx:if\="{{\_\_mpx\_mode\_\_ === 'wx'}}"\>wx env</view\>
      <view wx:if\="{{\_\_mpx\_mode\_\_ === 'ali'}}"\>ali env</view\>
    </view\>
  </view\>
</template\>

<script\>
  import { createPage } from '@mpxjs/core'

  createPage({
    data: {
      // 动态样式和类名也可以使用computed返回
      dynamicStyle: {
        fontSize: '16px',
        color: 'red'
      },
      title: 'hello world',
      list: \[
        {
          content: '全军出击',
          id: 0,
          active: false
        },
        {
          content: '猥琐发育，别浪',
          id: 1,
          active: false
        }
      \],
      customInfo: {
        title: 'test',
        content: 'test content'
      },
      current: 'com-a',
      showBottom: false
    },
    computed: {
      reversedTitle () {
        return this.title.split('').reverse().join('')
      }
    },
    watch: {
      title: {
        handler (val, oldVal) {
          console.log(val, oldVal)
        },
        immediate: true
      }
    },
    handleTap (index) {
      // 处理函数直接通过参数获取当前点击的index，清晰简洁.
      this.list\[index\].active \= !this.list\[index\].active
    },
    onReady () {
      setTimeout(() \=> {
        // 更新数据，同时关联的计算属性reversedTitle也会更新
        this.title \= '你好，世界'
        // 此时动态组件会从com-a切换为com-b
        this.current \= 'com-b'
      }, 1000)
    }
  })
</script\>

<script type\="application/json"\>
  {
    "usingComponents": {
      "custom-input": "../components/custom-input",
      "com-a": "../components/com-a",
      "com-b": "../components/com-b"
    }
  }
</script\>

<style lang\="stylus"\>
  .container
    position absolute
    width 100%
</style\>

更多示例请查看官方示例项目

设计思路
----

Mpx的核心设计思路为增强，不同于业内大部分小程序框架将web MVVM框架迁移到小程序中运行的做法，Mpx以小程序原生的语法和技术能力为基础，借鉴参考了主流的web技术设计对其进行了扩展与增强，并在此技术上实现了以微信增强语法为base的同构跨平台输出，该设计带来的好处如下：

-   良好的开发体验：在方便使用框架提供的便捷特性的同时，也能享受到媲美原生开发的确定性和稳定性，完全没有`框架太多坑，不如用原生`的顾虑；不管是增强输出还是跨平台输出，最终的dist代码可读性极强，便于调试排查；
-   极致的性能：得益于增强的设计思路，Mpx框架在运行时不需要做太多封装抹平转换的工作，框架的运行时部分极为轻量简洁，压缩+gzip后仅占用14KB；配合编译构建进行的包体积优化和基于模板渲染函数进行的数据依赖跟踪，Mpx框架在性能方面做到了业内最优(小程序框架运行时性能评测报告)；
-   完整的原生兼容：同样得益于增强的设计思路，Mpx框架能够完整地兼容小程序原生技术规范，并且做到实时跟进。在Mpx项目中开发者可以方便地使用业内已有的小程序生态，如组件库、统计工具等；原生开发者们可以方便地进行渐进迁移；甚至可以将框架的跨平台编译能力应用在微信的原生小程序组件当中进行跨平台输出。

生态周边
----

包名

版本

描述

@mpxjs/core

mpx运行时核心

@mpxjs/webpack-plugin

mpx编译核心

@mpxjs/api-proxy

将各个平台的 api 进行转换，也可以将 api 转为 promise 格式

@mpxjs/store

类vuex store

@mpxjs/pinia

mpx pinia store

@mpxjs/fetch

mpx网络请求库，处理wx并发请求限制

@mpxjs/unocss-plugin

mpx unocss插件，支持使用unocss原子类

@mpxjs/unocss-base

mpx unocss预设

@mpxjs/cli

mpx脚手架命令行工具

@mpxjs/webview-bridge

为跨小程序平台的H5项目提供通用的webview-bridge

@mpxjs/utils

mpx运行时工具库

@mpxjs/babel-plugin-inject-page-events

组合式API页面事件处理插件

@mpxjs/mpx-cube-ui

基于 Mpx 的移动端基础组件库

开发团队
----

核心团队: hiyuki, Blackgan3, anotherso1a, CommanderXL, yandadaFreedom, wangxiaokou, OnlyProbie, pagnkelly, thuman, theniceangel, dolymood

外部贡献者：sky-admin, pkingwa, httpsxiao, lsycxyj, okxiaoliang4, tangminFE, codepan, zqjimlove, xuehebinglan, zhaoyiming0803, ctxrr, JanssenZhang, heiye9, lj0812, SuperHuangXu, twtylkmrh, NineSwordsMonster

成功案例
----

微信小程序

滴滴出行

出行广场

滴滴公交

滴滴金融

滴滴外卖

司机招募

小桔加油

彗星英语

番薯借阅

疫查查应用

小桔养车

学而思直播课

小猴启蒙课

科创书店

在武院

三股绳Lite

学而思优选课

食享会

青铜安全医生

青铜安全培训

视穹云机械

店有生意通

花小猪打车

橙心优选

小二押镖

顺鑫官方微商城

嘀嗒出行

汉行通Pro

交圈

青桔单车

滴滴顺风车

滴滴代驾

新桔代驾

标贝知音

其他平台小程序：

滴滴出行(支付宝)

小桔充电(支付宝)

唯品会(QQ)

口袋证件照(百度)

唯品会(百度)

唯品会(字节)

更多案例，若你也在使用Mpx框架开发小程序，并想分享给大家，请填在此issue中。

交流
--

提供 微信群 / QQ群 两种交流方式

#### 添加MPX入群小助手等待受邀入群

#### 扫码进入QQ群

图片因github网络问题导致不可见的朋友可以点击该链接：https://s.didi.cn/rod
