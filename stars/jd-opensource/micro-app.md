---
project: micro-app
stars: 6135
description: A simple, efficient and powerful micro front-end framework. 一款简约、高效、功能强大的微前端框架
url: https://github.com/jd-opensource/micro-app
---

English｜简体中文｜Documentation｜Discussions｜WeChat

📖Introduction
==============

micro-app is a micro front-end framework launched by JD Retail. It renders based on webcomponent-like and realizes the micro front-end from component thinking, it aiming to reduce the difficulty of getting started and improve work efficiency.

It is the lowest cost framework for accessing micro front-end, and provides a series of perfect functions such as JS sandbox, style isolation, element isolation, preloading, resource address completion, plugin system, data communication and so on.

micro-app has no restrictions on the front-end framework, and any framework can be used as a base application to embed any type of micro application of the framework.

How to use
==========

Base application
----------------

**1、Install**

yarn add @micro-zoe/micro-app

**2、import at the entrance**

// main.js
import microApp from '@micro-zoe/micro-app'

microApp.start()

**3、Use components in page**

<!-- my-page.vue -->
<template\>
  <!-- 👇 name is the app name, url is the app address -->
  <micro-app name\='my-app' url\='http://localhost:3000/'\></micro-app\>
</template\>

Sub application
---------------

**Set cross-domain support in the headers of webpack-dev-server**

devServer: {
  headers: {
    'Access-Control-Allow-Origin': '\*',
  },
},

The above micro front-end rendering is completed, and the effect is as follows:

More detailed configuration can be viewed Documentation.

🤝 Contribution
===============

If you're interested in this project, you're welcome to mention pull request, and also welcome your "Star" ^\_^

### development

1、Clone

```
git clone https://github.com/jd-opensource/micro-app.git
```

2、Install dependencies

```
yarn bootstrap
```

3、Run project

```
yarn start
```

For more commands, see DEVELOP

FAQ
===

What are the advantages of micro-app? It is easy to use and low invasive. It only needs to change a small amount of code to access the micro front-end, and provides rich functions at the same time. How compatible? The micro-app relies on two newer APIs, CustomElements and Proxy.

For browsers that do not support CustomElements, they can be compatible by introducing polyfills. For details, please refer to: webcomponents/polyfills。

However, Proxy is not compatible for the time being, so the micro-app cannot be run on browsers that do not support Proxy.

Browser compatibility can be viewed: Can I Use

The general is as follows:

-   desktop: Except IE browser, other browsers are basically compatible.
-   mobile: ios10+、android5+

Must micro applications support cross-domain? yes!

If it is a development environment, you can set headers in webpack-dev-server to support cross-domain.

devServer: {
  headers: {
    'Access-Control-Allow-Origin': '\*',
  },
}

If it is a production environment, you can support cross-domain through Configuration nginx.

Does it support vite?

Yes, please see adapt vite for details.

Does it support ssr?

Yes, please see nextjs, nuxtjs for details.

Contributors
============

License
=======

MIT License
