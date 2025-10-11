---
project: vxe-table
stars: 8347
description: vxe table 支持 vue2, vue3 的表格解决方案
url: https://github.com/x-extends/vxe-table
---

vxe-table
=========

简体中文 | 繁體中文 | English | 日本語

一个基于 Vxe UI 的 PC 端表格组件，支持增删改查的可编辑表格，支持复制粘贴、数据透视表、虚拟列表高性能的企业级表格解决方案

-   设计理念
    
    -   面向现代浏览器，不支持 IE
    -   双向数据流的设计，在渲染器或自定义扩展中支持直接操作数据值，达到最高效的简洁 API 设计
    -   按需加载、自定义主题样式
-   版本说明
    
    -   **V4**
        -   v3.17 重构筛选，更简单配置功能更强大
        -   v3.16 适配 Gantt 甘特图
        -   v3.15 优化虚拟渲染，降低内存的占用率
        -   v4.14 重构虚拟渲染，提高渲染与拖拽效果流畅度
        -   v4.13 优化虚拟渲染，提升 Chrome、Safari、Firefox 流畅度极兼容性
        -   v4.12 重构虚拟渲染，支持百万级数据渲染、渲染性能及流畅度大幅提升
        -   v4.11 重构展开行功能，同时支持展开行与虚拟渲染和冻结列
        -   v4.7 基于 vue3.2+，内部重构，拆分 Table 库和 UI 库，只支持现代浏览器，不支持 IE
        -   v4.0 基于 vue3.2+，只支持现代浏览器，不支持 IE（2020-03-01 ~ 2024-12-01 已停止维护）
    -   **V3**
        -   v3.19 重构筛选，更简单配置功能更强大
        -   v3.18 适配 Gantt 甘特图
        -   v3.17 优化虚拟渲染，降低内存的占用率
        -   v3.16 重构虚拟渲染，提高渲染与拖拽效果流畅度
        -   v3.15 优化虚拟渲染，提升 Chrome、Safari、Firefox 流畅度极兼容性
        -   v3.14 重构虚拟渲染，支持百万级数据渲染、渲染性能及流畅度大幅提升
        -   v3.13 重构展开行功能，同时支持展开行与虚拟渲染和冻结列
        -   v3.9 基于 vue2.6~2.7，内部重构，拆分 Table 库和 UI 库，只支持现代浏览器，不支持 IE
        -   v3.0 基于 vue2.6~2.7，支持现代浏览器并保留兼容 IE11（2020-03-01 ~ 2024-12-01 已停止维护）
    -   **V2**
        -   v2.0 基于 vue2.6~2.7，支持所有主流的浏览器，同时兼具功能与性能（2019-03-01 ~ 2021-12-01 已停止维护）
    -   **V1**
        -   v1.0 基于 vue2.6~2.7，支持所有主流的浏览器，实现表格的一切实用的功能（2018-02-01 ~ 2020-04-01 已停止维护）
-   版本计划
    
    -   优化展开行与冻结列
    -   优化虚拟渲染，支持千万级数据渲染
    -   数据图表可视化

浏览器支持
-----

80+ ✔

80+ ✔

90+ ✔

75+ ✔

10+ ✔

在线文档
----

👉 基础库  
👉 表格库  
👉 甘特图  
👉 可视化

QQ 交流群
------

该群供大家交流問題，如果群人数已满，将会不定期剔除不活跃的。

功能点
---

-   基础表格
-   配置式表格
-   斑马线条纹
-   多种边框
-   单元格样式
-   列宽拖动
-   列拖拽排序
-   行拖拽排序
-   最小/最大高度
-   自适应宽高
-   固定列
-   多级表头
-   表尾数据
-   高亮行或列
-   序号
-   单选框
-   复选框
-   排序
-   多字段排序
-   筛选
-   合并单元格
-   合并表尾
-   行分组
-   导入/导出/打印
-   显示/隐藏列
-   拖拽/自定义列排序
-   加载中
-   格式化内容
-   自定义插槽 - 模板
-   快捷菜单
-   展开行
-   工具栏
-   虚拟树
-   增删改查
-   数据校验
-   数据代理
-   键盘导航
-   渲染器
-   虚拟滚动
-   虚拟合并
-   CSS 变量主题
-   (企业版) 数据汇总
-   (企业版) 聚合函数
-   (企业版) 单元格区域选取
-   (企业版) 单元格复制/粘贴
-   (企业版) 单元格查找和替换
-   (企业版) 全键盘操作
-   (企业版) 集成图表

