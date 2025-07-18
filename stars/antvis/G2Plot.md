---
project: G2Plot
stars: 2602
description: :dango:  An interactive and responsive charting library based on G2.
url: https://github.com/antvis/G2Plot
---

English | 简体中文

G2Plot
======

基于 G2 4.x 版本二次封装的图表库。

> 📢 新版本 G2 v5 已经发布，未来不会基于 G2 v5 封装 G2Plot v3 版本，但是可以使用 Ant Design Charts 代替。

网站 • 快速开始 • 博客 • AntV ThemeSet

一套简单、易用、并具备一定扩展能力和组合能力的统计图表库，基于图形语法理论搭建而成，『G2Plot』中的 G2 即意指图形语法 (the Grammar of Graphics)，同时也致敬了 ggplot2。我们想做的事有三件：

1.  使用户不用成为可视化专家也能够轻松制作出优雅美观的图表。
2.  保证图表能够经受得起业务的检验，在真实的场景中易用、好用。
3.  探索统计图表的更多可能性，使统计图表变得更好玩、更酷。

✨ 特性
----

### 📦 开箱即用、体验优雅的高质量统计图表

G2Plot 呈现给用户的是一套提炼自企业级产品的视觉语言和设计规范。不仅对图表的整体视觉样式进行了优化，并且针对每一个图表自身的特点，沉淀出一套最佳配置，保证用户能够通过最少的配置制作出优雅、标准的图表。

### 📊 响应式：让图表更聪明

在现实的图表应用场景中，一个棘手的难题是图表的展示空间往往并不足够显示图表的数据量，造成极值情况下文本的重叠遮挡、内容无法自适应、内容裁剪等问题。G2Plot 借鉴宽容性设计的思想，在图表的信息密度过高时，对图表辅助信息进行抽稀，保证图表主要信息的展示和基本可读性。

### 🔳 向前一步：会讲故事的图表

在 G2Plot 体系下，图表不仅仅只是各不相关的实例，图层概念的引入提供了多图表组合、叠加、联动，共同讲述一个数据故事的可能性。未来，我们还将探索统计图表转化信息图的可能性，丰富统计图表的表现能力。

📦 安装
-----

$ npm install @antv/g2plot

🔨 使用
-----

<div id\="container"\></div\>

import { Bar } from '@antv/g2plot';

const data \= \[
  { year: '1951 年', sales: 38 },
  { year: '1952 年', sales: 52 },
  { year: '1956 年', sales: 61 },
  { year: '1957 年', sales: 145 },
  { year: '1958 年', sales: 48 },
\];

const bar \= new Bar('container', {
  data,
  xField: 'sales',
  yField: 'year',
  seriesField: 'year',
});

bar.render();

🤝 参与贡献
-------

我们非常欢迎你的贡献！无论是 issue 还是 PR。

反馈问题请先阅读 issues。

提交代码请遵循 贡献指引。

感谢下面这些贡献者 (emoji key):

  
**Visiky**  
💻

  
**hustcc**  
💻

  
**Joel Alan**  
💻

  
**刘珍莹**  
💻

  
**zqlu**  
💻

  
**arcsin1**  
💻

  
**被雨水过滤的空气**  
💻

  
**banli**  
💻

  
**xi li**  
💻

  
**DarrenPei**  
💻

  
**MiniPear**  
💻

  
**connono**  
💻

  
**于向前**  
💻

  
**afc163**  
💻

  
**Martin Jul**  
💻

  
**jhwong**  
💻

  
**Jingsong Gao**  
💻

  
**Mr小刘**  
💻

  
**ntscshen**  
💻

  
**yiminanci**  
💻

  
**ai-qing-hai**  
💻

  
**xrkffgg**  
💻

  
**Dawnlck**  
💻

  
**Karis**  
💻

  
**Mayne**  
💻

  
**Plortinus**  
💻

  
**Shanjie Chen**  
💻

  
**Yang Libin**  
💻

  
**beewolf233**  
💻

  
**lqzhgood**  
💻

  
**neoddish**  
💻

  
**stack-stark**  
💻

  
**vector**  
💻

  
**嘤嘤嘤**  
💻

  
**琚致远**  
💻

  
**14**  
💻

🔗 相关链接
-------

ChartCube - 基于 G2Plot 的在线图表制作工具，交互简单，一键导出图表代码！

许可证
---

MIT
