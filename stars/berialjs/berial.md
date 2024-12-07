---
project: berial
stars: 521
description: 😈 Simple micro-front-end framework.
url: https://github.com/berialjs/berial
---

Berial
======

👿 Simple micro-front-end framework.

### Why Berial

Berial is a new approach to a popular idea: build a javascript framework for front-end microservices.

There are any wonderful features of it, such as Asynchronous rendering pipeline, Web components (shadow DOM + scoped css), JavaScript sandbox (Proxy).

Note: diffence form fre, Berial will pay attention to business value.

### Use

<one-app\></one-app\>
<two-app\></two-app\>

<script type\="module"\>
  import { register } from 'berial'
  register(\[{
    name: 'one-app',
    url: '1.html',
    allowList: \['fre'\] // 沙箱白名单
  },{
    name: 'two-app',
    scripts: \['2.js'\], // 可选
    styles: \['2.css'\]
  }\])
</script\>

### License

MIT ©yisar ©h-a-n-a
