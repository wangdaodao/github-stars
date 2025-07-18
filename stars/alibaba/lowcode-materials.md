---
project: lowcode-materials
stars: 348
description: An enterprise-class low-code technology stack with scale-out design / 一套面向扩展设计的企业级低代码技术体系
url: https://github.com/alibaba/lowcode-materials
---

Lowcode Materials
=================

基于 Fusion Design 和 Ant Design 设计规范的低代码基础物料库

介绍 / Introduce
--------------

物料（Material）是指能够被沉淀下来的前端能力，一般表现为组件、区块和模板。而低代码物料库，则是一套专门用于低代码开发模式（Lowcode）的物料，它除了包含物料组件，还有一套描述组件信息的低代码引擎物料协议。简单来说，低代码物料库包含了两个部分：

-   组件的实现，即组件的代码和样式
-   遵循《低代码引擎物料协议规范》的物料协议

低代码物料应该配合低代码引擎使用，如果你还不了解低代码引擎，请先阅读相关文档。

在使用中遇到的任何问题，请在lowcode-engine项目中反馈。

Fusion Design For Lowcode
-------------------------

### 在线示例 / DEMO

### 使用 / Usage

#### NPM

const { material } from '@alilc/lowcode-engine';
const assets \= require('@alilc/lowcode-materials/dist/assets.json');

// in GeneralWorkbench init
material.setAssets(assets);

#### CDN

// in GeneralWorkbench init
const assets \= await fetch(
  \`https://alifd.alicdn.com/npm/@alilc/lowcode-materials@1.2.1/dist/assets.json\`,
).then((res) \=> res.json());
material.setAssets(assets);

Ant Design For Lowcode
----------------------

### 在线示例 / DEMO

### 使用 / Usage

#### NPM

const { material } from '@alilc/lowcode-engine';
const assets \= require('@alilc/antd-lowcode-materials/build/lowcode/assets-prod.json');

// in GeneralWorkbench init
material.setAssets(assets);

#### CDN

// in GeneralWorkbench init
const assets \= await fetch(
  \`https://alifd.alicdn.com/npm/@alilc/antd-lowcode-materials@1.2.2/build/lowcode/assets-prod.json\`,
).then((res) \=> res.json());
material.setAssets(assets);

如何贡献 / How-to-contribute
------------------------

### 目录结构 / Structure

```
|-packages
    |-{package-name} // fusion 或 antd 低代码组件包
        |-lowcode // 组件低代码描述文件
            |-{component-name}
                |-meta.ts // 组件低代码描述协议
                |-meta.design.ts // 【可选】面向设计者的组件低代码描述，移除面向研发的高级配置能力，可做静态搭建和简单的交互
        |-src
            |-index.tsx // 组件库导出文件
            |-components // 组件库源码
                |-{component-name}
                |-index.tsx
                |-index.scss
    |-build.lowcode.js // 低代码调试和构建使用的配置文件
    |-build.json // 源码调试和构建使用的配置文件
```

### 常用命令 / Commands

#### 低代码 / LowCode

cd packages/fusion-lowcode-materilas
# OR \`cd packages/antd-lowcode-materilas\`
npm run lowcode:dev
npm run lowcode:build

#### 源码 / ProCode

npm start
npm run build

#### 其他命令 / Other Commands

# 更新 README 中的版本号
npm run update-readme

### 贡献者 / Contributors

因无法保留开源前的提交记录，这里列出开源前的贡献者（花名）：

@荣彬 @度城 @屹凡 @启剑 @春希 @梧忌 @褚天 @莫夭 @金禅 @默吉 @旅途 @斩鲌 @永元 @听鸿 @晓吉 @与白 @若泉 @独寒 @尤恩 @馨焱
