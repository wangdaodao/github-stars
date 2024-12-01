---
project: vue-testing-handbook
stars: 12
description: A guide on testing Vue components and applications
url: https://github.com/tonylua/vue-testing-handbook
---

English | 日本語 | Русский | 简体中文

Vue Testing Handbook
--------------------

Welcome to the Vue Testing Handbook!

What is this?
-------------

This is a collection of short, focused examples on how to test Vue components. It uses `vue-test-utils`, the official library for testing Vue components, and Jest, a modern testing framework. It covers the `vue-test-utils` API, as well as best practises and useful parts of the Jest API for testing Vue components. A working demo project with the examples is also included, which you can pull down and run yourself.

Languages
---------

The handbook is written in English. We have a Russian and Japanese translation in progress. Please make an issue if you would like to translate the book into your own language!

Contributing
------------

### Development

Vuepress is used to generate the static website. Articles are written in markdown.

Clone the repo and run `yarn` to install the dependencies. Then run `yarn dev` to open the dev server. Access it on `localhost:8080`.

To edit a guide, update the code in the src directory. The markdown files are converted to HTML when deployed – no need to edit those.
