---
project: wereader
stars: 728
description: 一个浏览器扩展：主要用于微信读书做笔记，对常使用 Markdown 做笔记的读者比较有帮助。
url: https://github.com/Higurashi-kagome/wereader
---

  
Wereader
-----------

**一个 Chrome / Firefox 扩展：主要用于微信读书做笔记，对常使用 Markdown 做笔记的读者比较有帮助。**

注意
--

之前有人在 Issues 中反馈获取标注等信息有被封号的风险（#121），请酌情使用。

本扩展仅供学习交流使用，请勿侵犯微信读书和作者权益。

安装
--

不能访问 Chrome 网上应用店时按如下操作在 Chrome 上手动安装（注意：手动安装的扩展不会自动更新）：

1.  首先，下载 wereader.zip。下载好后解压到某个文件夹（比如 `wereader`）。
    
2.  接下来，进入 Chrome，在地址栏输入 `chrome://extensions/` 后回车，进入扩展管理页面。
    
3.  进入页面后，先打开 `开发者模式`，再点击 `加载已解压的扩展程序`，找到前面解压得到的文件夹 `wereader`，**单击**该文件夹，这时候文件夹被选中，点击 `选择文件夹` 即可。
    

查看演示

功能
--

1.  一键导出标注、想法、目录；
2.  导出格式自定义；
3.  一键复制图片、注释、代码块；
4.  护眼色主题；
5.  标注搜索、标注目录；
6.  借助正则匹配对标注进行处理；
7.  选中后自动标注、自动复制或自动查询；
8.  解除右键限制；
9.  读书页图片、代码块放大。

致谢
--

Item

Reason

wereader

此项目为该扩展的起源，我先是在 pythontools/wereader 中完善了该项目，然后才基于 pythontools/wereader 实现了该扩展。

examples-of-web-crawlers

编写 pythontools/wereader 的过程中参考了该项目中的一键导出微信读书的书籍和笔记。

jquery/jquery: jQuery JavaScript Library

简化代码。

sweetalert2

实现弹窗。

HbnLg

图标来源于 iconfont，图库显示 Hbnlg 为图标作者。

SingleFile

设置页模仿自该扩展。

weread\_helper\_extension

参考该项目中的代码实现了公众号浏览和书架管理（目前该功能已移除，建议通过手机管理书架）。

uzairfarooq/arrive

方便监听 DOM 变动。

jquery/jquery-mousewheel

方便监听滚轮事件。

参考
--

Item

Description

chrome-plugin-demo

Chrome 扩展开发教程

Extensions - Chrome Developers

Chrome 扩展官方文档

其他
--

  
**加微信进交流群（备注：wereader 交流群）**
