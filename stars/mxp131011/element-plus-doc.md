---
project: element-plus-doc
stars: 18
description: null
url: https://github.com/mxp131011/element-plus-doc
---

element-plus-doc README
=======================

`element-plus` 的一个工具插件,用于智能提示，悬停显示属性文档等等，整理至`element-plus` 2.3.0 的文档，后续`element-plus`更新，也会跟着更新，如未及时更新，请大家到github提交issues 催促作者更新，有什么问题也请大家及时反馈，github访问不了也可到gitee提交issues，或者加作者微信:mxp131011 或者反馈。如还有什么需求，也可提出(不考虑`element-plus`之外的需求)。

功能介绍
----

1.  \[下 划 线\]：标签添加下划线，表示此标签可以显示悬浮文档，以及输入智能提示
    
2.  \[悬浮文档\]：鼠标移动到`element-plus`组件的标签上会提示标签此标签的所有文档。
    
3.  \[悬浮文档\]：鼠标移动到`element-plus`组件标签中的某条属性时仅显示该条属性的文档
    
4.  \[悬浮文档\]：鼠标移动到`element-plus`组件标签中的`ref`属性时会显示此组件暴露出的所有方法
    
5.  \[智能提示\]：`<template></template>`标签内输入`<el`或自定义前缀(如：`<base`)时会提示补全整个标签，如输入`<elbu`会补全`<el-button></el-button>`
    
6.  \[代码块智能提示\]：`<template></template>`标签内输入`el`(不带`<`),会提示出定义好的代码块,如输入:`elt`会补全如下内容
    
    <el-table :data\="data" :scroll\="{ x: 1200 }" :loading\="loading" bordered rowKey\="id" @change\="changePage"\>
      <el-table-column label\="id" prop\="id" width\="100"\></el-table-column\>
      <el-table-column label\="name"\>
        <template slot-scope\="scope"\>
          <span\>{{ scope.$index + 1 }}、{{ scope.row.name }}</span\>
        </template\>
      </el-table-column\>
      <el-table-column label\="操作" width\="100" fixed\="right"\>
        <template slot-scope\="scope"\>
          <el-button type\="link" @click\="toDo(scope.row)"\>修改</el-button\>
        </template\>
      </el-table-column\>
    </el-table\>
    
7.  \[代码块智能提示\]：在`js`、`ts`文件中或则`vue`文件的`<script></script>`标签内输入对应的代码会补全完整的代码。如：输入`al`,会补全如下内容
    
    ElMessageBox.alert('内容', '标题', {
      confirmButtonText: '确定',
      callback: (action) \=> {
        if (action \=== 'confirm') {
        }
      },
    });
    
8.  可在设置中设置自定义前缀，如 `base`,`my` 等等，以此前缀或 `le` 前缀开头的都视作 `element-plus` 组件。会添加相应悬浮文档（为了性能，不算 `el` 前缀，最多支持还可添加三个自定义前缀）
    
9.  如果自定义前缀还是无法满足需求，可以设置自定义映射组件，如：`<base-input-numb-for>` 组件想拥有 `<el-input>` 的文档或提示，则可在设置中配置：`{ baseInputNumbFor: 'elInput'` ，此时，`<base-input-numb-for>`就有了 `<el-input>` 的智能提示和此鼠标悬浮显示文档功能了
    
10.  可在设置中修改 `element-plus` 中/英官网的地址
    
11.  本插件仅支持中文和英文的提示文档，会根据 vscode 当前语言自动显示中文或英文的文档
    

### 示例图

1.  标签添加下划线 (图中所有有下划线的标签都支悬浮文档 和 持智能提示)
    
2.  鼠标移动到`element-plus`组件的标签上会提示标签此标签的所有文档
    
3.  \[悬浮文档\]：鼠标移动到`element-plus`组件标签中的某条属性时仅显示该条属性的文档
    
4.  \[悬浮文档\]：鼠标移动到`element-plus`组件标签中的`ref`属性时会显示此组件暴露出的所有方法
    
