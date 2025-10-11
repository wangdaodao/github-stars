---
project: quark-core
stars: 360
description: Open-source, Web Components engine designed for everyone.（用原生 JS 构建跨技术栈组件 / 无框架组件）
url: https://github.com/hellof2e/quark-core
---

Quarkc —— 无框架，跨框架！
------------------

简体中文 | English

介绍
--

Quarkc(Quark core缩写) 是一个拥有完美开发体验的 web components 工具（jsx + web components）。通过它，您可以开发 跨框架组件 或 独立页面。

特性
--

-   无框架，组件可以在任何框架或无框架的环境下使用，让你的代码更具复用性
-   产物体积极小，性能接近浏览器原生元素
-   Web Components, Simple, Fast！
-   浏览器原生API，组件可以跨技术栈使用
-   没有前端框架 Runtime，Web 组件体积小到极致
-   Shadow DOM 与 Virtual DOM 的完美融合
-   组件直接解耦，独立打磨，按需引用

使用
--

### 1、创建组件构建模版工程

创建模版

npm create quarkc@latest

启动工程

npm install
npm start

### 2、自定义你的 Custom Elements（组件/元素）

import { QuarkElement, property, customElement } from "quarkc"
import style from "./index.less?inline"

@customElement({ tag: "my-element", style }) // 自定义标签/组件、CSS
export default class MyElement extends QuarkElement {
  @property() // 外部属性
  count

  add \= () \=> {
    this.count += 1
  }

  render() {
    return (
      <button onClick\={this.add}\>count is: { this.count }</button\>
    )
  }
}

### 3、Build 打包

打包默认输出为 UMD / ESM 格式

npm run build

此时，构建产物 `lib/` 下的资源可以直接被任何框架的前端项目中使用。

### 4、使用

#### 场景1：含有工程管理的前端项目（含有package.json/node\_modules等文件）

import "./lib/your-element"

<my-element count\="count" />

// vue
// <my-element :count="count" />

// react
// <my-element count={count} />

// svelte
// <my-element {count} />

// angular
// <my-element \[count\]="count" />

#### 场景2：无工程管理的前端项目（不含有package.json/node\_modules等文件，纯HTML+CSS+JS文件）

单个 quarkc 组件，可以直接使用：

<!DOCTYPE html\>
<html lang\="en"\>
  <head\>
    <!-- 引用 npm run build 产物 -->
    <script type\="module" src\="./lib/index.mjs"\></script\>
  </head\>
  <body\>
    <my-element\></my-element\>
  </body\>
</html\>

多个 quarkc 组件同时加载，为了共用 quarkc 核心库，您可以选择开启了 `external`：

// vite.config.build.ts
export default defineConfig({
  build: {
    rollupOptions: {
+      external: \['quarkc'\],
    },
  },
});

然后，用下面方式单独加载 `quarkc` 核心库：

<!DOCTYPE html\>
<html lang\="en"\>
  <head\>
    <script type\="importmap"\>
      {
        "imports": {
          "quarkc": "https://unpkg.com/quarkc@latest/lib/index.browser.js"
        }
      }
    </script\>
    <!-- 引用 npm run build 产物 -->
    <!-- quarkc 构建的组件1 -->
    <script type\="module" src\="my-element1/lib/index.mjs"\></script\>
    <!-- quarkc 构建的组件2 -->
    <script type\="module" src\="my-element2/lib/index.mjs"\></script\>
  </head\>
  <body\>
    <!-- 使用 quarkc 元素/组件 -->
    <my-element1\></my-element1\>
    <my-element2\></my-element2\>
  </body\>
</html\>

文档
--

完整文档，请访问 https://quark-ecosystem.github.io/quarkc-docs

### 联系我们

添加微信：Sanqi9675

### 社区示例

作者

github 地址

截图 / 链接

@xsf0105

https://xsf0105.github.io/piano/

https://xsf0105.github.io/piano/

@xsf0105

https://github.com/xsf0105/dark-light-element

https://unpkg.com/dark-light-element@latest/demo.html

@hellof2e

https://github.com/hellof2e/quark-doc-header

https://quarkc.hellobike.com/#/

@yuhaiyang1

https://github.com/yuhaiyang1/quarkc-time

https://unpkg.com/quark-timer@0.0.2/demo.html

@dyf19118

https://github.com/dyf19118/quark-ui-rate

@hellof2e

https://github.com/hellof2e/quark-doc-home

@zhangfisher

https://github.com/zhangfisher/lite-tree/tree/master/packages/quark

点击查看

License
-------

MIT LICENSE
