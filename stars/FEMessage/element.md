---
project: element
stars: 60
description: deepexi customize element-ui
url: https://github.com/FEMessage/element
---

* * *

Install
-------

npm install @femessage/element-ui -S

#or
yarn add @femessage/element-ui

Quick Start
-----------

import Vue from 'vue'
import Element from '@femessage/element-ui'

Vue.use(Element)

// or
import {
  Select,
  Button
  // ...
} from '@femessage/element-ui'

Vue.component(Select.name, Select)
Vue.component(Button.name, Button)

For more information, please refer to Quick Start in our documentation.

Generate Theme
--------------

# fork this repository

git clone https://github/{ user || owner }/element.git

# remember: if want to update your component and its css, must merge latest only-component branch into your repository
git checkout -b only-component new-theme

# modify packages/theme-chalk/src/common/var.scss

# modify package name in packages/theme-chalk/package.json

sh ./publish-theme.sh

# now a new theme publish to npm for your own

The reason to checkout from branch `only-component`, can be found in Contributing Guide

Development
-----------

# install dependence
yarn bootstrap

# generate files for examples site
yarn build:file

# generate theme files
yarn build:theme

# generate utils files
yarn build:utils

# generate files about locale
yarn build:umd

# clean files from yarn dist
yarn clean

# bundle examples site
yarn deploy:build

# bundle extension files
yarn deploy:extension

# extension local dev
yarn dev:extension

# local dev and preview examples site
yarn dev

# local dev single component
yarn dev:play

# bundle all lib
yarn dist

# generate i18n files
yarn i18n

# using eslint to check code style
yarn lint

# run unit test
yarn test

Contribution
------------

Please make sure to read the Contributing Guide before making a pull request.

Browser Support
---------------

Modern browsers and Internet Explorer 10+.

Links
-----

-   Documentation
-   ChangeLog

LICENSE
-------

MIT