5.  \[智能提示\]：`<template></template>`标签内输入`<el`或自定义前缀(如：`<base`)时会提示补全整个标签，如输入`<elbu`会补全`<el-button></el-button>`
    
6.  \[代码块智能提示\]：`<template></template>`标签内输入`el`(不带`<`),会提示出定义好的代码块
    
7.  \[代码块智能提示\]：在`js`、`ts`文件中或则`vue`文件的`<script></script>`标签内输入对应的代码会补全完整的代码。
    

### 模板内的代码片段

输入字段

说明

生成代码

info

普通类型的消息提示 (ElMessage)

  

ElMessage.info({
  message: '',
  showClose: true,
});

success

成功类型的消息提示 (ElMessage)

  

ElMessage.success({
  message: '',
  showClose: true,
});

warning

警告类型的消息提示 (ElMessage)

  

ElMessage.warning({
  message: '',
  showClose: true,
});

error

错误类型的消息提示 (ElMessage)

  

ElMessage.error({
  message: '',
  showClose: true,
});

alert

alert消息弹出框 (ElMessageBox)

  

ElMessageBox.alert('内容', '标题', {
  confirmButtonText: '确定',
  callback: action \=> {
    if (action \=== 'confirm') {
      
    }
  }
});

confirm

confirm消息弹出框 (ElMessageBox)

  

ElMessageBox.confirm('内容', '标题', {
  {
     confirmButtonText: '确定'
     cancelButtonText: '取消'
  }
}).then(() \=> {
  
}).catch(() \=> {
  
});

prompt

prompt消息弹出框 (ElMessageBox)

  

ElMessageBox.prompt('内容', '标题', {
  {
     confirmButtonText: '确定'
     cancelButtonText: '取消'
  }
}).then(() \=> {
  
}).catch(() \=> {
  
});

info

普通类型的消息通知 (ElNotification)

  

ElNotification.info({
  title: '温馨提示',
  message: '',
});

success

成功类型的消息通知 (ElNotification)

  

ElNotification.success({
  title: '成功',
  message: '',
});

warning

警告类型的消息通知 (ElNotification)

  

ElNotification.warning({
  title: '警告',
  message: '',
});

error

错误类型的消息通知 (ElNotification)

  

ElNotification.error({
  title: '错误',
  message: '',
});

### JS/TS 内的代码片段

输入字段

说明

生成代码

template

模板

  

<template\>
  
</template\>

slot

插槽

  

<slot name\=""\></slot\>

elbutt

按钮组件

  

<el-button type\="" @click\=""\></el-button\>

el-button

按钮组件

  

<el-button type\="" @click\=""\></el-button\>

el-confirm

确认按钮组件

  

<el-button type\="primary" @click\="confirm()" :loading\="confirmLoading"\>确认</el-button\>

el-cancel

取消按钮组件

  

<el-button type\="default" @click\="cancel()"\>取消</el-button\>

el-link

路由跳转组件

  

<el-link type\="" href\="" target\="\_blank"\></el-link\>

el-scrollbar

滚动条组件

  

<el-scrollbar height\=""\>

</el-scrollbar\>

el-space

间距组件

  

<el-space wrap\>

</el-space\>

el-autocomplete

自动补全输入框组件

  

<el-autocomplete
  v-model\="state"
  :fetch-suggestions\="querySearch"
  clearable
  class\="inline-input w-50"
  placeholder\="Please Input"
  @select\="handleSelect"
\></el-autocomplete\>

el-icon

图标组件

  

<i class\="el-icon-"\></i\>

el-tabs

标签页组件

  

<el-tabs v-model\="activeKey"\>
  <el-tab-pane key\="1" tab\=""\></el-tab-pane\>
</el-tabs\>

el-tab-pane

面包屑子组件

  

<el-tab-pane key\="" tab\=""\></el-tab-pane\>

el-container

布局组件

  

<el-container\>
  <el-aside width\="200px"\>Sider</el-aside\>
  <el-container\>
    <el-header\>Header</el-header\>
    <el-main\>main</el-main\>
    <el-footer\>footer</el-footer\>
  </el-container\>
