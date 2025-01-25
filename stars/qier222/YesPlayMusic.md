---
project: YesPlayMusic
stars: 30188
description: 高颜值的第三方网易云播放器，支持 Windows / macOS / Linux :electron: 
url: https://github.com/qier222/YesPlayMusic
---

  

YesPlayMusic
------------

高颜值的第三方网易云播放器  
**🌎 访问DEMO**  |   **📦️ 下载安装包**  |   **💬 加入交流群**  
  

全新版本
----

全新2.0 Alpha测试版已发布，欢迎前往 Releases 页面下载。 当前版本将会进入维护模式，除重大bug修复外，不会再更新新功能。

✨ 特性
----

-   ✅ 使用 Vue.js 全家桶开发
-   🔴 网易云账号登录（扫码/手机/邮箱登录）
-   📺 支持 MV 播放
-   📃 支持歌词显示
-   📻 支持私人 FM / 每日推荐歌曲
-   🚫🤝 无任何社交功能
-   🌎️ 海外用户可直接播放（需要登录网易云账号）
-   🔐 支持 UnblockNeteaseMusic，自动使用各类音源替换变灰歌曲链接 （网页版不支持）
    -   「各类音源」指默认启用的音源。
    -   YouTube 音源需自行安装 `yt-dlp`。
-   ✔️ 每日自动签到（手机端和电脑端同时签到）
-   🌚 Light/Dark Mode 自动切换
-   👆 支持 Touch Bar
-   🖥️ 支持 PWA，可在 Chrome/Edge 里点击地址栏右边的 ➕ 安装到电脑
-   🟥 支持 Last.fm Scrobble
-   ☁️ 支持音乐云盘
-   ⌨️ 自定义快捷键和全局快捷键
-   🎧 支持 Mpris
-   🛠 更多特性开发中

📦️ 安装
------

Electron 版本由 @hawtim 和 @qier222 适配并维护，支持 macOS、Windows、Linux。

访问本项目的 Releases 页面下载安装包。

-   macOS 用户可以通过 Homebrew 来安装：`brew install --cask yesplaymusic`
    
-   Windows 用户可以通过 Scoop 来安装：`scoop install extras/yesplaymusic`
    

⚙️ 部署至 Vercel
-------------

除了下载安装包使用，你还可以将本项目部署到 Vercel 或你的服务器上。下面是部署到 Vercel 的方法。

