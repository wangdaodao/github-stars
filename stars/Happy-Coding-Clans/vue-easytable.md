---
project: vue-easytable
stars: 3769
description: A  powerful data table based on vuejs. You can use  it as data grid、Microsoft Excel or Google sheets. It supports virtual scroll、cell edit etc. 
url: https://github.com/Happy-Coding-Clans/vue-easytable
---

vue-easytable
=============

**English** | 中文

Sponsors
--------

Support this project by becoming a sponsor. Your logo or name will show up here with a link you provided. Become a sponsor

### Gold Sponsor

### Silver Sponsor

### Generous Sponsor

Introduction
------------

A powerful data table based on vue2.x You can use it as data grid、Microsoft Excel or Google sheets. It supports virtual scroll、cell edit etc.

Characteristics
---------------

-   Support 300000 rows of data display through virtual scroll
-   Free forever. Of course, you can also choose to donate

API & Examples
--------------

-   Official documents (Github)
-   Official documents (China)

Features
--------

**Base components**

-   Loading component
-   Pagination component
-   Contextmenu component
-   Icon component
-   Locale component

**Table component**

-   Internationalization
-   Theme Custom & Built in theme
-   Virtual Scroll
-   Column Fixed
-   Column Hidden
-   Header Fixed
-   Header Grouping
-   Filter
-   Sort
-   Column Resize
-   Cell Style
-   Cell Custom
-   Cell Span
-   Cell Selection(keyboard operation)
-   Cell Autofill
-   Cell Edit
-   Clipboard
-   Contextmenu
-   Cell Ellipsis
-   Row Radio
-   Row Checkbox
-   Row Expand
-   Row Style
-   Footer Summary
-   Event Custom
-   More

If there is no feature you want, Please Tell Us

Install
-------

```
npm install vue-easytable
```

or

```
yarn add vue-easytable
```

Usage
-----

Write the following in main.js:

import Vue from "vue";
import "vue-easytable/libs/theme-default/index.css";
import VueEasytable from "vue-easytable";

Vue.use(VueEasytable);

new Vue({
    el: "#app",
    render: (h) \=> h(App),
});

Example:

<template\>
  <ve-table :columns\="columns" :table\-data\="tableData" /\>
</template\>

<script\>
  export default {
    data() {
      return {
        columns: \[
          { field: "name", key: "a", title: "Name", align: "center" },
          { field: "date", key: "b", title: "Date", align: "left" },
          { field: "hobby", key: "c", title: "Hobby", align: "right" },
          { field: "address", key: "d", title: "Address" },
        \],
        tableData: \[
          {
            name: "John",
            date: "1900-05-20",
            hobby: "coding and coding repeat",
            address: "No.1 Century Avenue, Shanghai",
          },
          {
            name: "Dickerson",
            date: "1910-06-20",
            hobby: "coding and coding repeat",
            address: "No.1 Century Avenue, Beijing",
          },
          {
            name: "Larsen",
            date: "2000-07-20",
            hobby: "coding and coding repeat",
            address: "No.1 Century Avenue, Chongqing",
          },
          {
            name: "Geneva",
            date: "2010-08-20",
            hobby: "coding and coding repeat",
            address: "No.1 Century Avenue, Xiamen",
          },
          {
            name: "Jami",
            date: "2020-09-20",
            hobby: "coding and coding repeat",
            address: "No.1 Century Avenue, Shenzhen",
          },
        \],
      };
    },
  };
</script\>

Todo List
---------

What are we doing

Environment Support
-------------------

-   Modern browser and ie11 and above

  
IE / Edge

  
Firefox

  
Chrome

  
Safari

  
Opera

IE11, Edge

last 2 versions

last 2 versions

last 2 versions

last 2 versions

How to contribute
-----------------

If you want to contribute,just create a Pull Request

Contributors
------------

Thanks to the following friends for their contributions 🙏

Discussion group
----------------

-   Join In Gitter Chat Room
-   Join In Discord Chat Room

License
-------

http://www.opensource.org/licenses/mit-license.php
