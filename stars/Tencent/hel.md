---
project: hel
stars: 1087
description: A module federation SDK which is unrelated to tool chain for module consumer. 工具链无关的运行时模块联邦sdk.
url: https://github.com/Tencent/hel
---

简体中文 | English

Doc
---

**hel-micro**, 模块联邦 sdk 化，免构建、热更新、工具链无关的微模块方案 ❤️

see doc： https://helmicro.com or https://tencent.github.io/hel

文章
--

1.  hel-micro 模块联邦新革命
    
2.  使用 hel-micro 制作远程 antd、tdesign-react
    

视频
--

1.  【视频教程第一期】基于 hel-micro 开发、发布、使用远程 js 库
2.  【视频教程第二期】本地联调基于 hel-micro 开发的远程 js 库

模板
--

用户可参考模块开发教程，并基于hel-eco提供的各种模板项目做轻微调整，即可发布各种类型的 hel 远程模块

示例名称/功能

在线示例

模板地址

模板描述

托管位置

远程 ts 库

预加载+静态导入

remote-lib-ts

webpack 开发与打包

unpkg

远程 react js 组件

预加载+静态导入

懒加载 shadow

remote-react-comp

webpack 开发与打包

unpkg

远程 react ts 组件

懒加载 shadow

remote-react-comp-ts

webpack 开发与打包

unpkg

远程 vue2 js 组件

预加载+静态导入

懒加载

remote-vue-comp

webpack 开发与打包

unpkg、

github.io index.html、

unpkg index.html

远程 vue3 ts 组件

预加载

remote-vue3-comps-ts

vite 或 webpack 开发，webpack 打包

unpkg

远程 vue3 ts 组件

预加载

hel-tpl-remote-vue3-comps-vite

vite 开发与打包

unpkg index.html

实战
--

基于模板项目改造后发布的 hel 远程模块

模块名称/功能

在线演示

仓库地址

描述

托管位置

hel-lodash

codesandbox

gihub

lodash 远程包

unpkg

hel-antd

codesandbox

gihub

antd 远程包

unpkg

hel-tdesign-react

codesandbox

gihub

tdesign-react 远程包

unpkg

Why hel-micro
-------------

接入快、0 入侵、简单易用：

让模块联邦技术从构建工具插件层面提升到 sdk 层面，使用更灵活，模块流通性更好（工具链无关）：

### 如何使用远程模块

仅需要一句 npm 命令即可载入远程模块，查看下面例子线上示例

-   1 安装`hel-micro`

npm i hel-micro

-   2 惰性加载远程模块

示例：调用`hel-lodash` 模块的方法

import { preFetchLib } from 'hel-micro';
async function ran(seed) {
  const mod \= await preFetchLib('hel-lodash'); // 首次加载触发模块下载，之后会从hel-micro缓存获取
  const num \= mod.myUtils.num.random(500);
  return num;
}

-   3 预加载远程模块

示例：静态导入`hel-lodash`后调用其模块方法

安装`hel-lodash`

npm i hel-lodash

先执行模块拉取动作

import { preFetchLib } from 'hel-micro';

async function main() {
  await preFetchLib('hel-lodash');
  await import('./loadApp'); // 入口文件后移
}

main().catch(console.error);

在入口文件里关联的任意文件处静态导入`hel-micro`并调用模块方法

import m from 'hel-lodash';
console.log(m.myUtils.num.random(500);) // 获得随机数

hel-micro
---------

前端微件化 sdk，基于 hel-micro 可实现跨项目共享代码、模块热更新、微前端架构等功能

hel-micro-react
---------------

依赖 hel-micro 基础 api 实现的 react 组件加载库

🐚 谁在使用
-------

欢迎在此issue里提供你的公司 logo，公司名，截图、站点等信息，提供给其他用户一些参考信息，让未来有更多的人参与到 hel-micro 的建设与使用中。

  
**腾讯云**

  
**腾讯音乐**

  
**腾讯文档**

  
**腾讯新闻**

  
**腾讯自选股**

📦 了解更多
-------

欢迎入群了解更多，由于微信讨论群号 200 人已满，需加作者微信号或 qq 群号，再邀请你如`hel-micro`讨论群（加号时记得备注 hel 哦）

👅License
---------

hel-micro is released under the MIT License. http://www.opensource.org/licenses/mit-license
