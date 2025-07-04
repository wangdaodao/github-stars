---
project: vue-jsplumb-editor
stars: 242
description: 基于vue、jsPlumb参照阿里pai平台
url: https://github.com/fangyang921017/vue-jsplumb-editor
---

vue-jsplumb-editor
==================

在线预览

功能点
---

#### 菜单节点区域

-   从菜单中拖动一个节点到主设计区域，可放置该节点
-   按节点类型组织节点

#### 主设计区域

-   操作可撤销
-   背景的平移和缩放
-   可接收从菜单中拖入的节点
-   拖入的节点会根据当前的节点信息生成对应的端点（用于拖出连线）
-   生成的端点分两种类型：源端点和目标端点，应在样式上作区分
-   源端点放置在节点bottom位置，目标节点防止在节点的top位置（便于从上往下拖出连接线）
-   所有节点可通过拖拽移动位置
-   所有节点和连接线可删除
-   所有节点和端点在鼠标悬浮需要有tooltip框来提示节点或端点信息
-   所有节点、端点和连接线在鼠标悬浮时需要设置不同的样式
-   所有节点和连接线可被选中
-   操作实时保存数据
-   导入数据生成流程图

#### 节点配置区域

-   在设计区域选中节点时，节点配置区域会显示一个对应的节点配置面板
-   不同节点应拥有对应的节点配置面板
-   节点面板用来展示和配置节点属性

#### 右键菜单功能

-   节点：
    -   复制
    -   删除
    -   查看数据
    -   重命名
-   连接线：
    -   删除
-   背景：
    -   粘贴

安装依赖
----

```
npm install
```

开发模式
----

```
npm run serve
```

编译生产代码
------

```
npm run build
```
