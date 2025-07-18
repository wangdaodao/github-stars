---
project: vue-d3-charts
stars: 100
description: D3 charts for Vue
url: https://github.com/Saigesp/vue-d3-charts
---

vue-d3-charts
=============

**The development of this library is frozen for now. When I have more time I will continue its development. Any contribution is welcome**

Simply yet configurable charts build with D3.

See documentation and demo page.

### Install

npm i vue-d3-charts --save

### Usage

Import:

import { D3BarChart } from 'vue-d3-charts';

Template:

<D3BarChart :config\="config" :datum\="data"\></D3BarChart\>

Configuration and data:

// data
data \= \[{
  name: "Lorem",
  total: 30
},{
  name: "Ipsum",
  total: 21
},{
  name: "Dolor",
  total: 20
}\]

// Configuration
config \= {
  key: "name",
  value: "total",
  color: "steelblue",
}

### Contributing

See contribution guide.

### License

This repository is available under **GNU LESSER GENERAL PUBLIC LICENSE v2.1** (LGPL). See details.
