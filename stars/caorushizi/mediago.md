---
project: mediago
stars: 7264
description: 跨平台视频提取工具：支持流媒体下载、视频下载、m3u8 下载及 B站视频下载，提供 Windows 和 Mac 桌面客户端。Cross-platform video extraction tool: Supports streaming download, video download, m3u8 download, and Bilibili video download, with desktop clients for Windows and Mac.
url: https://github.com/caorushizi/mediago
---

MediaGo
=======

快速开始   •   官网   •   文档   •   Discussions  

English   •   日本語  

  

* * *

Intro
-----

本项目支持 m3u8 视频在线提取工具 流媒体下载 m3u8 下载。

-   **✅  无需抓包**： 使用软件自带浏览器可以轻松嗅探网页中的视频资源，通过嗅探到的资源列表选择自己想要下载的资源，简单快速。
-   **📱  移动播放**： 可以轻松无缝的在 PC 和移动设备之前切换，下载完成后即可使用手机观看视频。
-   **⚡️  批量下载**： 支持同时下载多个视频和直播资源，高速带宽不闲置。
-   **🎉  支持 docker 部署**： 支持 docker 部署 web 端，方便快捷。

Quickstart
----------

运行代码需要 node 和 pnpm，node 需要在官网下载安装，pnpm 可以通过`npm i -g pnpm`安装。

运行代码
----

# 代码下载
git clone https://github.com/caorushizi/mediago.git

# 安装依赖
pnpm i

# 开发环境
pnpm dev

# 打包运行
pnpm release

# 构建 docker 镜像
docker buildx build -t caorushizi/mediago:latest .

# docker 启动
docker run -d --name mediago -p 8899:8899 -v mediago-data:/root/mediago registry.cn-beijing.aliyuncs.com/caorushizi/mediago

Releases
--------

### v3.0.0 (2024.10.7 发布)

#### 软件下载

-   【mediago】 windows(安装版) v3.0.0
-   【mediago】 windows(便携版) v3.0.0
-   【mediago】 macos arm64（apple 芯片） v3.0.0
-   【mediago】 macos x64（intel 芯片） v3.0.0
-   【mediago】 linux v3.0.0
-   【mediago】 docker v3.0 `docker run -d --name mediago -p 8899:8899 -v /root/mediago:/root/mediago registry.cn-beijing.aliyuncs.com/caorushizi/mediago:v3.0.0`

### docker 宝塔面板一键部署（推荐）

1.  安装宝塔面板，前往 宝塔面板 官网，选择正式版的脚本下载安装
    
2.  安装后登录宝塔面板，在菜单栏中点击 `Docker`，首次进入会提示安装`Docker`服务，点击立即安装，按提示完成安装
    
3.  安装完成后在应用商店中找到`MediaGo`，点击安装，配置域名等基本信息即可完成安装
    

### 软件截图

### 重要更新

-   支持 docker 部署 web 端
-   更新桌面端 UI

### 更新日志

-   更新桌面端 UI
-   支持 docker 部署 web 端
-   新增视频播放，支持桌面端和移动端播放
-   修复 mac 打开无法展示界面的问题
-   优化了批量下载的交互
-   添加了 windows 的便携版（免安装哦）
-   优化了下载列表，支持页面中多个视频的嗅探
-   支持收藏列表手动导入导出
-   支持首页下载列表导出
-   优化了【新建下载】表单的交互逻辑
-   支持 UrlScheme 打开应用，并添加下载任务
-   修复了一些 bug 并提升用户体验

软件截图
----

技术栈
---

-   react https://react.dev/
-   electron https://www.electronjs.org
-   koa https://koajs.com
-   vite https://cn.vitejs.dev
-   antd https://ant.design
-   tailwindcss https://tailwindcss.com
-   shadcn https://ui.shadcn.com/
-   inversify https://inversify.io
-   typeorm https://typeorm.io

鸣谢
--

-   N\_m2u8DL-CLI 来自于 https://github.com/nilaoda/N\_m3u8DL-CLI
-   N\_m3u8DL-RE 来自于 https://github.com/nilaoda/N\_m3u8DL-RE
-   mediago 来自于 https://github.com/caorushizi/hls-downloader
