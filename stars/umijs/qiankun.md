---
project: qiankun
stars: 16340
description: 📦 🚀 Blazing fast, simple and complete solution for micro frontends.
url: https://github.com/umijs/qiankun
---

qiankun（乾坤）
===========

Warning

🚧 qiankun 3.0 is currently under active development. Check out the Roadmap for more details.

> In Chinese, `qian(乾)` means heaven and `kun(坤)` earth. `qiankun` is the universe.

Qiankun enables you and your teams to build next-generation and enterprise-ready web applications leveraging Micro Frontends. It is inspired by and based on single-spa.

🤔 Motivation
-------------

A quick recap about the concept of `Micro Frontends`:

> Techniques, strategies and recipes for building a **modern web app** with **multiple teams** using **different JavaScript frameworks**. — Micro Frontends

Qiankun was birthed internally in our group during the time web app development by distributed teams had turned to complete chaos. We faced every problem micro frontend was conceived to solve, so naturally, it became part of our solution.

The path was never easy, we stepped on every challenge there could possibly be. Just to name a few:

-   In what form do micro-apps publish static resources?
-   How does the framework integrate individual micro-apps?
-   How to ensure that sub-applications are isolated from one another (development independence and deployment independence) and runtime sandboxed?
-   Performance issues? What about public dependencies?
-   The list goes on long ...

After solving these common problems of micro frontends and lots of polishing and testing, we extracted the minimal viable framework of our solution, and named it `qiankun`, as it can contain and serve anything. Not long after, it became the cornerstone of hundreds of our web applications in production, and we decided to open-source it to save you the suffering.

**TLDR: Qiankun is probably the most complete micro-frontend solution you ever met🧐.**

✨ Features
----------

Qiankun inherits many benefits from single-spa:

-   📦 **Micro-apps Independent Deployment**
-   🛴 **Lazy Load**
-   📱 **Technology Agnostic**

And on top of these, it offers:

-   💃 **Elegant API**
-   💪 **HTML Entry Access Mode**
-   🛡 **Style Isolation**
-   🧳 **JS Sandbox**
-   ⚡ **Prefetch Assets**
-   🔌 **Umi Plugin Integration**

Packages
--------

Package

Version (click for changelogs)

qiankun

@qiankunjs/loader

@qiankunjs/sandbox

@qiankunjs/shared

@qiankunjs/react

@qiankunjs/vue

@qiankunjs/ui-shared

@qiankunjs/webpack-plugin

create-qiankun

📦 Installation
---------------

$ yarn add qiankun  # or npm i qiankun -S

📖 Documentation
----------------

You can find the Qiankun documentation on the website

Check out the Getting Started page for a quick overview.

The documentation is divided into several sections:

-   Tutorial
-   API Reference
-   FAQ
-   Community

💿 Examples
-----------

Inside the `examples` folder, there is a sample Shell app and multiple mounted Micro FE apps. To get it running, first clone `qiankun`:

$ git clone https://github.com/umijs/qiankun.git
$ cd qiankun

Now install and run the example:

$ pnpm install
$ pnpm run examples:install
$ pnpm run examples:start

Visit `http://localhost:7099`.

🎯 Roadmap
----------

See Qiankun 3.0 Roadmap

🤝 Contributing
---------------

See contributing guide.

👥 Contributors
---------------

Thanks to all the contributors!

🎁 Acknowledgements
-------------------

-   single-spa What an awesome meta-framework for micro-frontends!
-   writable-dom Utility to stream HTML content into a live document.

📄 License
----------

Qiankun is MIT licensed.
