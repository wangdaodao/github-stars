---
project: fish-ui
stars: 906
description: A Vue.js 2.0 UI Toolkit for Web
url: https://github.com/myliang/fish-ui
---

Fish-ui
=======

> A Vue.js 2.0 UI Toolkit for Web.

Install
-------

npm install less less-loader -S
npm install fish-ui -S

Quick Start
-----------

### google font & font-awesome

<link rel\="stylesheet" href\="https://cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.css"/>
<link rel\="stylesheet" href\="https://fonts.proxy.ustclug.org/css?family=Lato:400,700,400italic,700italic&subset=latin"/>

### Import all components

import Vue from 'vue'
import FishUI from 'fish-ui'

Vue.use(FishUI)

### Manually import

import 'fish-ui/styles/button.less'
import Button from 'fish-ui/src/components/Button.vue'

Vue.component(Button.name, Button)

And if you start with vue-webpack-boilerplate by vue-cli

Demo
----

https://myliang.github.io/fish-ui/

Features
--------

-   Equip with Vue.js, Moment, Vue-Router, ES6 & Babel 6
-   Cool with Webpack 2.0 & Vue Loader
-   Semantic CSS Components
-   Stylesheets in Less

Components
----------

-   BackTop
-   Button
-   Buttons
-   Calendar
-   Card
-   Carousel
-   CarouselItem
-   Cascader
-   Checkbox
-   Checkboxes
-   Col
-   DatePicker
-   Dropdown
-   Field
-   Fields
-   Form
-   Input
-   InputNumber
-   Layout
-   Menu
-   Message
-   Modal
-   Option
-   Pagination
-   Radio
-   Radios
-   Row
-   Select
-   Steps
-   Step
-   Submenu
-   Table
-   TabPane
-   Tabs
-   Tag
-   Tags
-   TimePicker
-   Upload
-   Tree
-   Tree Select
-   Transfer
-   Divider
-   Image
-   Timeline

Browser Support
---------------

Modern browsers and Internet Explorer 9+(no test).

Thanks to
---------

-   semantic-ui

LICENSE
-------

MIT
