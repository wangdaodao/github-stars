---
project: vxe-pc-ui
stars: 127
description: Vxe UI 支持 vue2, vue3 的 PC 端组件库
url: https://github.com/x-extends/vxe-pc-ui
---

vxe-pc-ui
=========

简体中文 | 繁體中文 | English | 日本語

一个基于 vue 的 PC 端组件库

-   设计理念
    
    -   面向现代浏览器，高效的简洁 API 设计
    -   按需加载
-   计划
    
    -   ~~v1.0 基于 vue2.6+，停止维护 ~~
    -   ~~v2.0 基于 vue2.6+，停止维护 ~~
    -   v3.0 基于 vue2.6+，只支持现代浏览器，不支持 IE
    -   v4.0 基于 vue3.2+，只支持现代浏览器，不支持 IE
    -   计划功能：虚拟列表，支持百万级数据渲染
    -   计划功能：虚拟表单，支持万级表单项渲染
    -   计划功能：全功能表单可视化设计器
    -   计划功能：全功能列表可视化设计器
    -   计划功能：全功能流程图可视化设计器
    -   计划功能：虚拟列表，支持千万级数据渲染

浏览器支持
-----

80+ ✔

80+ ✔

90+ ✔

75+ ✔

10+ ✔

在线文档
----

👉 组件文档  
👉 表格文档

QQ 交流群
------

该群供大家交流問題，如果群人数已满，将会不定期剔除不活跃的。

功能点
---

👀 Vxe UI

-   alert 警告提示
-   anchor 锚点
-   anchor-link 锚点-链接
-   avatar 头像
-   badge 徽标
-   breadcrumb 面包屑
-   breadcrumb-item 面包屑-项
-   button 按钮
-   button-group 按钮组
-   calendar 日历
-   card 卡片
-   carousel 走马灯
-   carousel-item 走马灯 - 项
-   checkbox 复选框
-   checkbox-group 复选框-组
-   col 列
-   collapse 展开面板
-   collapse-pane 展开面板-容器
-   color-picker 颜色选择器
-   countdown 倒计时
-   date-picker 日期选择器
-   drawer 抽屉
-   empty 空数据
-   flow-design 流程设计器
-   flow-view 流程设计器-视图渲染
-   form 表单
-   form-design 表单设计器
-   form-group 表单-分组
-   form-item 表单-项
-   form-view 表单设计器-视图渲染
-   icon 图标
-   icon-picker 图标选择
-   image 图片
-   image-group 图片组
-   image-preview 图片预览
-   input 输入框
-   layout-aside 页面布局-左侧
-   layout-body 页面布局-内容
-   layout-container 页面布局-容器
-   layout-footer 页面布局-页尾
-   layout-header 页面布局-页头
-   link 链接
-   list-design 列表设计器
-   list-view 列表设计器-视图渲染
-   list 虚拟列表
-   loading 加载中
-   menu 菜单
-   modal 模态窗口
-   number-input 数值输入框
-   optgroup 下拉框-分组项
-   option 下拉框-项
-   pager 分页
-   password-input 密码输入框
-   print 打印
-   print-page-break 分页打印
-   pulldown 下拉容器
-   radio 单选框
-   radio-button 单选框-按钮
-   radio-group 单选框-组
-   rate 评分
-   result 结果
-   row 行
-   select 下拉框
-   spilt 分割面板
-   spilt-pane 分割面板-面板
-   slider 滑块
-   steps 步骤条
-   switch 开关
-   tab-pane 页签-容器
-   tabs 页签
-   text-ellipsis 多行文本溢出
-   table-select 表格下拉框
-   textarea 文本域
-   tip 提示
-   tooltip 文字提示
-   tree 树形组件
-   tree-select 树形下拉框
-   upload 附件上传
-   watermark 水印

👀 Vxe Table

-   table 表格-基础表格
-   column 表格-列
-   colgroup 表格-分组列
-   toolbar 表格-工具栏
-   grid 表格-配置式

安装
--

npm install vxe-pc-ui

// ...
import VxeUI from 'vxe-pc-ui'
import 'vxe-pc-ui/lib/style.css'
// ...
// ...
import VxeTable from 'vxe-table'
import 'vxe-table/lib/style.css'
// ...

createApp(App).use(VxeUI).use(VxeTable).mount('#app')

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
      <vxe-form
        :data\="formData"
        @submit\="submitEvent"\>
        <vxe-form-item title\="名称" field\="name" span\="12" :item-render\="{}"\>
          <template #default\="params"\>
            <vxe-input v-model\="formData.name"\></vxe-input\>
          </template\>
        </vxe-form-item\>
        <vxe-form-item title\="角色" field\="role" span\="12" :item-render\="{}"\>
          <template #default\="params"\>
            <vxe-input v-model\="formData.role"\></vxe-input\>
          </template\>
        </vxe-form-item\>
        <vxe-form-item title\="年龄" field\="age" span\="12" :item-render\="{}"\>
          <template #default\="params"\>
            <vxe-input v-model\="formData.age"\></vxe-input\>
          </template\>
        </vxe-form-item\>
        <vxe-form-item align\="center" span\="24" :item-render\="{}"\>
          <template #default\>
            <vxe-button type\="submit" status\="primary"\>提交</vxe-button\>
            <vxe-button type\="reset"\>重置</vxe-button\>
          </template\>
        </vxe-form-item\>
      </vxe-form\>
    </div\>
  </div\>
  <script\>
    (function () {
      var App \= {
        data() {
          return {
            formData: {
              name: '',
              nickname: '',
              sex: '',
              role: ''
            }
          }
        },
        methods: {
          submitEvent () {
            VxeUI.modal.message({ content: '保存成功', status: 'success' })
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
    <vxe-form
      :data\="formData"
      @submit\="submitEvent"\>
      <vxe-form-item title\="名称" field\="name" span\="12" :item-render\="{}"\>
        <template #default\="params"\>
          <vxe-input v-model\="formData.name"\></vxe-input\>
        </template\>
      </vxe-form-item\>
      <vxe-form-item title\="角色" field\="role" span\="12" :item-render\="{}"\>
        <template #default\="params"\>
          <vxe-input v-model\="formData.role"\></vxe-input\>
        </template\>
      </vxe-form-item\>
      <vxe-form-item title\="年龄" field\="age" span\="12" :item-render\="{}"\>
        <template #default\="params"\>
          <vxe-input v-model\="formData.age"\></vxe-input\>
        </template\>
      </vxe-form-item\>
      <vxe-form-item align\="center" span\="24" :item-render\="{}"\>
        <template #default\>
          <vxe-button type\="submit" status\="primary"\>提交</vxe-button\>
          <vxe-button type\="reset"\>重置</vxe-button\>
        </template\>
      </vxe-form-item\>
    </vxe-form\>
  </div\>
</template\>

<script\>
export default {
  data() {
    return {
      formData: {
        name: '',
        nickname: '',
        sex: '',
        role: ''
      }
    }
  },
  methods: {
    submitEvent () {
      VxeUI.modal.message({ content: '保存成功', status: 'success' })
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

贡献源码步骤
------

1.  如果是修复 bug，必须有示例的复现链接
2.  如果新功能，涉及代码风格、质量、还需有对应的示例页面

贡献者
---

Thank you to everyone who contributed to this project.

许可证
---

MIT © 2019-present, Xu Liangzhan
