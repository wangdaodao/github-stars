---
project: gwm
stars: 210
description: 🍭gwm.js Generate Watermark  用于生成网页水印，警示信息安全与责任追踪。
url: https://github.com/loadchange/gwm
---

gwm.js
======

> Generate Watermark

It can be used to generate watermarking in internal system, which can prompt information security and responsibility tracking. Safety issues can not be ignored, which has a certain role in prompting the sensitive operation of internal personnel.

### Characteristic

-   Support the generation of three types of watermarking: canvas, SVG and element
-   Supporting element monitoring to prevent tampering
-   Extensibility

Example
-------

Click here to see the effect →：Demo

Instructions
------------

**1、Introducing JS files**

<script src\="../js/gwm.js"\></script\>

Or install with NPM

```
npm install gwm
```

**2、Building watermark**

```
gwm.creation()
```

Parameter
---------

Parameter

Default value

Explain

txt

date 内部资料 请勿外传

Watermarking text content

width

158

Watermark Canvas Width

height

100

Watermark canvas height

x

0

Watermarking coordinate X

y

50

Watermarking coordinate y

font

'microsoft yahe'

Setting Watermark Font

fontSize

12

Watermark font size

color

#000

Watermark font color

alpha

0.1

Watermark font transparency

angle

\-15

Watermarking Text Tilt Angle

mode

canvas

Optional parameters\[canvas, svg, element\]

watch

true

Monitoring whether watermarking elements have been tampered with  
Tampering triggers redrawing

css

null

Setting Watermark Element Styles

destroy

false

If \`true\`, prevents multiple calls to \`creation\` to protect against tampering

container

body

Pass in a package container, which can be a \`string\` Type selector, or a DOM object, defaults to body

count

null

Optional parameter, used to directly set the number of watermarks generated

Custom Font Example
-------------------

To use a custom font, you can specify the desired font through the `font` parameter when creating the watermark. For example, to change the font to `Arial`, you can do it like this:

gwm.creation({
  font: 'Arial'
})

Method
------

Method

Explain

gwm.creation

Create a watermarking.

gwm.observing

Manually open the observer, when the watermarking element is tampered with, re-render the watermarking element.

gwm.cancel

Cancel the observer, the watermark can be hidden or deleted.

Development Guide
-----------------

### Requirements

-   Node.js >= 20.0.0
-   npm >= 9.0.0

### Installation

# Clone the repository
git clone https://github.com/loadchange/gwm.git
cd gwm

# Install dependencies
npm install

### Development

# Start development server with hot reload
npm run dev

### Testing

# Run tests
npm test

# Run tests with coverage
npm run test:coverage

# Run tests in watch mode
npm run test:watch

### Building

# Build for production (includes type declarations)
npm run build

构建将使用 Vite 完成，产物和类型声明均输出到 dist 目录。

### Documentation

# Generate documentation
npm run deploy-docs

Contributing
------------

Please read CONTRIBUTING.md for details on our code of conduct, and the process for submitting pull requests to us.

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.
