---
project: IconPark
stars: 8840
description: 🍎Transform an SVG icon into multiple themes, and generate React icons，Vue icons，svg icons
url: https://github.com/bytedance/IconPark
---

IconPark
========

English | 简体中文

Introduction
------------

IconPark gives access to more than 2000 high-quality icons, and introduces an interface for customizing your icons. Instead of using various SVG source files to achieve different themes, we implement a technology transforming attributes of a single SVG source file into multiple themes. Besides, we provide cross-platform components, including `react-icons`, `vue-icons` and `svg-icons`. So whether you are a designer or a developer, you can use them in your designs or your projects for free.

### Packages

#### Generate Cross-platform Components

Find packages in `packages` folder. NPM packages make it painless to import icon components to your project.

Name

Github link

NPM link

React Icons

React Component

@icon-park/react

Vue2 Icons

Vue Component for old Vue2.0

@icon-park/vue

Vue3 Icons

Vue Component for Vue3.0

@icon-park/vue-next

SVG Icons

Pure SVG String

@icon-park/svg

#### Multiple themes

Basic coloring can be done by setting two attributes on the node: fill and stroke. Fill sets the color inside the object while stroke sets the color of the line drawn around the object. By changing this two attributes, you can transform a single SVG icon into different themes, including: `outline`, `filled`, `two-tone`, `multi-color`. Take the icon named `camera` for example:

Source file:

After Transforming:

React icons

Preview

Theme

`<Camera theme="outline" size="32" fill="#000000"/>`

Outline theme

`<Camera theme="filled" size="32" fill="#333"/>`

Filled theme

`<Camera theme="two-tone" size="32" fill={['#333' ,'#2F88FF']}/>`

Two-tone theme

`<Camera theme="multi-color" size="32" fill={['#333' ,'#2F88FF' ,'#FFF' ,'#43CCF8']}/>`

Multi-color theme

#### Embed IconPark in your project

If you need to use additional information such as icon name, author, category, label and creation time, you can use the `icons.json` file located in the root directory of each NPM.

### Website

#### Customization

Here is the website of IconPark. Each icon is hand-coded within a 48x48 grid, using SVG stroke giving the maximum flexibility on styling. You can adjust the color, size, `stroke-width`, `stroke-linejoin`, `stroke-linecap` and other attributes to meet your needs.

#### Convenient Online Tools

> You can use them in Figma, Sketch, Photoshop, PPT, etc.

-   Copy SVG
-   Copy React Icon Component
-   Copy Vue Icon Component
-   Download PNG
-   Download SVG

### Changelog

CHANGELOG.en-US | CHANGELOG.简体中文
