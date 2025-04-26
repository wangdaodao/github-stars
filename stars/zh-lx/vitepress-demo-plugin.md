---
project: vitepress-demo-plugin
stars: 157
description: 🎨 A vitepress plugin to display and render code, support React/Vue/Html. 一个可以在 vitepress 中展示和渲染代码的插件，支持 Vue/React/Html.
url: https://github.com/zh-lx/vitepress-demo-plugin
---

vitepress-demo-plugin
---------------------

在线文档

* * *

📖 介绍
-----

`vitepress-demo-plugin` 是一个支持在 Vitepress 构建的站点中展示并预览代码 Demo 的插件，支持 `vue/react/html` 等多种语法组件的预览。

在线查看效果

-   展示 React 组件：
    
-   展示 Vue 组件：
    

🚀 安装
-----

npm i vitepress-demo-plugin -D
# or
yarn add vitepress-demo-plugin -D
# or
pnpm add vitepress-demo-plugin -D

🌈 使用
-----

1.  引入插件

import { defineConfig } from 'vitepress';
import { vitepressDemoPlugin } from 'vitepress-demo-plugin'; 
import path from 'path';

export default defineConfig({
  // other configs...
  markdown: { 
    config(md) { 
      md.use(vitepressDemoPlugin); 
    }, 
  }, 
});

1.  展示 Demo

现在你可以在 markdown 中通过 `<demo />` 组件展示你的 demo 了：

<!-- 展示 vue demo -->
<demo vue\="../demos/demo.vue" />

<!-- 展示 react demo -->
<demo react\="../demos/demo.tsx" />

<!-- 展示 html demo -->
<demo html\="../demos/demo.html" />

📧 交流与反馈
--------

任何使用问题可以加入微信群或者添加作者微信 `zhoulx1688888` 进行咨询与反馈:
