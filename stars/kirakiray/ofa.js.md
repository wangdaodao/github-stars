---
project: ofa.js
stars: 740
description: No-build MVVM front-end framework, Progressive micro front-end framework.
url: https://github.com/kirakiray/ofa.js
---

ofa.js
======

Official Documentation / 官方文档 / 官方文檔 / Sitio oficial de documentación / 公式ドキュメントサイト / 공식 문서 사이트

What is ofa.js?
---------------

ofa.js is a library for building web interfaces and applications. You can start developing with it by including a `script` tag in your HTML, making it one of the best alternatives to jQuery.

ofa.js can be used as a library like jQuery and can also be employed for developing large web applications similar to React, Vue, and Angular. Its introduction eliminates the need for tools like npm, Node.js, and webpack that are unrelated to interface development, making web interface development easier and more efficient.

How to Use
----------

To start using ofa.js, simply add a reference to ofa.js in your HTML file.

<script src\="https://cdn.jsdelivr.net/gh/kirakiray/ofa.js@4.5.32/dist/ofa.min.js"\></script\>

User Experience
---------------

You can try out specific user experiences here.

The core idea of ofa.js is to simplify the encapsulation of web components. Traditional web component encapsulation requires a substantial amount of knowledge, which has led to slower development in the web components field. The Web Components v1 standard, for example, has been supported since 2018 but is still not widely adopted.

With ofa.js, however, you can quickly create a component by just creating an HTML file. Others can reference this component with a simple tag without the need for a pre-bundling process, significantly reducing the learning curve and allowing you to focus on application requirements.

<!-- my-component.html -->
<!-- Encapsulated component code written in an HTML file -->
<template component\>
    ...
</template\>

<!-- Using the encapsulated component -->
<script src\="https://cdn.jsdelivr.net/gh/kirakiray/ofa.js@4.5.32/dist/ofa.min.js"\></script\>
<l-m src\="./my-component.html"\></l-m\>
<my-component\>
    ...
</my-component\>

In addition, ofa.js also introduces template syntactic sugar similar to Angular and Vue, making it more efficient to work on web components.

Why Develop ofa.js?
-------------------

The development of ofa.js aims to eliminate unnecessary interference in frontend development by npm, Node.js, and webpack. These tools have increased the entry barrier for using frontend frameworks and components, making frontend development more complex. When developing complex frontend applications, a significant amount of time and effort is spent on learning and resolving issues related to Node.js and webpack.

> The author has worked with Vue and React for many years and initially thought that they were not convenient due to a lack of familiarity. However, with years of experience, the author gradually realized that they were genuinely inconvenient.

For example, for back-end developers who just want to create a clean and beautiful form page, they have to master some front-end basics (e.g., npm/nodejs/webpack/create-app-cli) before they can start building components using frameworks like React, Angular, or Vue. At this point, they may get frustrated and ask, "I just want a pretty page, why do I have to learn all this new stuff?" Or run into errors while fiddling with npm/nodejs/webpack and fall back to the jQuery forms they've used before. And now, there's ofa.js available, which is a great alternative to jQuery for such simple page needs.

The author believes that the original intention of Angular.js (v1) and jQuery was correct because they lowered the entry barrier. However, with the rise of Node.js and the introduction of pre-compilation, frontend development deviated. The author believes that frontend development should maintain JavaScript's instant execution feature instead of over-relying on pre-compilation. The author also appreciates Node.js's contributions to the community, as it has propelled the rapid development of JavaScript.

ofa.js is also a natural microfrontend framework, as you will discover when you use it.

License
-------

ofa.js is licensed under the MIT License.
