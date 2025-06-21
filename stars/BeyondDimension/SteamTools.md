---
project: SteamTools
stars: 22369
description: 🛠「Watt Toolkit」是一个开源跨平台的多功能 Steam 工具箱。
url: https://github.com/BeyondDimension/SteamTools
---

Watt Toolkit 🧰 (原名 Steam++)
============================

English | 简体中文

「Watt Toolkit」是一个开源跨平台的多功能游戏工具箱，此工具的大部分功能都是需要您下载安装 Steam 才能使用。

🚀 下载渠道
-------

-   
-   
-   软件官网
-   GitHub 发行版
-   码云 发行版
-   Arch 用户仓库（当前 Release 构建）
-   Arch 用户仓库 dev（拉取最新源码构建，也许会构建失败）

⬇️ 下载指南
-------

详见 ./doc/download-guide.md

✨ 功能
----

全新的 3.0 版本，支持自定义插件功能，以下功能为下载时自带的默认插件，可以自行删除或禁用。

1.  网络加速
    -   使用 YARP.ReverseProxy 开源项目进行本地反代来支持更快的访问游戏网站。
    -   通过加速服务拦截网络请求将一些 JS 脚本注入在网页中，提供类似网页插件的功能。
2.  账号切换
    -   快速切换已在当前 PC 上登录过的 Steam、Epic、Uplay 等等多平台账号，与管理 Steam 家庭共享库排序及禁用等功能。
3.  库存游戏
    -   直接管理你的 Steam 游戏库存，可以编辑游戏名称和自定义封面。
    -   监控 Steam 游戏下载进度实现 Steam 游戏下载完成定时关机功能。
    -   模拟运行 Steam 游戏，让您不用安装和下载对应的游戏也能挂游玩时间和掉落 Steam 卡片
    -   自助管理 Steam 游戏云存档，随时删除和上传自定义的存档文件至 Steam 云。
    -   解锁以及反解锁 Steam 游戏成就。
4.  本地令牌
    -   让您的手机令牌统一保存在电脑中、支持通用HOTP、TOTP、Steam、Google 等令牌导入。
    -   支持 Steam 登录账号自定绑定生成令牌、支持 Steam 批量确认交易功能。
5.  自动挂卡(新版本开发中)
    -   集成 ArchiSteamFarm 在应用内提供 挂机掉落 Steam 集换式卡牌 等功能。
6.  游戏工具
    -   强制游戏窗口使用无边框窗口化、更多功能待开发。

🖥 支持的操作系统
----------

-   Windows 11
-   Windows 10 版本 1809（OS 内部版本 17763）或更高版本
-   macOS 10.15 或更高版本
-   Ubuntu 20.04 或更高版本
-   Debian 11 或更高版本
-   Fedora 37 或更高版本
-   Deepin(UOS) 20 或更高版本
-   iOS 11 或更高版本（开发中…）
-   Android 5.0(API 21) 或更高版本

🧩 截图
-----

  

  

  
  

从移动端 Steam App 导入令牌指南
---------------------

-   Android 添加本地令牌（Xposed）
-   iOS 添加本地令牌（无需越狱/网络抓包）
-   iOS 添加本地令牌（无需越狱/iTunes 备份）
-   iOS 添加本地令牌（需越狱）

🌏 路线图
------

查看这个 milestones 来了解我们下一步的开发计划，并随时提出问题。

⌨️ 开发环境
-------

Visual Studio 2022 或 Visual Studio 2022 for Mac

-   系统要求
    -   Windows 11 版本 21H2 或更高版本：家庭版、专业版、专业教育版、专业工作站版、企业版和教育版
    -   macOS Big Sur 11.0 或更高版本
-   工作负荷
    -   Web 和云
        -   ASP.NET 和 Web 开发
    -   桌面应用和移动应用
        -   使用 .NET 的移动开发 / .NET Multi-platform App UI 开发
        -   .NET 桌面开发
        -   通用 Windows 平台开发
-   单个组件
    -   GitHub Extension for Visual Studio(可选)
-   Visual Studio Marketplace
    -   Avalonia for Visual Studio(可选)
    -   NUnit VS Templates(可选)

JetBrains Rider  
Visual Studio Code  
OpenJDK 17  
Android Studio Electric Eel 或更高版本  
Xcode 14 或更高版本

🏗️ 项目结构
--------

详见  ./src/README.md

🧑‍💼 加入我们
----------

-   .NET/C# 高级软件工程师（客户端方向）
-   .NET/C# 高级软件工程师

📄 开源代码库
--------

详见  ./doc/open-source-library.md