</el-container\>

el-aside

布局侧边栏组件

  

<el-aside\>aside</el-aside\>

el-header

布局顶部组件

  

<el-header\>header</el-header\>

el-main

布局内容组件

  

<el-main\>main</el-main\>

el-footer

布局底部组件

  

<el-footer\>footer</el-footer\>

el-breadcrumb

面包屑组件

  

<el-breadcrumb separator-class\="el-icon-arrow-right"\>
  <el-breadcrumb-item :to\="{ path: '/' }"\></el-breadcrumb-item\>
  <el-breadcrumb-item\></el-breadcrumb-item\>
  <el-breadcrumb-item\></el-breadcrumb-item\>
</el-breadcrumb\>

el-breadcrumb-item

面包屑子组件

  

<el-breadcrumb-item\></el-breadcrumb-item\>

el-menu

菜单组件

  

<el-menu :default-active\="current" mode\="horizontal"\>
  <el-menu-item index\="1"\></el-menu-item\>
  <el-menu-item index\="2"\></el-menu-item\>
</el-menu\>

el-submenu

子菜单组件

  

<el-submenu\>
  <span slot\="title"\></span\>
  <el-menu-item index\="1"\></el-menu-item\>
  <el-menu-item index\="2"\></el-menu-item\>
</el-submenu\>

el-menu-item

菜单子组件

  

<el-menu-item index\="1"\></el-menu-item\>

el-timeline

时间轴组件

  

<el-timeline :reverse\="false"\>
  <el-timeline-item\></el-timeline-item\>
  <el-timeline-item\></el-timeline-item\>
</el-timeline\>

el-timeline-item

时间轴子组件

  

<el-timeline-item color\=""\></el-timeline-item\>

el-collapse

折叠面板组件

  

<el-collapse v-model\="activeKey"\>
  <el-collapse-item name\="1" title\=""\></el-collapse-item\>
</el-collapse\>

el-collapse-item

折叠面板子组件

  

<el-collapse-item name\="" title\=""\></el-collapse-item\>

el-descriptions

描述列表组件

  

<el-descriptions title\=""\>
  <el-descriptions-item label\=""\></el-descriptions-item\>
</el-descriptions\>

el-descriptions-item

描述列表子组件

  

<el-descriptions-item label\=""\></el-descriptions-item\>

el-result

结果组件

  

<el-result
  icon\=""
  title\=""
  sub-title\=""
\>
  <template slot\="extra"\>
    
  </template\>
</el-result\>

el-empty

空状态组件

  

<el-empty description\=""\></el-empty\>

el-dropdown

下拉菜单父组件

  

<el-dropdown\>
  <span\></span\>
  <el-dropdown-menu slot\="dropdown"\>
    <el-dropdown-item\>
      
    </el-dropdown-item\>
    <el-dropdown-item disabled\>
      
    </el-dropdown-item\>
  </el-dropdown-menu\>
</el-dropdown\>

el-dropdown-menu

下拉菜单子组件

  

<el-dropdown-menu\>
  <el-dropdown-item\>
    
  </el-dropdown-item\>
  <el-dropdown-item disabled\>
    
  </el-dropdown-item\>
</el-dropdown-menu\>

el-dropdown-item

下拉菜单子组件

  

<el-dropdown-item\>
  
</el-dropdown-item\>

el-pagination

分页组件

  

<el-pagination
  background
  :total\="total"
  :page-size\="100"
  :page-sizes\="\[10, 25, 50, 100\]"
  layout\="total, sizes, prev, pager, next, jumper"
  @current-change\="handleCurrentChange"
  @size-change\="handleSizeChange"
\></el-pagination\>

el-checkbox-group

多选框 el-checkbox形式编码

  

<el-checkbox-group v-model\="value"\>
  <el-checkbox :label\=""\>
    
  </el-checkbox\>
  <el-checkbox :label\=""\>
    
  </el-checkbox\>
