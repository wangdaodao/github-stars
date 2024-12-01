---
project: vue-material-admin
stars: 615
description:  基于Vue3 、Vuetify、TypeScript、Nest.js、MySql、TypeORM轻量化设计中后台管理模板 
url: https://github.com/armomu/vue-material-admin
---

Vue Material Admin


====================

Vue Material Admin 是一个基于 `Vuetify.js` 组件库的开源中后台模板，采用了服务器端 + 前端全栈TypeScript技术开发，该项目遵循 Material Design 的设计规范，并在 Vuetify.js 基础组件继续向上构建开发，对其进行了扩展和优化，旨在实现一个轻量化、高性能的中后台解决方案，Vue Material Admin 目前阶段主要用于学习、功能展示和开发用例测试，同时也适合作为新项目的启动模板，项目将持续更新，增加更多的功能和优化现有的模块 🔥🔥🔥

⛲ 技术栈
-----

### WEB 前端

-   框架: Vue3
-   状态管理: Pinia
-   类型系统: TypeScript
-   UI 组件库: Vuetify.js

### Nodejs 服务端

-   框架: Nest.js
-   数据库: MySQL
-   映射工具: TypeORM
-   缓存: Redis

🌻 页面截图
-------

🍭 PreView
----------

🧱Vercel需要墙！打不开的同学自行下载项目在本地开发环境预览

-   🌍 Vercel https://vue-material-admin.vercel.app/

👊 TODO
-------

1.  🍳 Vuetify 组件
    -   ✅ Table
    -   ✅ Calendar
    -   ✅ DictSelect(自动注册可枚举字典下拉框)
2.  🏡 智能家居控制组件
    -   ✅ 环形控制器(支持鼠标拖动进度)
    -   ✅ 360度全景图预览(其实是Babylon.js的一个API而已)
3.  🔥 Pixi.js捕鱼DEMO
    -   ✅ 小鱼自动移动
    -   ✅ 射击撒网
    -   ❌ 小鱼获取新位置后旋转对应角度方向
    -   ❌ 击落效果获取金币
    -   ❌ 音频
4.  🐝 适配
    -   ✅ 夜间模式
    -   ✅ 适配移动设备(大部分适配)
    -   ✅ 主题颜色修改
5.  💻 后端 Nest.js
    -   ✅ TypeORM
    -   ✅ JWT 认证
    -   ✅ RBAC 权限控制

📑 本地开发
-------

### 前端

> ⚠️ 本地开发需要 `nodejs 18/20` vite5不支持更低的nodejs版本

```
git clone https://github.com/armomu/vue-material-admin.git

cd vue-material-admin

pnpm install

pnpm run dev

```

### 后端

接口文档 https://nliq7vrniv.apifox.cn

> 非常感谢 zclzone大佬提供的Nestjs服务项目，让我快速搭建了这个模版的后台服务，也从vue-naive-admin项目中学习到了一些新的封装思路

后端服务启动请切换到 Serve 分支查看教程，注意MySQL要导入Serve分支下的sql脚本的数据