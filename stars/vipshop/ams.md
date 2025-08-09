---
project: ams
stars: 395
description: AMS是基于 Vue.js 和 Element组件库、通过JSON配置来快速搭建管理后台的一整套前端解决方案
url: https://github.com/vipshop/ams
---

AMS
---

> AMS (admin material system)，管理后台物料系统。

AMS是基于 Vue.js 和 Element组件库、通过JSON配置来快速搭建管理后台的一整套解决方案

-   使用文档
-   演示示例
-   FAQ相关

npm 安装
------

```
npm i @ams-team/ams -S
```

CDN
---

目前可以通过 unpkg.com/@ams-team/ams 获取到最新版本的资源，在页面上引入 js 文件即可开始使用。

<!-- 引入ams库 -->
<script src\="https://unpkg.com/@ams-team/ams/lib/ams.js"\></script\>

快速开始
----

AMS的核心思想是通过规范数据接口的数据结构，再用类JSON的格式配置对应的 `区块` 和 `资源`，即可渲染成有UI和数据交互的前端界面。

### 第一步，注册资源

ams.resource('demoRes', { // ”demoRes“为资源名
    api: {
        prefix: 'https://easy-mock.com/mock/5a0023effbbb09615044cb82/', // 接口前缀
        update: 'update', // 更新表单数据，值为更新接口的path，和接口前缀组成最终请求的url
        read: 'read', // 读取表单数据，值为读取接口的path
    },
    fields: { // 字段
        id: { // “id”为字段名
            type: 'text', // 字段类型
            label: '文本' // 该字段显示在页面的文本标签
        },
        testRate: {
            type: 'rate',
            label: '评分'
        },
        testTextarea: {
            type: 'textarea',
            label: '评语'
        }
    }
})

### packages目录本地开发调试

npm run dev

### 第二步，注册区块

ams.block('demo', { // “demo”为区块名
    type: 'form', // 区块类型，“form”代表表单类型
    ctx: 'edit', // 状态，“edit”代表为可编辑
    resource: 'demoRes', // 该区块挂载的资源
    operations: { // 操作
        submit: { // 操作触发的事件名
            type: 'button', // 操作类型
            label: '提交' // 操作按钮显示的文案
        }
    },
    events: { // 事件流
        init: '@read', // “read”是内置的读取数据操作
        submit: '@update' // “update”是内置的更新数据操作
    }
});

### 第三步，渲染区块

// 渲染名字为“demo”的区块
ams.render('demo')

尝试AMS的最简单的方式是使用JSRUN上的官方入门Demo。你可以在浏览器新标签页中打开它，跟着例子学习一些基础用法。

### packages本地开发调试

```
npm run dev
```

浏览器支持
-----

现代浏览器 及 Internet Explorer 10+。

1.0版本规划
-------

> 通过 `1.0` 版本调整，希望把ams的配置的更加精简，希望解决一些设计不规范或者在实践中反馈不合理的地方，解决已知的痛点，敬请期待。点击查看1.0版本规划详情>>

本地开发
----

npm install
npm run build
npm run dev

开发团队
----

来自vip.com的开发者：

-   bfkkkd
-   w3cmark
-   wuzebin
-   EdwardQ

vip.com以外的开发者：

-   hodor-cn
-   ly525

社区互助
----

加入技术支持群，请扫二维码加“唯技术”老师咨询（添加时请备注“AMS”）

LICENSE
-------

Apache 2.0
