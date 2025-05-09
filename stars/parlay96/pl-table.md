---
project: pl-table
stars: 1153
description: A table based on element, 完美解决万级数据渲染卡顿问题
url: https://github.com/parlay96/pl-table
---

pl-table 不在更新维护, 你可以使用umy-ui，这里面包含了pl-table的所有功能。只是把pl-table移动到umy-ui库里面去了，umy-ui它一样解决表格卡的情况！请点击下面链接
====================================================================================================

> umy-ui官网

> umy-ui代码库，如何您是pl-table的使用者，感谢您点击这个，去点个Star吧

> （更多问题请加入pl-table交流群吧）感谢点击上方的Star！！！

> QQ交流1群: 675286117已满员
> 
> QQ交流2群： 893342082 新群

友情链接
----

#### \- uView 文档（超棒的移动跨端框架，文档详细，上手容易）

#### \- uView 开源地址（uView UI，是 uni-app 生态优秀的 UI 框架，全面的组件和便捷的工具会让您信手拈来，如鱼得水）

#### **vue-admin-beautiful** —— 企业级、通用型中后台前端解决方案（基于vue/cli 4 最新版，同时支持电脑，手机，平板）

#### **vue-admin-beautiful** —— 在线演示

#### \- ✨Element UI 表单设计及代码生成器（可视化表单设计器，一键生成 element 表单）

安装方式 and 引入方式
=============

\*\* npm方式安装 \*\*

  // npm i pl-table

  // npm引入方式 如下
  // main.js
  import plTable from 'pl-table'

  import 'pl-table/themes/index.css' // 引入样式（必须引入)，vuecli3.0不需要配置，cli2.0请查看webpack是否配置了url-loader对woff，ttf文件的引用,不配置会报错哦

  import 'pl-table/themes/plTableStyle.css' // 默认表格样式很丑 引入这个样式就可以好看啦（如果你不喜欢这个样式，就不要引入，不引入就跟ele表格样式一样）

  Vue.use(plTable);

  new Vue({
    el: '#app',
    render: h \=> h(App)
  });

  // 注意：如果你不想在入口文件注入, 而是想在单个某个文件页面引入，你可以这样写哦
  import { PlTable, PlTableColumn, PlxTableGrid, PlxTableColumn } from 'pl-table';
  export default {
    components: {
      PlTable,
      PlTableColumn
    },
  }

\*\* CDN方式 \*\*

  <!--引入表格样式-->
  <link rel\="stylesheet" href\="https://unpkg.com/pl-table/themes/index.css"\>

  <!--默认表格样式很丑 引入这个样式就可以好看啦-->
  <link rel\="stylesheet" href\="https://unpkg.com/pl-table/themes/plTableStyle.css"\>

  <!-- import Vue -->
  <script src\="https://unpkg.com/vue/dist/vue.js"\></script\>

  <script src\="https://unpkg.com/pl-table/lib/index.js"\></script\>
  // 真实项目不建议你直接引入  <script src\="https://unpkg.com/pl-table/lib/index.js"\></script\>这样去引如会直接下最新版本，如果你的项目打包发     // 布了，然后遇见pl-table大更新 你可能项目会报错。
  // 推荐你这样引入： https://unpkg.com/pl-table@2.7.4/lib/index.js   加入版本号！

用前须知（必读）
========

1.  pl-table不使用use-virtual属性，整个表格功能性的东西都是element表格，除了样式
2.  pl-table 开启use-virtual虚拟可以支持微小的合并行|列 如2列 2行，支持多级头
3.  plx-table-grid同时虚拟不支持合并行|列，不支持多级头，非必要不推荐使用X + Y同时虚拟
4.  pl-table开启use-virtual不支持展开行

pl-table表格的API
==============

https://github.com/livelyPeng/pl-table/wiki/pl-table-api

plx-table-grid表格的API（对列没有刚需的，没必要用这个，用上面的pl-table就行, 列没有几百列不需要用这个）
=================================================================

https://github.com/livelyPeng/pl-table/wiki/plx-table-grid-APi

实例文件（基础用法）
==========

> https://github.com/livelyPeng/pl-table/blob/master/website-project/testFile/index.vue // npm方式实例

> https://github.com/livelyPeng/pl-table/blob/master/website-project/testFile/cdn.html // cdn方式实例

更新日志
====

**2.7.5**

1.  修改合计
2.  新增属性
3.  新增pl-table大数据树表格
4.  重构代码
5.  修改BUG

**2.7.4**

1.  解决动态加载数据，当滚动条未在顶部时，加载的数据只显示3条
2.  新增表格最大高度属性，max-height，你可以添加如此属性
3.  优化表格
4.  解决高度异步赋值，导致表格高度计算错误问题
5.  解决缓存组件，不能记录之前滚动条的滚动距离
6.  之前绑定表格数据是datas, 现在是data属性
7.  添加分页组件
8.  新增表格滚动底部方法
9.  解决pagingScrollTopLeft方法的BUG

**其他版本** . . .

当前版本BUG（等着下个版本修改）
=================

暂未发现
