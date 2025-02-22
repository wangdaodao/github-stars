---
project: PyMuPDF
stars: 6537
description: PyMuPDF is a high performance Python library for data extraction, analysis, conversion & manipulation of PDF (and other) documents.
url: https://github.com/pymupdf/PyMuPDF
---

PyMuPDF
=======

**PyMuPDF** is a high performance **Python** library for data extraction, analysis, conversion & manipulation of PDF (and other) documents.

Community
=========

Join us on **Discord** here: #pymupdf

Installation
============

**PyMuPDF** requires **Python 3.9 or later**, install using **pip** with:

`pip install PyMuPDF`

There are **no mandatory** external dependencies. However, some optional features become available only if additional packages are installed.

You can also try without installing by visiting PyMuPDF.io.

Usage
=====

Basic usage is as follows:

import pymupdf \# imports the pymupdf library
doc \= pymupdf.open("example.pdf") \# open a document
for page in doc: \# iterate the document pages
  text \= page.get\_text() \# get plain text encoded as UTF-8

Documentation
=============

Full documentation can be found on pymupdf.readthedocs.io.

Optional Features
=================

-   fontTools for creating font subsets.
-   pymupdf-fonts contains some nice fonts for your text output.
-   Tesseract-OCR for optical character recognition in images and document pages.

About
=====

**PyMuPDF** adds **Python** bindings and abstractions to MuPDF, a lightweight **PDF**, **XPS**, and **eBook** viewer, renderer, and toolkit. Both **PyMuPDF** and **MuPDF** are maintained and developed by Artifex Software, Inc.

**PyMuPDF** was originally written by Jorj X. McKie.

License and Copyright
=====================

**PyMuPDF** is available under open-source AGPL and commercial license agreements. If you determine you cannot meet the requirements of the **AGPL**, please contact Artifex for more information regarding a commercial license.
