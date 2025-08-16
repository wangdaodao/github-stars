---
project: lowcode-engine-vue
stars: 381
description: Lowcode engine renderer and simulator for vue
url: https://github.com/KNXCloud/lowcode-engine-vue
---

lowcode-engine-vue
==================

Lowcode Engine Vue 渲染器及适配器实现，点击查看在线演示

> PS: 该项目仅包含画布实现，不能直接运行，如果需要本地查看效果请访问 DEMO 仓库

如何自定义组件
-------

我们提供了 `npm init @knxcloud/lowcode@latest` 命令用于初始化一个基础的低代码组件项目，该项目基于 `vue-cli` 构建。项目启动后，会生成一个 `/assets.json` 文件，该文件可直接作为低代码物料的导入入口，部分代码示例如下：

const editorInit \= (ctx: ILowCodePluginContext) \=> {
  return {
    name: 'editor-init',
    async init() {
      const { material, project } \= ctx;
      const assets \= await fetch('http://127.0.0.1:9000/assets.json').then((res) \=>
        res.json(),
      );
      material.setAssets(assets);
    },
  };
};

和 React 渲染器使用区别
---------------

使用变量时：

-   `this.props.xxx` -> `this.xxx`
-   `this.state.xxx` -> `this.xxx`

若直接使用 react 代码编辑器编辑代码，渲染器已做适配：

-   state 内容会自动转化为 vue data
-   lifecycle 自动适配为 vue lifecycle
    -   `componentDidMount` -> `onMounted`
    -   `componentDidCatch` -> `onErrorCaptured`
    -   `shouldComponentUpdate` -> `onBeforeUpdate`
    -   `componentWillUnmount` -> `onBeforeUnmount`
-   其余方法自动转化为 vue methods

appHelper 暴露给 `this` 的属性都会加上 `$` 前缀，区别于其他属性，如

-   `utils` -> `this.$utils`
-   `constants` -> `this.$constants`

Vue 代码编辑器
---------

现已支持 Vue 代码编辑器 @knxcloud/lowcode-plugin-vue-code-editor，支持情况如下

-   ESModule
    -   import (assets 加载的包，可以使用 `import` 语法导入)
    -   export default (必须导出一个组件)
    -   export
-   data
-   props
-   emits
-   computed
-   watch
-   provide
-   inject
-   setup
    -   async setup
    -   return void
    -   return object
    -   return function
-   beforeCreate
-   created
-   beforeMount
-   mounted
-   beforeUpdate
-   updated
-   beforeUnmount
-   unmounted
-   activated
-   deactivated
-   errorCaptured
-   renderTracked
-   renderTriggered
-   beforeRouteEnter
-   beforeRouteUpdate
-   beforeRouteLeave

对于 v-model 的适配：

在 assets 中使用 name 为 `v-model` 或 `v-model:xxx` 的属性会被作为双向绑定特性编译，编译的逻辑为

```
v-model -> modelValue prop + onUpdate:modelValue event
v-model:xxx -> xxx prop + onUpdate:xxx event
```

### VueRouter

若使用了 `beforeRouteEnter`、`beforeRouteUpdate`、`beforeRouteLeave` 钩子，则渲染器在使用时，必须作为 VueRouter 页面使用，使用示例

// router.ts
import { createRouter, createWebHistory } from 'vue-router'
import VueRenderer, {
  LOWCODE\_ROUTE\_META,
  setupLowCodeRouteGuard,
} from '@knxcloud/lowcode-vue-renderer'

const schema \= {} // 低代码设计器导出的页面 schema
const components \= {} // 组件映射关系对象

const router \= createRouter({
  history: createWebHistory('/'),
  routes: \[
    {
      name: 'lowcode-page'
      path: '/lowcode-page-path',
      component: VueRenderer,
      meta: {
        \[LOWCODE\_ROUTE\_META\]: schema,
      },
      props: {
        schema: schema，
        components: components,
      }
    }
  \]
})

setupLowCodeRouteGuard(router)

export default router;

### async setup & init dataSource

若使用了 `async setup` 或者 `init dataSource`，则需要在渲染器组件外部包裹 `Suspense` 组件，使用方式参考 Suspense

画布使用示例
------

import { init, project } from '@alilc/lowcode-engine';
import { setupHostEnvironment } from '@knxcloud/lowcode-utils';

setupHostEnvironment(project, 'https://unpkg.com/vue@3.2.47/dist/vue.runtime.global.js');

init(document.getElementById('lce'), {
  // ...
  simulatorUrl: \[
    'https://unpkg.com/@knxcloud/lowcode-vue-simulator-renderer/dist/vue-simulator-renderer.js',
    'https://unpkg.com/@knxcloud/lowcode-vue-simulator-renderer/dist/vue-simulator-renderer.css',
  \],
});

> 当不指定版本号时，默认使用最新版，推荐在 cdn 链接上添加适配器具体版本号

本地调试
----

git clone git@github.com:KNXCloud/lowcode-engine-vue.git
cd lowcode-engine-vue
pnpm install && pnpm -r build
pnpm start

项目启动后，提供了 umd 文件，可以结合 DEMO 项目做调试，文件代理推荐XSwitch, 规则参考:

{
  "proxy": \[
    \[
      "(?:.\*)unpkg.com/@knxcloud/lowcode-vue-simulator-renderer(?:.\*)/dist/(.\*)",
      "http://localhost:5559/$1"
    \],
  \]
}

技术交流
----

微信搜索: cjf395782896，加好友&备注：低代码引擎，申请入群
