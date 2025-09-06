---
project: Paddle.js
stars: 1047
description: Paddle.js is a web project for Baidu PaddlePaddle, which is an open source deep learning framework running in the browser. Paddle.js can either load a pre-trained model, or transforming a model from paddle-hub with model transforming tools provided by Paddle.js. It could run in every browser with WebGL/WebGPU/WebAssembly supported. It could also run in Baidu Smartprogram and WX miniprogram.
url: https://github.com/PaddlePaddle/Paddle.js
---

中文版

Paddle.js
=========

Paddle.js is a web project for Baidu PaddlePaddle, which is an open source deep learning framework running in the browser. Paddle.js can either load a pre-trained model, or transforming a model from paddle-hub with model transforming tools provided by Paddle.js. It could run in every browser with WebGL/WebGPU/WebAssembly supported. It could also run in Baidu Smartprogram and WX miniprogram.

Ecosystem
---------

Project

version

Description

paddlejs-core

inference engine

paddlejs-backend-webgl

webgl backend

paddlejs-backend-wasm

wasm backend

paddlejs-backend-webgpu

webgpu backend

paddlejsconverter

convert paddlepaddle model

humanseg

human segmentation library

ocr

optical character recognition library

gesture

gesture recognition library

mobilenet

image classification library

ocr detection

optical character detection library

facedetect

face detection library

Website
-------

https://paddlejs.baidu.com

Key Features
------------

### Module

-   paddlejs-core, the core part of the Paddle.js ecosystem, which is responsible for the operation of the inference process of the entire engine.
-   paddlejsconverter, model transformation tool for Paddle.js, convert PaddlePaddle models (also known as fluid models) into a browser-friendly format.
-   paddlejs-models, model projects, supply flexible low-level APIs for users to implement their AI scenario.
-   paddlejs-examples, Paddle.js AI examples
-   paddlejs-mediapipe, tools for live and streaming media, support webrtc camera and a lightweight opencv package

### Backends

-   paddlejs-backend-webgl, webgl backend, the main backend for Paddle.js, ops supported
-   paddlejs-backend-webgpu, webgpu backend, an experimental backend, WebGPU draft, ops supported
-   paddlejs-backend-wasm, WebAssembly backend, ops supported
-   paddlejs-backend-cpu, cpu backend, ops supported
-   paddlejs-backend-nodegl, nodegl backend, a backend in Node.js for Paddle.js, using the webgl backend ops. ops supported

Examples
--------

-   image classification game image classification game example in wx miniprogram
-   gesture gesture recognition example online experience
-   humanStream video-streaming human segmentation online experience
-   humanseg human segmentation example online experience
-   ocr optical character recognition example online experience
-   ocr detection optical character detection example online experience
-   mobilenet classify images into 1000 object categories online experience
-   wine classify bottles into 7 categories online experience
-   webglworker This demo help us to use Paddle.js in WebWorker.

### Browser/Platforms Coverage

-   PC: Chrome, Safari, Firefox
-   Phone: Baidu App , Chrome , UC and QQ Browser
-   Smartprogram: Baidu Smartprogram, WX miniprogram
-   Platform: macOS, Windows

Load Model
----------

1.  Support load model files on the network:

-   model.json (model structure and operators' attributes)
-   chunk\_x.dat (model params binary data)

1.  Support use model obj

-   modelObj.model (model structure json object)
-   modelObj.params（model params Float32Array data）

If you dont' want to put model on the network, you can use method 2.

Feedback and Community Support
------------------------------

-   Online video tutorial start video
-   Questions, reports, and suggestions are welcome through Github Issues!
-   Forum: Opinions and questions are welcome at our PaddlePaddle Forum！
-   QQ group chat: 696965088
