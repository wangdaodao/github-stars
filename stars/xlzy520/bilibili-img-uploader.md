---
project: bilibili-img-uploader
stars: 373
description: Chrome/Firefox/Edge Extension bilibili img uploader。哔哩哔哩图床上传插件.https://chrome.google.com/webstore/detail/b%E7%AB%99%E5%9B%BE%E5%BA%8A/domljbndjbjgpkhdbmfgmiclggdfojnd?hl=zh-CN
url: https://github.com/xlzy520/bilibili-img-uploader
---

B站图床、短链(Firefox、Chrome、Edge)
============================

哔哩哔哩图床插件，速度快,多种图片压缩格式选择，自动读取Bilibili的Cookie，不再需要手动输入。 基于vitesse-webext 重构

### 说明(2023-12-06)

由于B站将之前的图片上传接口返回的图片链接不是永久的了，其他接口又因为`Origin`会被拦截，因此在`v2.2.0`版本之后，不会在右上角打开弹窗了，而是打开一个不存在的B站页面并注入插件。

### 在线安装

Chrome、Edge

Firefox

### 在线使用

假如有需要使用Web版本的图床上传工具，那么可以使用这个地址，但是需要填写自己B站的SESSDATA和bili\_jct，如果您有顾虑，还是建议使用客户端版

Web在线版

### 本地安装

下载

### 安装步骤

1.  进入`拓展程序`,可以通过地址栏输入`chrome://extensions/`，也可以从 `更多工具`\->`拓展程序`进入
2.  右上角开启`开发者模式`
3.  左侧点击 `加载已解压的拓展程序`,然后选择上面下载好的压缩包解压后的文件夹即可。

### 本地开发(支持热更新)

1.  执行`npm i`或者`pnpm i`, 执行`npm run dev`或`pnpm run dev`
2.  上一步(安装步骤)将文件夹选择为`extension`文件夹

### 构建

执行`npm run build`或`pnpm run build`

### 截屏

### 哔哩哔哩上传接口返回格式

{
    "code": 0,
    "message": "success",
    "data": {
        "image\_url": "http://i0.hdslb.com/bfs/album/104c4f1ae6b66d78a5952a191281ec7883dc5c5c.jpg",
        "image\_width": 818,
        "image\_height": 1000
    }
}

### 图片样式

Type

Url

原图

baseURL/1.jpg

原分辨率，质量压缩

baseURL/1.jpg@1e\_1c.jpg

规定宽，高度自适应，质量压缩

baseURL/1.jpg@104w\_1e\_1c.jpg

规定高，宽度自适应，质量压缩

baseURL/1.jpg@104h\_1e\_1c.jpg

规定高宽，质量压缩

baseURL/1.jpg@104w\_104h\_1e\_1c.jpg

原分辨率，webp格式(占用最小)

baseURL/1.jpg@104w\_104h\_1e\_1c.webp

规定高度，webp格式(占用最小)

baseURL/1.jpg@104w\_104h\_1e\_1c.webp

格式：(图像原链接)@(\\d+\[whsepqoc\]\_?)\*(.(|webp|gif|png|jpg|jpeg))?$

-   w:\[1, 9223372036854775807\] (width，图像宽度)
-   h:\[1, 9223372036854775807\] (height，图像高度)
-   s:\[1, 9223372036854775807\] (作用未知)
-   e:\[0,2\] (resize，0:保留比例取其小，1:保留比例取其大，2:不保留原比例，不与c混用)
-   p:\[1,1000\] (默认100，放大倍数，不与c混用)
-   q:\[1,100\] (quality，默认75，图像质量)
-   o:\[0,1\] (作用未知)
-   c:\[0,1\] (clip，0:默认，1:裁剪)
-   webp,png,jpeg,gif(不加则保留原格式)
-   不区分大小写，相同的参数后面覆盖前面
-   计算后的实际w_h不能大于原w_h，否则wh参数失效

### 防盗链解决方案

#### 全站图片使用

在html的head标签中设置如下标志，那么全站资源引用都不会携带referrer

<meta name\="referrer" content\="no-referrer"\>

### 新窗口打开

主要设置rel="noreferrer"，使用window.open打开的话是会默认携带referrer的，第一次还是会403

<a rel\="noreferrer" target\="\_blank"\></a\>

感谢
--

> 本项目得到以下项目的支持与帮助，在此表示衷心的感谢！

-   antfu/vitesse-webext
-   (License Certificate for JetBrains All Products Pack)
