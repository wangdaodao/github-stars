---
project: dayjs
stars: 48278
description: ⏰ Day.js 2kB immutable date-time library alternative to Moment.js with the same modern API
url: https://github.com/iamkun/dayjs
---

  
Warp is built for coding with multiple AI agents

* * *

English | 简体中文 | 日本語 | Português Brasileiro | 한국어 | Español (España) | Русский | Türkçe | සිංහල | עברית

Fast **2kB** alternative to Moment.js with the same modern API

  

> Day.js is a minimalist JavaScript library that parses, validates, manipulates, and displays dates and times for modern browsers with a largely Moment.js-compatible API. If you use Moment.js, you already know how to use Day.js.

dayjs().startOf('month').add(1, 'day').set('year', 2018).format('YYYY-MM-DD HH:mm:ss');

-   🕒 Familiar Moment.js API & patterns
-   💪 Immutable
-   🔥 Chainable
-   🌐 I18n support
-   📦 2kb mini library
-   👫 All browsers supported

* * *

Getting Started
---------------

### Documentation

You can find more details, API, and other docs on day.js.org website.

### Installation

npm install dayjs --save

📚Installation Guide

### API

It's easy to use Day.js APIs to parse, validate, manipulate, and display dates and times.

dayjs('2018-08-08') // parse

dayjs().format('{YYYY} MM-DDTHH:mm:ss SSS \[Z\] A') // display

dayjs().set('month', 3).month() // get & set

dayjs().add(1, 'year') // manipulate

dayjs().isBefore(dayjs()) // query

📚API Reference

### I18n

Day.js has great support for internationalization.

But none of them will be included in your build unless you use it.

import 'dayjs/locale/es' // load on demand

dayjs.locale('es') // use Spanish locale globally

dayjs('2018-05-05').locale('zh-cn').format() // use Chinese Simplified locale in a specific instance

📚Internationalization

### Plugin

A plugin is an independent module that can be added to Day.js to extend functionality or add new features.

import advancedFormat from 'dayjs/plugin/advancedFormat' // load on demand

dayjs.extend(advancedFormat) // use plugin

dayjs().format('Q Do k kk X x') // more available formats

📚Plugin List

Sponsors
--------

Support this project by becoming a sponsor. Your logo will show up here with a link to your website.

\[Become a sponsor via Github\] \[Become a sponsor via OpenCollective\]

                                                                                

Contributors
------------

This project exists thanks to all the people who contribute.

Please give us a 💖 star 💖 to support us. Thank you.

And thank you to all our backers! 🙏

  

License
-------

Day.js is licensed under a MIT License.
