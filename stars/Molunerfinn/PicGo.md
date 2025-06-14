---
project: PicGo
stars: 25273
description: :rocket:A simple & beautiful tool for pictures uploading built by vue-cli-electron-builder
url: https://github.com/Molunerfinn/PicGo
---

PicGo
=====

> 图片上传+管理新体验

应用概述
----

**PicGo: 一个用于快速上传图片并获取图片 URL 链接的工具**

PicGo 本体支持如下图床：

-   `七牛图床` v1.0
-   `腾讯云 COS v4\v5 版本` v1.1 & v1.5.0
-   `又拍云` v1.2.0
-   `GitHub` v1.5.0
-   `SM.MS V2` v2.3.0-beta.0
-   `阿里云 OSS` v1.6.0
-   `Imgur` v1.6.0

**本体不再增加默认的图床支持。你可以自行开发第三方图床插件。详见 PicGo-Core**。

特色功能
----

-   支持拖拽图片上传
-   支持快捷键上传剪贴板里第一张图片
-   Windows 和 macOS 支持右键图片文件通过菜单上传 (v2.1.0+)
-   上传图片后自动复制链接到剪贴板
-   支持自定义复制到剪贴板的链接格式
-   支持修改快捷键，默认快速上传快捷键：`command+shift+p`（macOS）| `control+shift+p`（Windows\\Linux)
-   支持插件系统，已有插件支持 Gitee、青云等第三方图床
    -   更多第三方插件以及使用了 PicGo 底层的应用可以在 Awesome-PicGo 找到。欢迎贡献！
-   支持通过发送 HTTP 请求调用 PicGo 上传（v2.2.0+)
-   更多功能等你自己去发现，同时也会不断开发新功能
    -   开发进度可以查看 Projects，会同步更新开发进度

**如果第一次使用，请参考应用 使用文档。遇到问题了还可以看看 FAQ 以及被关闭的 issues。**

下载安装
----

下载源

地址/安装方式

平台

备注

GitHub Release

https://github.com/Molunerfinn/PicGo/releases

All

国内下载速度可能会慢

腾讯云COS

https://github.com/Molunerfinn/PicGo/releases 附在更新日志结尾

All

感谢 腾讯云COS 提供的赞助支持

山东大学镜像站

https://mirrors.sdu.edu.cn/github-release/Molunerfinn\_PicGo

All

感谢 山东大学镜像站 提供的镜像支持

Scoop

`scoop bucket add extras` & `scoop install picgo`

Windows

感谢 @huangnauh 和 @Gladtbam 的贡献

Chocolatey

`choco install picgo`

Windows

感谢 @iYato 的贡献

Homebrew

`brew install picgo --cask`

macOS

感谢 @womeimingzi11 的贡献

AUR

`yay -S picgo-appimage`

Arch-Linux

感谢 @houbaron 的贡献

应用截图
----

开发说明
----

> 目前仅针对 Mac、Windows。Linux 平台并未测试。

如果你想要学习、开发、修改或自行构建 PicGo，可以依照下面的指示：

> 如果想学习 Electron-vue 的开发，可以查看我写的系列教程——Electron-vue 开发实战

1.  你需要有 Node、Git 环境，了解 npm 的相关知识。
2.  `git clone https://github.com/Molunerfinn/PicGo.git` 并进入项目。
3.  `yarn` 下载依赖。注意如果你没有 `yarn`，请去 官网 下载安装后再使用。 **用 `npm install` 将导致未知错误！**
4.  Mac 需要有 Xcode 环境，Windows 需要有 VS 环境。
5.  如果需要贡献代码，可以参考贡献指南。

### 开发模式

输入 `npm run electron:serve` 进入开发模式，开发模式具有热重载特性。不过需要注意的是，开发模式不稳定，会有进程崩溃的情况。此时需要：

ctrl+c # 退出开发模式
npm run electron:serve # 重新进入开发模式

**注：Windows 开发模式运行之后会在底部任务栏的右下角应用区出现 PicGo 的应用图标。**

### 生产模式

如果你需要自行构建，可以 `npm run electron:build` 开始进行构建。构建成功后，会在 `dist_electron` 目录里出现构建成功的相应安装文件。

**注意**：如果你的网络环境不太好，可能会出现 `electron-builder` 下载 `electron` 二进制文件失败的情况。这个时候需要在 `npm run electron:build` 之前指定一下 `electron` 的源为国内源：

export ELECTRON\_MIRROR="https://npmmirror.com/mirrors/electron/"
# 在 Windows 上，则可以使用 set ELECTRON\_MIRROR=https://npmmirror.com/mirrors/electron/ （无需引号）
npm run electron:build

只需第一次构建的时候指定一下国内源即可。后续构建不需要特地指定。二进制文件下载在 `~/.electron/` 目录下。如果想要更新 `electron` 构建版本，可以删除 `~/.electron/` 目录，然后重新运行上一步，让 `electron-builder` 去下载最新的 `electron` 二进制文件。

其他相关
----

-   vs-picgo：PicGo 的 VS Code 版。
-   flutter-picgo：PicGo 的手机版 App（支持 Android 和 iOS ）。
-   PicHoro：另一款支持 PicGo 配置的手机版 App（暂时只支持 Android）。

赞助
--

如果你喜欢 PicGo 并且它对你确实有帮助，欢迎给我打赏一杯咖啡哈~

支付宝：

微信：

License
-------

MIT

Copyright (c) 2017 - Now Molunerfinn