</el-checkbox-group\>

el-checkbox

复选框组件

  

<el-checkbox v-model\="checked"\></el-checkbox\>

el-radio-group

单选框组件 el-radio形式编码

  

<el-radio-group v-model\="value"\>
  <el-radio :label\=""\>
    
  </el-radio\>
  <el-radio :label\=""\>
    
  </el-radio\>
</el-radio-group\>

el-radio

复选框组件

  

<el-radio v-model\="checked" :label\=""\></el-radio\>

el-badge

徽标数组件

  

<el-badge :value\="count"\>
  
</el-badge\>

el-calendar

日历组件

  

<el-calendar v-model\="value"\></el-calendar\>

el-image

图片组件

  

<el-image :src\="" :fit\=""\></el-image\>

el-backtop

返回顶部组件

  

<el-backtop target\=""\></el-backtop\>

el-card

卡片组件

  

<el-card\>
  <template slot\="header"\>
    
  </template\>
  
</el-card\>

el-carousel

走马灯组件

  

<el-carousel height\="400" autoplay :interval\="3000" @change\="onChange"\>
  <el-carousel-item\></el-carousel-item\>
  <el-carousel-item\></el-carousel-item\>
</el-carousel\>

el-carousel-item

走马灯子组件

  

<el-carousel-item\></el-carousel-item\>

el-switch

开关组件

  

<el-switch v-model\="value"\></el-switch\>

el-input

输入框组件

  

<el-input placeholder\="" v-model\="value"\></el-input\>

el-select

下拉框组件

  

<el-select v-model\="value" placeholder\=""\>
  <el-option
    v-for\="item in options"
    :key\="item.value"
    :label\="item.label"
    :value\="item.value"
  \></el-option\>
\></el-select\>

el-input-number

数字输入框组件

  

<el-input-number :min\="" :max\="" v-model\="value" :step\="1"\></el-input-number\>

el-avatar

头像组件

  

<el-avatar :size\="" :src\=""\></el-avatar\>

el-spin

加载中组件

  

<el-spin :size\="default"\></el-spin\>

el-divider

分割线组件

  

<el-divider\></el-divider\>

el-skeleton

骨架屏组件

  

<el-skeleton :rows\="10"\></el-skeleton\>

el-alert

警告提示组件

  

<el-alert type\="" title\="" closable\></el-alert\>

el-popconfirm

气泡二次确认组件

  

<el-popconfirm
  title\="确认吗？"
  confirm-button-text\="确认"
  cancel-button-text\="取消"
  @confirm\="confirm"
  @cancel\="cancel"
\>
  <el-button type\="link"\></el-button\>
</el-popconfirm\>

el-popover

气泡组件

  

<el-popover width\="200" title\="" content\="" trigger\="hover" placement\="bottom" \>
  
</el-popover\>

el-tooltip

文字提示组件

  

<el-tooltip effect\="dark" content\="" placement\="bottom"\>
  
</el-tooltip\>

el-tag

标签组件

  

<el-tag closable type\=""\></el-tag\>

el-slider

滑动输入条

  

<el-slider v-model\="value" :step\="1"\></el-slider\>

el-progress

进度条组件

  

<el-progress :percentage\="" :status\=""\></el-progress\>

el-time-select

时间选择器

  

<el-time-select v-model\="value" :picker-options\="{ start: '00:00', step: '00:15', end: '24:00' }" placeholder\=""\></el-time-select\>

el-time-picker

时间选择器

  

<el-time-picker v-model\="value" value-format\="HH:mm:ss" @change\="getTime"\></el-time-picker\>

el-date-picker

日期范围选择器

  

<el-date-picker type\="datetimerange" v-model\="value" format\="YYYY-MM-DD HH:mm:ss" @change\="getDateRange"\></el-date-picker\>

el-rate

评分组件

  

<el-rate v-model\="value" :max\="5" allow-half\></el-rate\>

el-color-picker

颜色选择器

  

<el-color-picker v-model\="color" show-alpha\></el-color-picker\>

