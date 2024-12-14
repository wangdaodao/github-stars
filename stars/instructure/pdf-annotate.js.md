---
project: pdf-annotate.js
stars: 548
description: Annotation layer for pdf.js (no longer maintained)
url: https://github.com/instructure/pdf-annotate.js
---

pdf-annotate.js (no longer maintained)
======================================

Annotation layer for pdf.js

Objectives
----------

-   Provide a low level annotation layer for pdf.js.
-   Optional high level UI for managing annotations.
-   Agnostic of backend, just supply your own `StoreAdapter` to fetch/store data.
-   Prescribe annotation format.

Example
-------

import \_\_pdfjs from 'pdfjs-dist/build/pdf';
import PDFJSAnnotate from 'pdfjs-annotate';
import MyStoreAdapter from './myStoreAdapter';

const { UI } \= PDFJSAnnotate;
const VIEWER \= document.getElementById('viewer');
const RENDER\_OPTIONS \= {
  documentId: 'MyPDF.pdf',
  pdfDocument: null,
  scale: 1,
  rotate: 0
};

PDFJS.workerSrc \= 'pdf.worker.js';
PDFJSAnnotate.setStoreAdapter(MyStoreAdapter);

PDFJS.getDocument(RENDER\_OPTIONS.documentId).then((pdf) \=> {
  RENDER\_OPTIONS.pdfDocument \= pdf;
  VIEWER.appendChild(UI.createPage(1));
  UI.renderPage(1, RENDER\_OPTIONS);
});

See more examples.

Documentation
-------------

View the docs.

Developing
----------

# clone the repo
$ git clone https://github.com/instructure/pdf-annotate.js.git
$ cd pdf-annotate.js

# intall dependencies
$ npm install

# start example server
$ npm start
$ open http://127.0.0.1:8080

# run tests
$ npm test

License
-------

MIT
