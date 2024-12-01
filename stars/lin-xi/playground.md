---
project: playground
stars: 54
description: UI framework playground
url: https://github.com/lin-xi/playground
---

* * *

UI framework playground
=======================

Config the component with the mouse through WYSWYG， have fun！

-   config library.config.js
-   npm run dev
-   open http://localhost:8800

UI framework configaration
--------------------------

**library.config.js**

module.exports \= {
  name: 'ELEMENT',  // UI framework Name
  url: 'https://unpkg.com/element-ui/lib/index.js',  // UI framework UMD module path
  style: 'https://unpkg.com/element-ui/lib/theme-chalk/index.css',    // UI framework theme
  components: \[
    {
      name: 'Button',     //Componnet Name
      title: '按钮',       //Decription Name
      image: '',          //Icon
      property: \[         //Componnet props
        {
          name: 'size',         //props name
          title: '尺寸',         //props description name
          type: 'enum',         //type, text, number, object, enum, switch are supported
          values: \[             //if type is enum, values are enumerated options
            {label: '中', value: 'medium'},
            {label: '小', value: 'small'},
            {label: '迷你', value: 'mini'},
          \],
          value: 'medium'       //default value of props
        },
      \]
    }
    ...
  \]
}

### Component Configaration

名称

描述

默认值

可选值

name

属性名称

\-

\-

title

属性描述

\-

\-

type

类型

\-

text 文本型  
number 数字型  
object 对象  
enum 枚举型  
switch 布尔型

value

默认值

\-

\-

values

枚举的值，只有当类型为enum是有效

\-

\-

Screenshot
----------

### Element
