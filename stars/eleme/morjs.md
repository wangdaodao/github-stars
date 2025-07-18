---
project: morjs
stars: 1976
description: 基于小程序 DSL（微信、支付宝）的，可扩展的多端研发框架，支持一键将微信或支付宝小程序转换为微信、支付宝、百度、字节、QQ、快手、淘宝、钉钉等小程序 或 Web 应用。
url: https://github.com/eleme/morjs
---

MorJS
=====

Mor (发音为 /mɔːr/，类似 more)，是饿了么开发的一款基于小程序 DSL 的，可扩展的多端研发框架，使用小程序原生 DSL 构建，使用者只需书写一套（微信或支付宝）小程序，就可以通过 Mor 的转端编译能力，将源码分别编译出可以在不同端（微信/支付宝/百度/字节/钉钉/快手/QQ/淘宝/Web…）运行的产物。

MorJS 以多端编译为基础，配以面向全生命周期的插件体系，覆盖从源码到构建产物的每个阶段，支持各类功能扩展和业务需求，无论是基础的页面和组件还是复杂的分包和插件，MorJS 都可以胜任，帮助你高效地开发多端小程序。

### 📚 快速上手 MorJS →

优势与核心能力
-------

Mor 是一套基于小程序 DSL (支付宝或微信) 的框架。他的易用性、标准化和灵活性，使得开发者能更好地专注于业务，让开发成本，招聘、管理、测试各方面成本都大幅下降，提高开发者的工作效率。

-   ⭐️ **易用性**：
    -   💎 **DSL 支持**：可使用微信小程序 DSL 或 支付宝小程序 DSL 编写小程序，无额外使用成本；
    -   🌴 **多端支持**：支持将一套小程序转换为各类小程序平台及 Web 应用, 节省双倍人力；
    -   🚀 **快速接入**：仅需引入两个包，增加一个配置文件，即可简单快速接入到现有小程序项目；
-   🌟 **标准化**：
    -   📦 **开箱即用**：内置了脚手架、构建、分析、多端编译等完整研发能力，仅需一个依赖即可上手开发；
    -   🌈 **表现一致**：通过编译时+运行时抹平多端差异性，让不同平台的小程序获得一致的用户体验；
    -   🖇 **形态转换**：支持同一个项目的不同的形态，允许小程序、分包、插件不同形态之间的相互转换；
-   ✨ **灵活性**：
    -   🎉 **方便扩展**：Mor 将完备的生命周期和内部功能插件化，使用插件(集)以满足功能和垂直域的分层需求；
    -   📚 **类型支持**：除小程序标准文件类型外，还支持 ts、less/scss、jsonc/json5 等多种文件类型；
    -   🧰 **按需适配**：可根据需求选择性接入适配能力，小项目仅需编译功能，中等项目可结合编译和页面注入能力，大型项目推荐使用复杂小程序集成能力；

示例
--

以下是饿了么-美食外卖频道在微信、支付宝、抖音小程序及 H5 中的表现。

部分使用案例
------

贡献
--

参见 参与贡献

社区
--

参见 社区指南

### 核心成员

核心成员是在 MorJS 相关问题、BUG 修复、功能增强、新特性添加等方便投入大量的时间和精力的社区贡献者。

-   lyfeyaj
-   BboyZaki
-   hwaphon
-   shujian-cao
-   robin-shine
-   aboyforwind

许可证
---

MIT
