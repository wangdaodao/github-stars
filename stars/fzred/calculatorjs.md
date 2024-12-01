---
project: calculatorjs
stars: 192
description: Accurately arithmetic library. 解决Javascript浮点运算精度问题。
url: https://github.com/fzred/calculatorjs
---

Calculatorjs
============

中文文档

\> 2.1 + 2.2
4.300000000000001
\> calc(' 2.1 + 2.2 ')
4.3

Usage
-----

Using NPM:

npm install --save calculatorjs

In Node.js or Browser:

const calc \= require('calculatorjs')

console.log(calc(' 0.1\*(0.1+0.1) '))

Direct `<script>` Include

<script src\="calc.js"\></script\>
<script\>
    console.log(calc(' 0.1 \* (0.1 + 0.1) '))
</script\>

DOC
---

### Arithmetic expression

calc(' 1 + (2 \* 3 - 1) / 4 \* -1 ')

Support **+** **\-** **\*** **/** **(** **)** **minus**

### API

calc.add(0.1, 0.2) // 0.3
calc.sub(0.1, 0.2) // -0.1
calc.mul(0.1, 0.2) // 0.02
calc.div(0.1, 0.2) // 0.5
calc.round(0.555, 2) // 0.56

License
-------

Distributed under MIT License.
