---
project: vue-table-optimize
stars: 63
description: table enhancement with the thousands of data rendering: add requestAnimationFrame and virtual scroll enhancement
url: https://github.com/kcikkick/vue-table-optimize
---

nk-table-demo
=============

Only study only, for the virtual scroll design,please refer the wiki, Vue - Table表格渲染上千数据优化

> Table enhancement with the thousands of data rendering: add common table body with Reflow, requestAnimationFrame and virtual scroll enhancement

Build Setup
-----------

# install dependencies
npm install

# serve with hot reload at localhost:7777
npm run dev

# build for production with minification
npm run build

Table Config
------------

-   `columnsConfig`: require property, Each column config
-   `data`: table data.
-   `filters(TBC)`: to filter table data.
-   `renderType` (default: `common`): display table body render type,VIRTUAL -> virtual scroll body; ANIMATION -> use window.requestAnimationFrame to render body with frame scroll.
-   `recordKey`: require property to optimize the table body to reuse the DOM elements.
-   `height` (default: `400`): display height of the table in integer number, including header and body.
-   `headerHeight` (default: `40`): display height of the header in integer number.
-   `recordHeight` (default: `36`): display height of the items in integer number.For virtual body scroll render,it used to calculate the scroll height and position.

#### columnsConfig

-   `title`: 列头显示文字
-   `key`: 对应列内容的字段名
-   `render`: 自定义渲染列，使用 Vue 的 Render 函数

License
-------

MIT
