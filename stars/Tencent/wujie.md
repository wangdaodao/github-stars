---
project: wujie
stars: 4741
description: 极致的微前端框架
url: https://github.com/Tencent/wujie
---

wujie（无界）
=========

无界微前端是一款基于 Web Components + iframe 微前端框架，具备成本低、速度快、原生隔离、功能强等一系列优点。

文档
--

动机：动机

文档详见：文档

演示详见：demo

背景
--

微前端已经是一个非常成熟的领域了，但开发者不管采用哪个现有方案，在适配成本、样式隔离、运行性能、页面白屏、子应用通信、子应用保活、多应用激活、vite 框架支持、应用共享等用户核心诉求都或存在问题、或无法提供支持。

Web Components 是一个浏览器原生支持的组件封装技术，可以有效隔离元素之间的样式，iframe 可以给子应用提供一个原生隔离的运行环境，相比自行构造的沙箱 iframe 提供了独立的 window、document、history、location，可以更好的和外部解耦。无界微前端采用 webcomponent + iframe 的沙箱模式，在实现原生隔离的前提下比较完善的解决了上述问题。

特性
--

1.  成本低
    -   主应用使用成本低
    -   子应用适配成本低
2.  速度快
    -   子应用首屏打开速度快
    -   子应用运行速度快
3.  原生隔离
    -   css 样式通过 Web Components 可以做到严格的原生隔离
    -   js 运行在 iframe 中做到严格的原生隔离
4.  功能强大
    -   支持子应用保活
    -   支持子应用嵌套
    -   支持多应用激活
    -   支持应用共享
    -   支持去中心化通信
    -   支持生命周期钩子
    -   支持插件系统
    -   支持 vite 框架

快速上手
----

### 直接使用

-   安装

npm install wujie -S

-   使用

import { startApp } from "wujie";

startApp({ name: "唯一id", url: "子应用路径", el: "容器", sync: true });

### vue 框架

-   安装

# vue2 框架
npm i wujie-vue2 -S
# vue3 框架
npm i wujie-vue3 -S

-   引入

// vue2
import WujieVue from "wujie-vue2";
Vue.use(WujieVue);
// vue3
import WujieVue from "wujie-vue3";
app.use(WujieVue);

-   使用

<WujieVue
  width\="100%"
  height\="100%"
  name\="xxx"
  :url\="xxx"
  :sync\="true"
  :fetch\="fetch"
  :props\="props"
  :beforeLoad\="beforeLoad"
  :beforeMount\="beforeMount"
  :afterMount\="afterMount"
  :beforeUnmount\="beforeUnmount"
  :afterUnmount\="afterUnmount"
\></WujieVue\>

### react 框架

-   安装

npm i wujie-react -S

-   引入

import WujieReact from "wujie-react";

-   使用

<WujieReact
  width\="100%"
  height\="100%"
  name\="xxx"
  url\="{xxx}"
  sync\="{true}"
  fetch\="{fetch}"
  props\="{props}"
  beforeLoad\="{beforeLoad}"
  beforeMount\="{beforeMount}"
  afterMount\="{afterMount}"
  beforeUnmount\="{beforeUnmount}"
  afterUnmount\="{afterUnmount}"
\></WujieReact\>

常见问题
----

详见文档

本地开发
----

运行以下脚本，可以本地开发无界微前端框架，支持实时编译调试开发。

nvm use v14.20.0         // 切换node版本到14版本，因为有些demo的node版本比较低
pnpm i                  // 安装包依赖，务必使用pnpm
npm run start           // 启动所有应用

One more thing
--------------

无界微前端解决方案来源于团队的**无极低代码平台**。无极是专注于高效实现企业B端应用、专业的一站式低代码解决方案，是腾讯内部应用最广泛的低代码平台，360度覆盖全企业应用场景。通过无界微前端，存量页面和低代码页面可以丝滑的互相内嵌，闭环新老系统的连接。欢迎体验【腾讯无极低代码】，感受智能而高效的研发模式！
