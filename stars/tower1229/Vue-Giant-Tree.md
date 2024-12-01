---
project: Vue-Giant-Tree
stars: 663
description: 🌳 巨树：基于ztree封装的Vue树形组件，轻松实现海量数据的高性能渲染。
url: https://github.com/tower1229/Vue-Giant-Tree
---

vue-giant-tree
==============

> 🌳 巨树：基于ztree封装的 Vue 树形组件，轻松实现海量数据的高性能渲染。

Vue3.x 版本在这

为什么需要 vue-giant-tree
--------------------

Vue 的数据监听机制决定了在大数据量场景下的渲染性能非常低下，基于 Vue 实现的常规树组件几乎无法胜任上万条数据的高性能渲染，在 IE 浏览器（即便是 IE11）中很容易导致页面卡死甚至浏览器崩溃。

> 不服气可以试试这份数据 big-tree.json

为了摆脱数据监听，只能放弃通过 Vue 渲染，采用常规 DOM 操作的方式。在这个领域ztree是当之无愧最成熟的方案，因此 vue-giant-tree 直接基于 ztree 做上层封装，以组件的形式将 ztree 的配置和事件暴露出来，使其可以方便的在 Vue 项目中安装使用。

vue-giant-tree 仅仅是给 ztree 套了一层 Vue 组件的壳，顺便提供了一套更现代化的皮肤，因为主打大数据量场景，所以取名**巨树**。

ztree 在性能优化方面已经做到了近乎极致，感谢 ztree 作者的工作，向您致敬！

安装
--

npm i vue-giant-tree --save

**注意：组件依赖 jQuery，务必在页面中提前加载 jQuery**

```
<script src="https://code.jquery.com/jquery-3.6.0.min.js"
    integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
```

使用
--

in script:

import tree from "vue-giant-tree";

export default {
	components: {
          tree
	},
	data() {
		return {
			nodes: \[
                    { id:1, pid:0, name:"随意勾选 1", open:true},
                    { id:11, pid:1, name:"随意勾选 1-1", open:true},
                    { id:111, pid:11, name:"随意勾选 1-1-1"},
                    { id:112, pid:11, name:"随意勾选 1-1-2"},
                    { id:12, pid:1, name:"随意勾选 1-2", open:true},
                    { id:121, pid:12, name:"随意勾选 1-2-1"},
                    { id:122, pid:12, name:"随意勾选 1-2-2"},
                    { id:2, pid:0, name:"随意勾选 2", checked:true, open:true},
                    { id:21, pid:2, name:"随意勾选 2-1"},
                    { id:22, pid:2, name:"随意勾选 2-2", open:true},
                    { id:221, pid:22, name:"随意勾选 2-2-1", checked:true},
                    { id:222, pid:22, name:"随意勾选 2-2-2"},
                    { id:23, pid:2, name:"随意勾选 2-3"}
                \]
		}
	},
    methods: {
        onClick(evt, treeId, treeNode) {

        },
        onCheck(evt, treeId, treeNode) {

        },
        handleCreated(ztreeObj) {

        }
    }
	...

in template:

<tree
  :nodes\="nodes"
  @onClick\="onClick"
  @onCheck\="onCheck"
  @onCreated\="handleCreated"
/>

属性
--

参数

说明

类型

默认值

setting

ztree 配置

Object

`{view: {showIcon: false}}`

nodes

ztree 数据

Array

`[]`

事件
--

完全移植zTree API中`callback`支持的事件，除了：

-   不支持所有 `before` 开头的事件。这类事件的主要作用是根据返回值决定是否阻止后续的`on`事件，这种判断可以在`on`事件中实现；当然，你也可以通过`setting.callback.beforeXXX`自行配置
-   不支持 `onNodeCreated` 事件。因为在大数据量下很耗性能，如果需要可以通过 `setting.callback.onNodeCreated` 自行传入
-   增加 `onCreated` 事件。每次实例初始化完成时触发，回调参数接收 ztree 实例，通过 ztree 实例可以使用所有实例方法

事件名称

说明

onAsyncError

参考 zTree API

onAsyncSuccess

参考 zTree API

onCheck

参考 zTree API

onClick

参考 zTree API

onCollapse

参考 zTree API

onDblClick

参考 zTree API

onDrag

参考 zTree API

onDragMove

参考 zTree API

onDrop

参考 zTree API

onExpand

参考 zTree API

onMouseDown

参考 zTree API

onMouseUp

参考 zTree API

onRemove

参考 zTree API

onRename

参考 zTree API

onRightClick

参考 zTree API

onCreated

初始化渲染完成后触发，回调参数接收 ztree 实例

扩展
--

zTree 没有提供给整个实例更新数据的方法，vue-giant-tree 基于 Vue 的组件通信机制扩展实现了_响应式数据_特性，只要`nodes`的值发生变化，ztree 实例就会随之更新。

项目 DEMO里演示了 vue-giant-tree 的响应式数据特性。

演示
--

-   线上演示：

> http://refined-x.com/Vue-Giant-Tree/

-   本地演示：

```
npm i
npm run serve
```

License
-------

MIT

Copyright (c) 2019-present, 前端路上
