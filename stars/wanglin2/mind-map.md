---
project: mind-map
stars: 6753
description: 一个还算强大的Web思维导图。A relatively powerful web mind map.
url: https://github.com/wanglin2/mind-map
---

Simple mind map
===============

> 中文名：思绪思维导图。一个简单&强大的 Web 思维导图。

本项目包含两部分：

1.一个 js 思维导图库，不依赖任何框架，可以使用它来快速完成 Web 思维导图产品的开发。

开发文档：https://wanglin2.github.io/mind-map-docs/。

2.一个 Web 思维导图，基于思维导图库、Vue2.x、ElementUI 开发，可以操作电脑本地文件，可以当做一个在线版思维导图应用使用，也可以自部署和二次开发。

在线地址：https://wanglin2.github.io/mind-map/。

此外也提供了客户端可供下载使用，支持`Windows`、`Mac`及`Linux`，下载地址：

Github：releases。百度云盘：地址。

> 客户端版本会落后于在线版本，尝试最新功能请优先使用在线版。

【云存储版本】如果你需要带后端的云存储版本，可以尝试我们开发的另一个项目理想文档。

特性
==

-   插件化架构，除核心功能外，其他功能作为插件提供，按需使用，减小打包体积
-   支持逻辑结构图（向左、向右逻辑结构图）、思维导图、组织结构图、目录组织图、时间轴（横向、竖向）、鱼骨图等结构
-   内置多种主题，允许高度自定义样式，支持注册新主题
-   节点内容支持文本（普通文本、富文本）、图片、图标、超链接、备注、标签、概要、数学公式
-   节点支持拖拽（拖拽移动、自由调整）、多种节点形状；支持扩展节点内容、支持使用 DDM 完全自定义节点内容
-   支持画布拖动、缩放
-   支持鼠标按键拖动选择和 Ctrl+左键两种多选节点方式
-   支持导出为`json`、`png`、`svg`、`pdf`、`markdown`、`xmind`、`txt`，支持从`json`、`xmind`、`markdown`导入
-   支持快捷键、前进后退、关联线、搜索替换、小地图、水印、滚动条、手绘风格、彩虹线条、标记、外框
-   提供丰富的配置，满足各种场景各种使用习惯
-   支持协同编辑
-   支持演示模式

官方提供了如下插件，可根据需求按需引入（某个功能不生效大概率是因为你没有引入对应的插件），具体使用方式请查看文档：

> RichText（节点富文本插件）、Select（鼠标多选节点插件）、Drag（节点拖拽插件）、AssociativeLine（关联线插件）、Export（导出插件）、KeyboardNavigation（键盘导航插件）、MiniMap（小地图插件）、Watermark（水印插件）、TouchEvent（移动端触摸事件支持插件）、NodeImgAdjust（拖拽调整节点图片大小插件）、Search（搜索插件）、Painter（节点格式刷插件）、Scrollbar（滚动条插件）、Formula（数学公式插件）、Cooperate（协同编辑插件）、RainbowLines（彩虹线条插件）、Demonstrate（演示模式插件）、OuterFrame（外框插件）、HandDrawnLikeStyle（手绘风格插件）\[收费\]、Notation（节点标记插件）\[收费\]、Numbers（节点编号插件）\[收费\]、Freemind（Freemind格式导入导出插件）\[收费\]、Excel（Excel格式导入导出插件）\[收费\]、Checkbox（待办插件）\[收费\]

本项目不会实现的特性：

> 1.自由节点，即多个根节点；
> 
> 2.概要节点后面继续添加节点；
> 
> 如果你需要以上特性，那么本库可能无法满足你的需求。

安装
==

npm i simple-mind-map

使用
==

提供一个宽高不为 0 的容器元素：

<div id\="mindMapContainer"\></div\>

另外再设置一下`css`样式：

#mindMapContainer \* {
  margin: 0;
  padding: 0;
}

然后创建一个实例：

import MindMap from "simple-mind-map";

const mindMap \= new MindMap({
  el: document.getElementById("mindMapContainer"),
  data: {
    data: {
      text: "根节点",
    },
    children: \[\],
  },
});

即可得到一个思维导图。

想要实现更多功能？可以查看开发文档。

License
=======

MIT。保留`mind-map`版权声明的情况下可随意商用。如不想保留可联系作者。

微信交流群
=====

微信添加`wanglinguanfang`拉你入群。根据过往的经验，大部分问题都可以通过查看issue列表或文档解决，所以提问前请确保你已经阅读完了所有文档，文档里没有的可在群里提问，不必私聊作者，如果你一定要私聊，请先发红包（￥9.9+每次）。

star
====

如果喜欢本项目，欢迎点个 star，这对我们很重要。

关于定制
====

如果你有个性化的商用定制需求，可以联系我们，我们提供付费开发服务，无论前端、后端、还是部署，都可以帮你一站式搞定。

请作者喝杯咖啡
=======

开源不易，如果本项目有帮助到你的话，可以考虑请作者喝杯咖啡~

> 推荐使用支付宝，微信获取不到头像。转账请备注【思维导图】。
> 
> 也可以通过购买付费插件来支持我们：付费插件。
> 
> 为什么需要你的赞助：simple-mind-map 的目标是成为开源中最好的思维导图，为开发者提供一个快速实现思维导图产品的js库，为用户提供一个免费好用的思维导图软件，为了这个目标，作者已经持续开发维护了3年多，耗费了非常多的精力，随着时间的推移，simple-mind-map 已经取得了一定的成绩，相比最初，无论是功能，还是体验都已经有了翻天覆地的改变，但是收益方面却可以忽略不计，因为 simple-mind-map 是采用 MIT 许可的开源项目，永久免费，保留版权下可随意商用，这也意味着很难直接通过项目获取收益，为爱发电的激情总会慢慢消退，所以你的赞助对项目的可持续发展非常重要，是作者持续维护的最大动力。

Think 志斌 小土渣的宇宙 qp ZXR 花儿朵朵 suka Chris 水车 仓鼠 千帆 才镇 小米bbᯤ²ᴳ \*棐 Luke 布林 南风 蜉蝣撼大叔 乙 敏 沐风牧草 有希 樊笼 达仁科技 小逗比 天清如愿 敬明朗 飞箭 戚永峰 moom 张扬 长沙利奥软件 HaHN 继龙 欣 易空小易 国发 建明 汪津合 博文 慕智打印-兰兰 锦冰 旭东 俊奇 橘半 pluvet 皇登攀 风格 SR 逆水行舟 LiuJL L sunniberg 在下青铜五 木星二号 阿晨 铁 庆国 Alex 子豪 宏涛 最多5个字 雨馨 ZX 峰 协成 木木 好名字 Kyle lsytyrt 秀树因馨雨 buddy 小川 Tobin 夏虫不语冰 晴空 黄泳 ccccs 。 Jeffrey 张文建 炫 Lawliet 一叶孤舟 晏江 Eric Joe 中文网字计划-江夏尧 梁辉 海云 皮老板 h.r.w Matt 时光匆匆 广兴 一亩三
