---
project: right-menu
stars: 396
description: 📜 @right-menu 是一个使用 TypeScript 开发的右键菜单插件, 🏆 可以在 JS / TS / Vue / React 等多端框架使用, 🦄 支持多级菜单 / 异步渲染 / 骨架Loading / 自适应主题 / mac黑夜模式
url: https://github.com/buuing/right-menu
---

@right-menu
===========

一个支持 JS / TS / Vue / React 等多端框架的右键菜单插件

适配框架

最新版本

NPM 下载量

CDN 使用量

**JS / TS**

**Vue**

**React**

  

文档 - Docs
---------

-   官方文档 - 首页

  

使用 Usage
--------

-   在 JS / TS 中使用
-   在 Vue 中使用
-   在 React 中使用

  

贡献者
---

-   **🤖 `核心开发`：** 实现了某个重要的功能 / 核心逻辑, 或者是提交过多次PR
-   **🦄 `逻辑优化`：** 优化了某处逻辑问题, 对代码的性能做出了贡献
-   **🛰 `基础建设`：** 完善项目的打包发布流程, 优化了一些项目构建相关
-   **🚧 `需求功能`：** 参与项目的需求开发, 提交PR完成合并
-   **🛠 `修复bug`：** 修复了某个可能会导致代码运行的漏洞
-   **📚 `维护文档`：** 参与了文档的开发 / 维护 / 翻译

🤖 🛰 📚

🤖 🛰 🚧

🤖 🛰

🤖 🛠

🤖 🛰 🛠

🚧

  

需求计划
----

-   `💡 待认领`
    -   🛠 **在mac系统下, 第二次点击控制台时 blur 事件没有触发**
    -   🚧 增加icon选项, 可以使用一些内置图标, 或让用户自由使用外部的svg图标

  

历史功能更新记录
--------

-   增加`@right-menu/vue`的包, 并支持`vue2/3` - _buuing_
-   点击非窗口区域时, 看看能不能监听到然后关闭菜单 - _buuing_
-   支持`new RightMenu('#box', async () => [])`异步返回菜单数据 - _buuing_
-   菜单的宽度根据文字长度做到自适应 - _buuing_
-   增加`class`和`style`选项, 可以给当前标签添加类和样式 - _buuing_
-   增加不同的主题样式: mac / win10 - _buuing_
-   自动根据操作系统切换主题, 并做到自适应`mac`的白天/黑夜模式 - _qingtiantongxie_
-   异步等待期间增加菜单骨架来作为缓冲, 减少用户等待的焦虑 - _qingtiantongxie_
-   增加了三级菜单 / 多级菜单的逻辑处理, 并自动计算剩余位置来切换渲染方向 - _yushen7_
-   增加了 minWidth / maxWidth 最大最小宽度的配置 - _buuing_
-   `core`包增加`eslint-standard`规范, 保存时校验 - _dora1995_
-   增加`@right-menu/react`包, 支持`react-dom`方式使用 - _Deja-vuuu_
-   增加`@right-menu/react`包的 hooks 使用方式 - _pingxinwen_
-   增加`@right-menu/vue`包的 抽象组件 使用方式 - _buuing_

  

友情链接
----

-   🎁 lucky-canvas 一个跨平台、兼容多端的【大转盘 / 九宫格 / 老虎机】抽奖插件
