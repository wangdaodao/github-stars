---
project: xe-utils
stars: 645
description: javascript 函数库、工具类
url: https://github.com/x-extends/xe-utils
---

xe-utils
========

简体中文 | English

JavaScript 函数库、工具类

Browser Support
---------------

7+ ✔

Latest ✔

Latest ✔

Latest ✔

Latest ✔

6+ ✔

Docs
----

查看文档

Installing
----------

npm install xe-utils

Using nodejs

const XEUtils \= require('xe-utils')

Get on unpkg and cdnjs

<script src\="https://cdn.jsdelivr.net/npm/xe-utils"\></script\>

### Import all methods

import XEUtils from 'xe-utils'

XEUtils.toDateString(Date.now())
// 2018-01-01 10:30:28
XEUtils.toStringDate('2018-01-01 10:30:00')
// Mon Jan 01 2018 10:30:00 GMT+0800 (中国标准时间)

Import on demand
----------------

这样按需引入方法，可以使体积达到最小  
单个导入，包的大小 gzip >≈ 60B+，按需导入

import each from 'xe-utils/each'
import toDateString from 'xe-utils/toDateString'

each({ a: 11, b: 22, c: 33 }, function (item, key){
  console.log(item)
})
// 11
// 22
// 33
toDateString(Date.now(), 'yyyy-MM-dd HH:mm:ss')
// 2018-01-01 10:30:28

import XEUtils from 'xe-utils/ctor'
import each from 'xe-utils/each'
import toDateString from 'xe-utils/toDateString'
import toFixedNumber from 'xe-utils/toFixedNumber'

XEUtils.mixin({
  each,
  toDateString,
  toFixedNumber
})
XEUtils.toDateString(Date.now(), 'yyyy-MM-dd HH:mm:ss')
// 2018-01-01 10:30:28

按功能导入所有方法

import XEUtils from 'xe-utils/ctor'
import objectMethods from 'xe-utils/object'
import arrayMethods from 'xe-utils/array'
import baseMethods from 'xe-utils/base'
import numberMethods from 'xe-utils/number'
import dateMethods from 'xe-utils/date'
import stringMethods from 'xe-utils/string'
import functionMethods from 'xe-utils/function'
import urlMethods from 'xe-utils/url'
import webMethods from 'xe-utils/web'

XEUtils.mixin(
  // Object
  objectMethods,
  // Array
  arrayMethods,
  // Base
  baseMethods,
  // Number
  numberMethods,
  // Date
  dateMethods,
  // String
  stringMethods,
  // Function
  functionMethods,
  // URL
  urlMethods,
  // Web
  webMethods
)

Contributors
------------

Thank you to everyone who contributed to this project.

License
-------

MIT © 2017-present, Xu Liangzhan
