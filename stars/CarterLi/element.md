---
project: element
stars: 1
description: A Vue.js 2.0 UI Toolkit for Web
url: https://github.com/CarterLi/element
---

The offical version seemed to be no longer maintained, we forked the offical repo to provide various bugfixes and improvements, for our internal use.

The modification may or may not introduce unknown issues. USE IT AT YOUR OWN RISK!

NPM repo: https://www.npmjs.com/element-ui-eoi

Usage:

$ npm i element-ui-eoi

// vue.config.js
module.exports \= {
  configureWebpack: {
    resolve: {
      alias: {
        'element-ui': 'element-ui-eoi',
      },
    },
  },
};

// tsconfig.json
{
  "compilerOptions": {
    "paths": {
      "element-ui": \["node\_modules/element-ui-eoi"\],
      "element-ui/\*": \["node\_modules/element-ui-eoi/\*"\]
    }
  }
}

* * *

  

> A Vue.js 2.0 UI Toolkit for Web.

Element will stay with Vue 2.x

For Vue 3.0, we recommend using Element Plus from the same team

Links
-----

-   Homepage and documentation
    -   International users
    -   Chinese users
    -   Spanish users
    -   French users
-   awesome-element
-   FAQ
-   Vue.js 3.0 migration
-   Customize theme
-   Preview and generate theme online
-   Element for React
-   Element for Angular
-   Atom helper
-   Visual Studio Code helper
-   Starter kit
    -   element-starter
    -   element-in-laravel-starter
-   Design resources
-   Gitter
    -   International users
    -   Chinese users

Install
-------

npm install element-ui -S

Quick Start
-----------

import Vue from 'vue'
import Element from 'element-ui'

Vue.use(Element)

// or
import {
  Select,
  Button
  // ...
} from 'element-ui'

Vue.component(Select.name, Select)
Vue.component(Button.name, Button)

For more information, please refer to Quick Start in our documentation.

Browser Support
---------------

Modern browsers and Internet Explorer 10+.

Development
-----------

Skip this part if you just want to use Element.

For those who are interested in contributing to Element, please refer to our contributing guide (中文 | English | Español | Français) to see how to run this project.

Changelog
---------

Detailed changes for each release are documented in the release notes.

FAQ
---

We have collected some frequently asked questions. Before reporting an issue, please search if the FAQ has the answer to your problem.

Contribution
------------

Please make sure to read the contributing guide (中文 | English | Español | Français) before making a pull request.

Special Thanks
--------------

English documentation is brought to you by SwiftGG Translation Team:

-   raychenfj
-   kevin
-   曾小涛
-   湾仔王二
-   BlooDLine
-   陈铭嘉
-   千叶知风
-   梁杰
-   Changing
-   mmoaay

Spanish documentation is made possible by these community developers:

-   adavie1
-   carmencitaqiu
-   coderdiaz
-   fedegar33
-   Gonzalo2310
-   lesterbx
-   ProgramerGuy
-   SantiagoGdaR
-   sigfriedCub1990
-   thechosenjuan

French documentation is made possible by these community developers:

-   smalesys
-   blombard

Join Discussion Group
---------------------

Scan the QR code using Dingtalk App to join in discussion group :

LICENSE
-------

MIT
