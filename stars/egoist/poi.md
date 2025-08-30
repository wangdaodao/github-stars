---
project: poi
stars: 5210
description: ⚡A zero-config bundler for JavaScript applications.
url: https://github.com/egoist/poi
---

⚠️ Poi has been deprecated, please migrate to Vite, contact me personally if you need help.
===========================================================================================

  

Poi is a bundler built on the top of webpack, trying to make developing and bundling apps with webpack as easy as possible.

**The Poi project is supported by our Backers and funded through Patreon.**

Features
--------

-   📦 Out of box support for JS, CSS, File assets and more.
-   ⚛ Framework-agnostic but also support JSX, Vue and more with no configs.
-   🔌 Great extensibility.
-   🐙 Fits most web apps, npm libs.
-   🚨 Great development experience.

Quick Overview
--------------

Before we get started, ensure that you have installed Node.js (>=8) and Yarn (or npm) on your machine.

### Get Started Immediately

yarn global add create-poi-app
create-poi-app my-app

cd my-app
npm run dev

Then open http://localhost:4000 to see your app.  
When you’re ready to deploy to production, create a minified bundle with `npm run build`.

### Get Started Manually

Inside an empty project, run `yarn init` or `npm init` to create a `package.json` and install Poi:

yarn init
yarn add poi --dev

Now all you need is to create an entry file, like if you're building a website, just create an `index.js`:

const el \= document.createElement('div')
el.textContent \= 'Hello Poi!'

document.body.appendChild(el)

Now if you run:

yarn poi --serve

You will get a URL like `http://localhost:4000` which you can open to preview the app.

Next let's start adding some dependencies like a CSS file `style.module.css`:

.title {
  color: pink;
}

import styles from './style.module.css'

const el \= document.createElement('div')
el.className \= styles.title
el.textContent \= 'Hello Poi!'

document.body.appendChild(el)

Save it and the browser will automatically reload to apply the changes!

Documentation
-------------

📚 https://poi.js.org

You can improve it by sending pull requests to this repository.

Check out this repository for more examples.

Community
---------

All feedback and suggestions are welcome!

-   💬 Join the community on Spectrum.
-   📣 Stay up to date on new features and announcements on Twitter @poi\_\_js.

Credits
-------

Poi v12 wouldn't exist without the inspirations from following projects:

-   Webpack
-   Parcel 2
-   Poi itself
-   Vue CLI 3
-   Create React App

License
-------

MIT © EGOIST
