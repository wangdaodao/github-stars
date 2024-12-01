---
project: pdf-annotate.js
stars: 269
description: Annotation layer for pdf.js
url: https://github.com/Submitty/pdf-annotate.js
---

@submitty/pdf-annotate.js
=========================

Annotation layer for PDF.js.

Combined fork of archived instructure/pdf-annotate.js and deleted DynamicEnvironmentSystems/pdf-annotate.js. Under active development for usage within Submitty.

To report issues for pdf-annotate.js, please file them under the Submitty/Submitty repository.

Objectives
----------

-   Provide a low level annotation layer for PDF.js.
-   Optional high level UI for managing annotations.
-   Agnostic of backend, just supply your own `StoreAdapter` to fetch/store data.
-   Prescribe annotation format.

Installation
------------

npm install Submitty/pdf-annotate.js

Example
-------

import pdfjsLib from 'pdfjs-dist/build/pdf';
import PDFJSAnnotate from 'pdfjs-annotate';

const { UI } \= PDFJSAnnotate;
const VIEWER \= document.getElementById('viewer');
const RENDER\_OPTIONS \= {
  documentId: 'MyPDF.pdf',
  pdfDocument: null,
  scale: 1,
  rotate: 0
};

pdfjsLib.GlobalWorkerOptions.workerSrc \= 'pdf.worker.js';
PDFJSAnnotate.setStoreAdapter(new PDFJSAnnotate.LocalStoreAdapter());

pdfjsLib.getDocument(RENDER\_OPTIONS.documentId).promise.then((pdf) \=> {
  RENDER\_OPTIONS.pdfDocument \= pdf;
  VIEWER.appendChild(UI.createPage(1));
  UI.renderPage(1, RENDER\_OPTIONS);
});

See /web for an example web client for annotating PDFs.

Documentation
-------------

View the docs.

Developing
----------

# clone the repo
$ git clone https://github.com/Submitty/pdf-annotate.js.git
$ cd pdf-annotate.js

# intall dependencies
$ npm install

# start example server
$ npm start
$ open http://127.0.0.1:8080

# run tests
$ npm test

# lint the code
$ npm run lint

Building
--------

**Do not** commit your built files when contributing. If on Windows, change the `build` script in `package.json` to `webpack && SET MINIFY=1&webpack`.

# switch to node v14 or earlier
$ nvm use 14

# build the dist files
$ npm run build
