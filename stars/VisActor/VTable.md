---
project: VTable
stars: 2939
description: VTable is not just a high-performance multidimensional data analysis table, but also a grid artist that creates art between rows and columns.
url: https://github.com/VisActor/VTable
---

VTable
======

VTable is not just a high-performance multidimensional data analysis table, but also a grid artist that creates art between rows and columns.

Introduction • demo • Tutorial • API•

English | 简体中文 | 日本語

（video）

Introduction
============

VTable is based on visual rendering engine VRender.

The core capabilities are as follows:

1.  Extreme performance: Supports fast computation and rendering of millions of data points.
2.  Multidimensional analysis: Automatically analyzes and presents multidimensional data.
3.  Strong expressiveness: Provides flexible and powerful graphic capabilities, seamlessly integrating with charts of VChart.

Repository Introduction
=======================

This repository includes the following packages:

1.  packages/vtable: The core code repository of VTable
2.  packages/vtable-gantt: Gantt chart component code
3.  packages/vtable-editors: Table editor component code
4.  packages/vtable-export: Table export tool code
5.  packages/vtable-search: Table search tool code
6.  packages/react-vtable: React version of the table component
7.  packages/vue-vtable: Vue version of the table component
8.  docs: Include VTable site tutorials, demos,apis and options, and also contains all Chinese and English documents.

Usage
=====

Installation
------------

npm package

// npm
npm install @visactor/vtable

// yarn
yarn add @visactor/vtable

Quick Start
-----------

// this demo you can run on codesanbox https://codesandbox.io/s/vtable-simple-demo-g8q738
import \* as VTable from '@visactor/vtable';

const columns \= \[
  {
    field: 'Order ID',
    caption: 'Order ID'
  },
  {
    field: 'Customer ID',
    caption: 'Customer ID'
  },
  {
    field: 'Product Name',
    caption: 'Product Name'
  },
  {
    field: 'Sales',
    caption: 'Sales'
  },
  {
    field: 'Profit',
    caption: 'Profit'
  }
\];

const option \= {
  container: document.getElementById(CONTAINER\_ID),
  records: \[
    {
      'Order ID': 'CA-2018-156720',
      'Customer ID': 'JM-15580',
      'Product Name': 'Bagged Rubber Bands',
      Sales: '3.024',
      Profit: '-0.605'
    },
    {
      'Order ID': 'CA-2018-115427',
      'Customer ID': 'EB-13975',
      'Product Name': 'GBC Binding covers',
      Sales: '20.72',
      Profit: '6.475'
    }
    // ...
  \],
  columns
};
const tableInstance \= new VTable.ListTable(option);

More demos and detailed tutorials

⌨️ Development
==============

First of all, please install @microsoft/rush

$ npm i --global @microsoft/rush

Then clone locally:

# clone
$ git clone git@github.com:VisActor/VTable.git
$ cd VTable
# install dependencies
$ rush update
# start vtable demo
$ cd packages/vtable
# execute in file path: ./packages/vtable
$ rushx demo
# start site development server, execute in file path: ./
$ rush docs
# after execut git commit, please run the following command to update the change log. Please execute in file path: ./
$ rush change-all

📖 Documents
============

After installation & clone & update, run docs to preview VTable documents locally.

# start vtable document server. execute in file path: ./
$ rush update
$ rush build
$ rush docs

If you meet dependency problems
===============================

$ rush purge
$ rush update

🔗 Related Links
----------------

-   Official website
-   Usage Trend

💫 Ecosystem
============

Project

Description

React-VTable

VTable in React component

⭐️ Star History
===============

🤝 Contribution
===============

If you would like to contribute, please read the Code of Conduct and Guide first。

Small streams converge to make great rivers and seas!

License
=======

MIT License
