---
project: electron-vite-vue
stars: 4732
description: 🥳 Really simple Electron + Vite + Vue boilerplate.
url: https://github.com/electron-vite/electron-vite-vue
---

electron-vite-vue
=================

🥳 Really simple `Electron` + `Vue` + `Vite` boilerplate.

Features
--------

📦 Out of the box  
🎯 Based on the official template-vue-ts, less invasive  
🌱 Extensible, really simple directory structure  
💪 Support using Node.js API in Electron-Renderer  
🔩 Support C/C++ native addons  
🖥 It's easy to implement multiple windows

Quick Setup
-----------

# clone the project
git clone https://github.com/electron-vite/electron-vite-vue.git

# enter the project directory
cd electron-vite-vue

# install dependency
npm install

# develop
npm run dev

Debug
-----

Directory
---------

+ ├─┬ electron
+ │ ├─┬ main
+ │ │ └── index.ts    entry of Electron-Main
+ │ └─┬ preload
+ │   └── index.ts    entry of Preload-Scripts
  ├─┬ src
  │ └── main.ts       entry of Electron-Renderer
  ├── index.html
  ├── package.json
  └── vite.config.ts

FAQ
---

-   C/C++ addons, Node.js modules - Pre-Bundling
-   dependencies vs devDependencies