el-steps

步骤条组件

  

<el-steps :active\="current" direction\="horizontal" :status\="status"\>
  <el-step title\="标题" description\="描述"\></el-step\>
  <el-step\>
    <template slot\="title"\>
      
    </template\>
    <template slot\="description"\>
      
    </template\>
  </el-step\>
</el-steps\>

el-dialog

弹窗组件

  

<el-dialog title\="title" width\="600px" :visible.sync\="visible" @close\="onClose"\>
  <span slot\="footer" class\="dialog-footer"\>
    <el-button size\="small" @click\="handleCancel"\>取 消</el-button\>
    <el-button size\="small" type\="primary" @click\="handleOk" :loading\="confirmLoading"\>确 定</el-button\>
  </span\>
</el-dialog\>

el-transfer

穿梭框组件

  

<el-transfer :data\="data" v-model\="value"\></el-transfer\>

el-cascader

级联选择组件

  

<el-cascader v-model\="value" :options\="options" placeholder\="Please select" @change\="onChange"\></el-cascader\>

el-cascader-panel

级联选择面板组件

  

<el-cascader-panel :options\="options"\></el-cascader-panel\>

el-upload

上传文件组件

  

<el-upload
  name\="file"
  multiple
  :file-list\="fileList"
  :action\="uploadUrl"
  :on-preview\="preview"
  :on-remove\="remove"
  :on-exceed\="handleExceed"
  :before-remove\="beforeRemove"
  :limit\="3"
\>
  <el-button size\="small" type\="primary"\>点击上传</el-button\>
  <div slot\="tip" class\="el-upload\_\_tip"\>只能上传jpg/png文件，且不超过500kb</div\>
</el-upload\>

el-drawer

抽屉组件

  

<el-drawer
  title\="Title"
  direction\="rtl"
  show-close
  :visible.sync\="visible"
  :before-close\="close"
\>
  <p\></p\>
</el-drawer\>

el-tree

树形结构组件

  

<el-tree :data\="data" :props\="defaultProps" @node-click\="handleNodeClick"\></el-tree\>

el-tree-select

树形选择器组件

  

<el-tree-select
  v-model\="value"
  :data\="data"
  :render-after-expand\="true"
  show-checkbox
\>

el-page-header

页头组件

  

<el-page-header content\="" @back\="\\$router.back()"\></el-page-header\>

el-table

表格组件

  

<el-table
  :data\="data"
  :scroll\="{ x: 1200 }"
  :loading\="loading"
  bordered
  rowKey\="id"
  @change\="changePage"
\>
  <el-table-column label\="id" prop\="id" width\="100"\></el-table-column\>
  <el-table-column label\="name"\>
    <template slot-scope\="scope"\>
      <span\>{{ scope.\\$index + 1 }}、{{ scope.row.name }}</span\>
    </template\>
  </el-table-column\>
  <el-table-column label\="操作" width\="100" fixed\="right"\>
    <template slot-scope\="scope"\>
      <el-button type\="link" @click\="toDo(scope.row)"\>修改</el-button\>
    </template\>
  </el-table-column\>
</el-table\>

el-form

表单组件

  

<el-form ref\="form" :model\="form" :rules\="rules" label-width\="80px"\>
  <el-form-item label\="姓名" prop\="name"\>
    <el-input placeholder\="请填写姓名" :maxLength\="20" v-model\="form.name"\></el-input\>
  </el-form-item\>
  <el-form-item label\="性别" prop\="sex"\>
    <el-select placeholder\="请选择性别" v-model\="form.sex"\></el-select\>
  </el-form-item\>
</el-form\>

el-form-item

表单子组件

  

<el-form-item label\="" prop\=""\>
  
</el-form-item\>

el-row

栅格布局组件

  

<el-row :gutter\="0"\>
  <el-col :span\="12"\></el-col\>
  <el-col :span\="12"\></el-col\>
</el-row\>

el-col

栅格布局子组件

  

<el-col :span\=""\><el-col\>
