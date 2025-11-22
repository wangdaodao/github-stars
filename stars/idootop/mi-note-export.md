---
project: mi-note-export
stars: 161
description: 📝 小米笔记秒变个人博客网站，一键备份小米笔记（包含图片、录音等文件）
url: https://github.com/idootop/mi-note-export
---

📝 小米笔记备份助手
===========

小米笔记秒变个人博客网站，一键备份小米笔记

功能列表
----

-   **⚡️ 一键备份**：完整备份笔记和图片等文件，避免数据丢失。
-   **✨ 秒变博客**：将小米笔记转成网页，您的个人博客即刻上线！
-   **🔒 隐私安全**：纯本地处理，无需第三方服务器，数据 100% 掌控
-   **🚗 迁移到其他平台**：支持保存为 Markdown 格式，方便导入其他应用

快速开始
----

首先，克隆项目到本地

git clone https://github.com/idootop/mi-note-export.git && cd mi-note-export

### 1\. 配置参数

然后，把 env 配置文件中的 Cookie 换成你自己的 👉 设置教程

MI\_COOKIE='xxxxxx'

### 2\. 备份笔记

下载小米笔记和图片/录音等附件到本地

docker run -it --rm --env-file $(pwd)/env -v $(pwd)/public/data:/app/public/data idootop/mi-note-sync:latest

Note

暂不支持备份私密笔记、待办和思维导图

### 3\. 生成博客

备份完成后，运行以下命令启动网页端，访问 http://localhost:3000 即可查看笔记。

docker run -it --rm --init -p 3000:3000 -v $(pwd)/public/data:/home/static/data idootop/mi-note-web:latest

### 4\. 部署上线

复制 `apps/web/dist` 下的静态文件到 `public`，然后将 `public` 文件夹打包上传到任意静态站点即可。

> 👉 查看演示网站：https://mi-note-export.vercel.app

public
├── assets
│   ├── index-Bu60GB9I.css
│   └── index-CprafGi1.js
├── data
│   ├── assets      # 下载的文件
│   ├── notes.json  # 小米笔记数据
├── index.html      # 静态网站首页
└── logo.png

Important

网页端默认可以访问全部笔记，公网部署需谨慎，防止泄露隐私信息！🚨

项目背景
----

犹记得我用过的最后一部小米手机是 红米 Note 4X —— 当年的千元机性价比之王，陪我走过了大学的青春岁月，记录了许多美好回忆。不过毕业之后，我就再没用过小米手机。

直到有一天，我收到了「小米云服务存储数据即将清空」的通知邮件。

原以为小米云服务里的数据是永久保存的，原来长时间不用也会被清空。

幸好我有经常看邮件的习惯，不然一个月之后就灰飞烟灭了。

但遗憾的是，小米笔记并没有提供「批量导出」的功能。

于是，便有了本项目 ;)

其他信息
----

-   本项目图标由「豆包」生成，宣传图使用 Figma 制作
-   本项目代码由 Cursor + Claude Sonnet 4.5 辅助生成
-   前端由 Vite + Svelte 强力驱动（轻量高效，适合小型单页应用）
-   后端由 Bun 强力驱动（更小、更高效的 Node.js 运行时替代品）
-   网站 Docker 镜像由 lipanski/docker-static-website 强力驱动（不到 **100KB**）

License
-------

MIT License © 2022-PRESENT Del Wang