安装
--

版本：vue 3.x

npm install vxe-table

Get on unpkg and cdnjs

### NPM

// ...
import VxeUITable from 'vxe-table'
import 'vxe-table/lib/style.css'
// ...

createApp(App).use(VxeUITable).mount('#app')

### CDN

使用第三方 CDN 方式记得锁定版本号，避免受到非兼容性更新的影响  
_**不建议将第三方的 CDN 地址用于正式环境，因为该连接随时都可能会失效**_

<!DOCTYPE html\>
<html\>
<head\>
  <meta charset\="utf-8"\>
  <meta http-equiv\="Cache-Control" content\="no-cache, no-store, must-revalidate"\>
  <meta http-equiv\="X-UA-Compatible" content\="IE=edge,chrome=1"\>
  <!-- style -->
  <link rel\="stylesheet" href\="https://cdn.jsdelivr.net/npm/vxe-pc-ui@4/lib/style.css"\>
  <link rel\="stylesheet" href\="https://cdn.jsdelivr.net/npm/vxe-table@4/lib/style.css"\>
  <!-- vue -->
  <script src\="https://cdn.jsdelivr.net/npm/vue@3"\></script\>
  <!-- table -->
  <script src\="https://cdn.jsdelivr.net/npm/xe-utils"\></script\>
  <script src\="https://cdn.jsdelivr.net/npm/vxe-pc-ui@4"\></script\>
  <script src\="https://cdn.jsdelivr.net/npm/vxe-table@4"\></script\>
</head\>
<body\>
  <div id\="app"\>
    <div\>
      <vxe-table :data\="tableData"\>
        <vxe-column type\="seq" title\="Seq" width\="60"\></vxe-column\>
        <vxe-column field\="name" title\="Name"\></vxe-column\>
        <vxe-column field\="role" title\="Role"\></vxe-column\>
        <vxe-colgroup title\="Group1"\>
          <vxe-column field\="sex" title\="Sex"\></vxe-column\>
          <vxe-column field\="address" title\="Address"\></vxe-column\>
        </vxe-colgroup\>
      </vxe-table\>
    </div\>
  </div\>
  <script\>
    (function () {
      var App \= {
        data() {
          return {
            tableData: \[
              { id: 10001, name: 'Test1', role: 'Develop', sex: 'Man', address: 'Shenzhen' },
              { id: 10002, name: 'Test2', role: 'Test', sex: 'Man', address: 'Guangzhou' },
              { id: 10003, name: 'Test3', role: 'PM', sex: 'Man', address: 'Shanghai' }
            \]
          }
        }
      }
      Vue.createApp(App).use(VxeUI).use(VXETable).mount('#app')
    })()
  </script\>
</body\>
</html\>

示例
--

<template\>
  <div\>
    <vxe-table :data\="tableData"\>
      <vxe-column type\="seq" title\="Seq" width\="60"\></vxe-column\>
      <vxe-column field\="name" title\="Name"\></vxe-column\>
      <vxe-column field\="role" title\="Role"\></vxe-column\>
      <vxe-colgroup title\="Group1"\>
        <vxe-column field\="sex" title\="Sex"\></vxe-column\>
        <vxe-column field\="address" title\="Address"\></vxe-column\>
      </vxe-colgroup\>
    </vxe-table\>
  </div\>
</template\>

<script\>
export default {
  data() {
    return {
      tableData: \[
        { id: 10001, name: 'Test1', role: 'Develop', sex: 'Man', address: 'Shenzhen' },
        { id: 10002, name: 'Test2', role: 'Test', sex: 'Man', address: 'Guangzhou' },
        { id: 10003, name: 'Test3', role: 'PM', sex: 'Man', address: 'Shanghai' }
      \]
    }
  }
}
</script\>

运行项目
----

安装依赖

npm run update

启动本地调试

npm run serve

编译打包，生成编译后的目录：es,lib

npm run lib

Contributors
------------

Thank you to everyone who contributed to this project.

License
-------

MIT © 2019-present, Xu Liangzhan
