---
project: vue-digital-transform
stars: 60
description: A vue component for better digital transform animation
url: https://github.com/DakerHub/vue-digital-transform
---

vue-digital-transform
=====================

中文文档

Make your changes of digtals more funny. vue-digital-transform

Install
-------

npm install vue-digital-transform

Example
-------

<template\>
  <DigitalTransform :value\="num" dislocation :interval\="200"\></DigitalTransform\>
</template\>

import DigitalTransform from "vue-digital-transform";

export default {
  components: {
    DigitalTransform,
  },
  data() {
    return {
      num: 0,
    };
  },
};

Config
------

prop

type

description

default

value

Number,String

Digitals. Only allow \[0-9.,\]

undefined

dislocation

Boolean

Whether every singal digital transforms in diffrent duration.

false

interval

Number

The time that transform spends.（ms）

500

useGrouping (v1.1.0+)

Boolean

Whether group the digital or not. (Only when value is pure num)

false

Contribution
------------

Any contribution to the code or any part of the documentation and any idea and/or suggestion are very welcome.

Just pull requests!

Licence
-------

MIT License