本项目的 Demo (https://music.qier222.com) 就是部署在 Vercel 上的网站。

1.  部署网易云 API，详情参见 Binaryify/NeteaseCloudMusicApi 。你也可以将 API 部署到 Vercel。
    
2.  点击本仓库右上角的 Fork，复制本仓库到你的 GitHub 账号。
    
3.  点击仓库的 Add File，选择 Create new file，输入 `vercel.json`，将下面的内容复制粘贴到文件中，并将 `https://your-netease-api.example.com` 替换为你刚刚部署的网易云 API 地址：
    

{
  "rewrites": \[
    {
      "source": "/api/:match\*",
      "destination": "https://your-netease-api.example.com/:match\*"
    }
  \]
}

1.  打开 Vercel.com，使用 GitHub 登录。
    
2.  点击 Import Git Repository 并选择你刚刚复制的仓库并点击 Import。
    
3.  点击 PERSONAL ACCOUNT 旁边的 Select。
    
4.  点击 Environment Variables，填写 Name 为 `VUE_APP_NETEASE_API_URL`，Value 为 `/api`，点击 Add。最后点击底部的 Deploy 就可以部署到 Vercel 了。
    

⚙️ 部署到自己的服务器
------------

除了部署到 Vercel，你还可以部署到自己的服务器上

1.  部署网易云 API，详情参见 Binaryify/NeteaseCloudMusicApi
2.  克隆本仓库

git clone --recursive https://github.com/qier222/YesPlayMusic.git

1.  安装依赖

yarn install

1.  （可选）使用 Nginx 反向代理 API，将 API 路径映射为 `/api`，如果 API 和网页不在同一个域名下的话（跨域），会有一些 bug。
    
2.  复制 `/.env.example` 文件为 `/.env`，修改里面 `VUE_APP_NETEASE_API_URL` 的值为网易云 API 地址。本地开发的话可以填写 API 地址为 `http://localhost:3000`，YesPlayMusic 地址为 `http://localhost:8080`。如果你使用了反向代理 API，可以填写 API 地址为 `/api`。
    

```
VUE_APP_NETEASE_API_URL=http://localhost:3000
```

1.  编译打包

yarn run build

1.  将 `/dist` 目录下的文件上传到你的 Web 服务器

⚙️ 宝塔面板 docker应用商店 部署
---------------------

1.  安装宝塔面板，前往宝塔面板官网 ，选择正式版的脚本下载安装。
    
2.  安装后登录宝塔面板，在左侧导航栏中点击 Docker，首次进入会提示安装Docker服务，点击立即安装，按提示完成安装
    
3.  安装完成后在应用商店中找到YesPlayMusic，点击安装，配置域名、端口等基本信息即可完成安装。
    
4.  安装后在浏览器输入上一步骤设置的域名即可访问。
    

⚙️ Docker 部署
------------

1.  构建 Docker Image

docker build -t yesplaymusic .

1.  启动 Docker Container

docker run -d --name YesPlayMusic -p 80:80 yesplaymusic

1.  Docker Compose 启动

docker-compose up -d

YesPlayMusic 地址为 `http://localhost`

⚙️ 部署至 Replit
-------------

1.  新建 Repl，选择 Bash 模板
    
2.  在 Replit shell 中运行以下命令
    

bash <(curl -s -L https://raw.githubusercontent.com/qier222/YesPlayMusic/main/install-replit.sh)

1.  首次运行成功后，只需点击绿色按钮 `Run` 即可再次运行
    
2.  由于 replit 个人版限制内存为 1G（教育版为 3G），构建过程中可能会失败，请再次运行上述命令或运行以下命令：
    

cd /home/runner/${REPL\_SLUG}/music && yarn install && yarn run build

👷‍♂️ 打包客户端
-----------

如果在 Release 页面没有找到适合你的设备的安装包的话，你可以根据下面的步骤来打包自己的客户端。

1.  打包 Electron 需要用到 Node.js 和 Yarn。可前往 Node.js 官网 下载安装包。安装 Node.js 后可在终端里执行 `npm install -g yarn` 来安装 Yarn。
    
2.  使用 `git clone --recursive https://github.com/qier222/YesPlayMusic.git` 克隆本仓库到本地。
    
3.  使用 `yarn install` 安装项目依赖。
    
4.  复制 `/.env.example` 文件为 `/.env` 。
    
5.  选择下列表格的命令来打包适合的你的安装包，打包出来的文件在 `/dist_electron` 目录下。了解更多信息可访问 electron-builder 文档
    

命令

说明

`yarn electron:build --windows nsis:ia32`

Windows 32 位

`yarn electron:build --windows nsis:arm64`

Windows ARM

`yarn electron:build --linux deb:armv7l`

Debian armv7l（树莓派等）

`yarn electron:build --macos dir:arm64`

macOS ARM

💻 配置开发环境
---------

本项目由 NeteaseCloudMusicApi 提供 API。

运行本项目

# 安装依赖
yarn install

# 创建本地环境变量
cp .env.example .env

# 运行（网页端）
yarn serve

# 运行（electron）
yarn electron:serve

本地运行 NeteaseCloudMusicApi，或者将 API 部署至 Vercel

# 运行 API （默认 3000 端口）
yarn netease\_api:run

☑️ Todo
-------

查看 Todo 请访问本项目的 Projects

欢迎提 Issue 和 Pull request。

📜 开源许可
-------

本项目仅供个人学习研究使用，禁止用于商业及非法用途。

基于 MIT license 许可进行开源。

灵感来源
----

API 源代码来自 Binaryify/NeteaseCloudMusicApi

-   Apple Music
-   YouTube Music
-   Spotify
-   网易云音乐

🖼️ 截图
------
