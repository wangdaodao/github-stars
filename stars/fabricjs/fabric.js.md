---
project: fabric.js
stars: 29318
description: Javascript Canvas Library, SVG-to-Canvas (& canvas-to-SVG) Parser
url: https://github.com/fabricjs/fabric.js
---

Fabric.js
=========

A **simple and powerful Javascript HTML5 canvas library**.

-   **Website**
-   **GOTCHAS**
-   **Contributing, Developing and More**

* * *

* * *

* * *

* * *

Features
--------

-   Out of the box interactions such as scale, move, rotate, skew, group...
-   Built in shapes, controls, animations, image filters, gradients, patterns, brushes...
-   `JPG`, `PNG`, `JSON` and `SVG` i/o
-   Typed and modular
-   Unit tested

#### Supported Browsers/Environments

Context

Supported Version

Notes

Firefox

✔️

58

Safari

✔️

11

Opera

✔️

chromium based

Chrome

✔️

64

Edge

✔️

chromium based

Edge Legacy

❌

IE11

❌

Node.js

✔️

Node.js installation

Fabric.js Does not use transpilation by default, the browser version we support is determined by the level of canvas api we want to use and some js syntax. While JS can be easily transpiled, canvas API can't.

Installation
------------

$ npm install fabric --save
// or
$ yarn add fabric

#### Browser

See browser modules for using es6 imports in the browser or use a dedicated bundler.

#### Node.js

Fabric.js depends on node-canvas for a canvas implementation (`HTMLCanvasElement` replacement) and jsdom for a `window` implementation on node. This means that you may encounter `node-canvas` limitations and bugs.

Follow these instructions to get `node-canvas` up and running.

Quick Start
-----------

// v6
import { Canvas, Rect } from 'fabric'; // browser
import { StaticCanvas, Rect } from 'fabric/node'; // node

// v5
import { fabric } from 'fabric';

**Plain HTML**

<canvas id\="canvas" width\="300" height\="300"\></canvas\>

<script src\="https://cdn.jsdelivr.net/npm/fabric@6.4.3/dist/index.js"\></script\>
<script\>
  const canvas \= new fabric.Canvas('canvas');
  const rect \= new fabric.Rect({
    top: 100,
    left: 100,
    width: 60,
    height: 70,
    fill: 'red',
  });
  canvas.add(rect);
</script\>

**ReactJS**

import React, { useEffect, useRef } from 'react';
import \* as fabric from 'fabric'; // v6
import { fabric } from 'fabric'; // v5

export const FabricJSCanvas \= () \=> {
  const canvasEl \= useRef<HTMLCanvasElement\>(null);
  useEffect(() \=> {
    const options \= { ... };
    const canvas \= new fabric.Canvas(canvasEl.current, options);
    // make the fabric.Canvas instance available to your app
    updateCanvasContext(canvas);
    return () \=> {
      updateCanvasContext(null);
      canvas.dispose();
    }
  }, \[\]);

  return <canvas width\="300" height\="300" ref\={canvasEl}/>;
};

**Node.js**

import http from 'http';
import \* as fabric from 'fabric/node'; // v6
import { fabric } from 'fabric'; // v5

const port \= 8080;

http
  .createServer((req, res) \=> {
    const canvas \= new fabric.Canvas(null, { width: 100, height: 100 });
    const rect \= new fabric.Rect({ width: 20, height: 50, fill: '#ff0000' });
    const text \= new fabric.Text('fabric.js', { fill: 'blue', fontSize: 24 });
    canvas.add(rect, text);
    canvas.renderAll();
    if (req.url \=== '/download') {
      res.setHeader('Content-Type', 'image/png');
      res.setHeader('Content-Disposition', 'attachment; filename="fabric.png"');
      canvas.createPNGStream().pipe(res);
    } else if (req.url \=== '/view') {
      canvas.createPNGStream().pipe(res);
    } else {
      const imageData \= canvas.toDataURL();
      res.writeHead(200, '', { 'Content-Type': 'text/html' });
      res.write(\`<img src="${imageData}" />\`);
      res.end();
    }
  })
  .listen(port, (err) \=> {
    if (err) throw err;
    console.log(
      \`> Ready on http://localhost:${port}, http://localhost:${port}/view, http://localhost:${port}/download\`,
    );
  });

See our ready to use templates.

* * *

Other Solutions
---------------

Project

Description

Three.js

3D graphics

PixiJS

WebGL renderer

Konva

Similar features

html-to-image

HTML to image/canvas

More Resources
--------------

-   WIP new fabricjs.com
-   Demos on `fabricjs.com`
-   Fabric.js on `Twitter`
-   Fabric.js on `CodeTriage`
-   Fabric.js on `Stack Overflow`
-   Fabric.js on `jsfiddle`
-   Fabric.js on `Codepen.io`

Credits
-------

-   kangax
-   asturur on `Twitter`
-   ShaMan123
-   melchiar
-   Ernest Delgado for the original idea of manipulating images on canvas
-   Maxim "hakunin" Chernyak for ideas, and help with various parts of the library throughout its life
-   Sergey Nisnevich for help with geometry logic
-   Stefan Kienzle for help with bugs, features, documentation, GitHub issues
-   Shutterstock for the time and resources invested in using and improving Fabric.js
-   and all the other contributors
