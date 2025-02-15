---
project: v-track
stars: 344
description: 🕹 A manual tracking decoupling plugin based on Vue directive / 一个基于Vue指令实现的埋点解耦插件~
url: https://github.com/l-hammer/v-track
---

v-track
=======

v-track通过 Vue 自定义指令的方式将埋点代码与业务代码完全解耦~

安装
--

### YARN

$ yarn add v-track

### NPM

$ npm install v-track --save

### CDN

目前可以通过unpkg.com/v-track获取到最新版本的资源，在页面上使用 script 标签直接引入文件即可开始使用

<script src\="https://unpkg.com/v-track/dist/v-track.min.js"\></script\>

或者

<script src\="https://cdn.jsdelivr.net/npm/v-track/dist/v-track.min.js"\></script\>

> 建议使用 CDN 引入 v-track 的用户在链接地址上锁定版本，以免将来 v-track 升级时受到非兼容性更新的影响。锁定版本的方法请查看 unpkg.com or jsdelivr.com。

用法
--

import Vue from "vue"
import VTrack from "v-track"
import trackEvents from "./track-events"

Vue.use(VTrack, {
  trackEvents, // 埋点事件对象
  trackEnable: {
    UVPV: true, // 是否开启UVPV统计，v0.8.3新增routeUpdate，即在当前路由参数发生改变时埋点，默认为false
    TONP: true // 是否开启页面停留时长统计，默认为false
  }
})

/\* track-events.js \*/
export default {
  /\*\*
   \* @name UVPV 固定名称不支持修改
   \* @desc UV、PV埋点
   \* @param {Object} context 当前上下文
   \*/
  UVPV(context) {
    ...
  },
  /\*\*
   \* @name TONP 固定名称不支持修改
   \* @desc 页面停留时间埋点（Time on Page）
   \* @param {Object} context 当前上下文
   \* @param {Timestamp} et 进入页面时间
   \* @param {Timestamp} dt 离开页面时间
   \*/
  TONP(context, { et, dt }) {
    ...
  },
  /\*\*
   \* @name 18015 埋点唯一标识ID（自定义）
   \* @param {Object} context 当前上下文
   \* @param {Object} args 剩余参数
   \*/
  18015(context, args) {
    ...
  }
  ...
}

<!-- 页面行为埋点（track-view为v-track全局注册的组件） -->
<track-view v-track:18015\></track-view\>
<track-view v-track:18015.watch\="{ rest }"\></track-view\>
<track-view v-track:18015.watch.delay\="{ rest }"\></track-view\>
<track-view v-if\="rest" v-track:18015\></track-view\>

<!-- 事件行为埋点（DOM） -->
<div v-track:18015.click\="handleClick"\></div\>
<div v-track:18015.click\="{ handleClick, item, index }"\></div\>
<div v-track:18015.click.async\="{ handleSearch, rest }"\></div\>
<div v-track:18015.click.delay\="handleClick"\></div\>

<!-- 事件行为埋点（组件） -->
<cmp v-track:18015.click\="handleClick"\></cmp\>
<cmp v-track:18015.\[自定义事件名\]\="handleSearch"\></cmp\>
<cmp v-track:18015.\[自定义事件名\].delay\="handleSearch"\></cmp\>
<cmp v-track:18015.\[自定义事件名\].async\="{ handleSearch, rest }"\></cmp\>

<!-- 区域展现埋点（block 可以是 DOM 或者组件） -->
<block v-track:18015.show\></block\>
<block v-track:18015.show.once\></block\>
<block v-track:18015.show.custom\="{ ref: 'scroll' }"\></block\>
<block v-track:18015.show.custom.once\="{ ref: 'scroll' }"\></block\>

指令修饰符
-----

-   `.click` 表示事件行为的埋点
-   `.[custom-event]` 表示自定义事件行为的埋点
-   `.native` 表示监听组件原生click事件行为的埋点
-   `.watch` 表示页面异步行为的埋点
-   `.async` 配合`.click`指令，表示异步事件行为的埋点
-   `.delay` 表示埋点是否延迟执行，默认先执行埋点再执行回调
-   `.show` 表示区域曝光埋点
-   `.once` 配合`.show`指令，只执行一次埋点
-   `.custom` 配合`.show`指令，表示使用自定义scroll事件

LICENSE
-------

MIT © 2019-present, LHammer
