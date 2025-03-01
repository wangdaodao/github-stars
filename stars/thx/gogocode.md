---
project: gogocode
stars: 5782
description: GoGoCode is a transformer for JavaScript/Typescript/HTML based on AST but providing a more intuitive API.
url: https://github.com/thx/gogocode
---

详细文档点击这里

What is GoGoCode?
-----------------

中文 README

GoGoCode is a transformer for JavaScript/Typescript/HTML based on AST but providing an intuitive API:

-   A jQuery-like API to select and transform AST.
-   A Regex-like syntax to match and replace code.

Learn more at GoGoCode Document

Intro
-----

Let's show you how to select and modify code with our API

### In

const a \= 1;
const b \= 2;

### Transform With GoGoCode

const $ \= require('gogocode');
const script \= $(source);
// use $\_$ as a wildcard to match AST element at any position you want
const aAssignment \= script.find('const a = $\_$');
// get matched AST element value
const aValue \= aAssignment.match?.\[0\]?.\[0\]?.value;
// replace AST as same as replace a string
// but ignore code format (space、indent or linebreak)
script.replace('const b = $\_$', \`const b = ${aValue}\`);
// generate ast to string
const outCode \= script.generate();

### Out

const a \= 1;
const b \= 1;

Related Project
---------------

Project

Description

gogocode-plugin-vue

transform a project from vue2 to vue3

gogocode-plugin-element

transform a project from ElementUI to ElementPlus

gogocode-cli

command-line tool for gogocode

gogocode-playground

test gogocode at browser instantly

gogocode-vscode

refactor your project with gogocode in vscode

Support
-------

-   issues
-   Ding Group：34266233
-   QQ Group：735216094

License
-------

MIT
