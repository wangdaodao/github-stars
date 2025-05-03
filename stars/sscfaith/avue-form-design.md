---
project: avue-form-design
stars: 1271
description: 本项目是一款基于 Avue 的表单设计器，拖拽式操作让你快速构建一个表单。
url: https://github.com/sscfaith/avue-form-design
---

简介
--

Vue3版本，因Avue还存在部分bug，请慎重使用。

本项目是一款基于 Avue 的表单设计器，拖拽式操作让你快速构建一个表单。

🎉 基于Bladex的工作流插件已上市。授权地址  
表单设计器预览地址  
流程设计器预览地址  
工作流插件预览地址

文档及demo项目
---------

Wiki

依赖
--

element-ui 2.13.2+

$ npm i element-ui

@smallwei/avue 2.6.16+

$ npm i @smallwei/avue

或自行引入cdn

安装
--

### 组件

$ npm i @sscfaith/avue-form-design
或
$ yarn add @sscfaith/avue-form-design

### 源码

github or gitee

$ yarn
$ yarn serve

### html

详见examples

使用
--

```
import AvueFormDesign from '@sscfaith/avue-form-design'

Vue.use(AvueFormDesign)
```

```
<avue-form-design style="height: 86vh;"
                  :options="options"
                  storage
                  @submit="handleSubmit"></avue-form-design>
```

### 属性

参数

说明

类型

默认值

options

字段配置

Object/String

{ column: \[\] }

storage

开启本地存储功能，防止浏览器刷新丢失json

Boolean

false

asideLeftWidth

左工具栏宽度

String/Number

'270px'

asideRightWidth

右工具栏宽度

String/Number

'380px'

showAvueDoc（已废弃，请使用toolbar）

是否显示Avue文档

Boolean

false

showGithubStar

是否显示GitHub Star

Boolean

true

toolbar

顶部工具栏

Array

\['avue-doc', 'import', 'generate', 'preview', 'clear'\]

undoRedo

是否开启撤销重做功能

Boolean

true

includeFields

左侧展示字段

Array

fieldsConfig.js中配置的字段

customFields

自定义组件

Array

使用方法

### options字段配置

Avue文档

属性

说明

类型

可选值

默认值

column

Avue字段

Array

\-

\[\]

labelPosition

字段位置

String

'left'/'center'/'right'

\-

labelWidth

字段宽度

Number

\-

\-

gutter

字段间隔

Number

\-

0

menuBtn

表单按钮

Boolean

true/false

true

submitBtn

显示提交按钮

Boolean

true/false

true

submitText

提交按钮文本

String

\-

'提交'

emptyBtn

显示清空按钮

Boolean

true/false

true

emptyText

清空按钮文本

String

\-

'清空'

tabs

多分组转标签

Boolean

true/false

false

detail

详情模式

Boolean

true/false

false

readonly

全局只读

Boolean

true/false

false

disabled

全局禁用

Boolean

true/false

false

### 事件

名称

说明

回调参数

submit

生成json回调

当前配置的json

### 方法

名称

说明

参数

返回

getData

获取当前编辑器的JSON

type: 'string'/'json'

Promise

### 插槽

名称

说明

toolbar

顶部工具栏右侧插槽

toolbar-left

顶部工具栏左侧插槽

### Avue插件

#### 富文本

```
import AvueUeditor from 'avue-plugin-ueditor'

Vue.use(AvueUeditor)
```

打包
--

### 组件

$ yarn lib

### 源码

$ yarn build

捐赠
--

如果你觉得本项目帮助到你的话，可以给作者买杯咖啡。

License
-------

MIT
