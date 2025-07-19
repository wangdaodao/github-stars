---
project: vue2-waterfall
stars: 96
description: 😁 An AutoHeight Waterfall Component For Vue2
url: https://github.com/PLDaily/vue2-waterfall
---

vue2-waterfall
==============

访问中文版

Overview
--------

> An AutoHeight Waterfall Component For Vue2

demo

Install
-------

### Install vue2-waterfall

npm install vue2-waterfall

### Import vue2-waterfall

ES6/commonjs import style is supported.

// ES6
import {Waterfall, WaterfallItem} from 'vue2-waterfall';

// commonjs
const Waterfall \= require("vue2-waterfall").Waterfall;
const WaterfallItem \= require("vue2-waterfall").WaterfallItem;

or link as a `script` in an html file and access global variable `Vue2Waterfall`.

<script src\="dist/vue2-waterfall.js"\></script\>

Usage
-----

<Waterfall\>
  <WaterfallItem\>item1</WaterfallItem\>
  <WaterfallItem\>item2</WaterfallItem\>
  <WaterfallItem\>item3</WaterfallItem\>
  ...
</Waterfall\>

options
-------

Option

Description

default

type

options

masonry options

{}

Object

LICENSE
-------

MIT@PLDaily
