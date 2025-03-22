---
project: canvas-editor
stars: 4032
description: rich text editor by canvas/svg
url: https://github.com/Hufe921/canvas-editor
---

canvas-editor
=============

a rich text editor by canvas/svg

View Demo · View Docs · Report Bug · Request Feature · FAQ

Love the project? Please consider donating to help it improve!

Tips
----

1.  Official plugin: canvas-editor-plugin
2.  The render layer by svg is under development, see feature/svg
3.  The export pdf feature is available now, see feature/pdf
4.  The AI-powered text processing demo, see feature/ai

Basic usage
-----------

npm i @hufe921/canvas-editor --save

<div class\="canvas-editor"\></div\>

import Editor from '@hufe921/canvas-editor'

new Editor(document.querySelector('.canvas-editor'), {
  main: \[
    {
      value: 'Hello World'
    }
  \]
})

Features
--------

-   Rich text operations (Undo, Redo, Font, Size, Bold, Italic, Underline, Strikeout, Superscript, Alignment, Title, List, ...)
-   Insert elements (Table, Image, Link, Code Block, Page Break, Math Formula, Date Picker, Block, ...)
-   Print (Based on canvas to picture, pdf drawing)
-   Controls (Select, Text, Date, Radio, Checkbox)
-   Contextmenu (Internal, Custom)
-   Shortcut keys (Internal, Custom)
-   Drag and Drop(Text, Element, Control)
-   Header, Footer, Page Number
-   Page Margin
-   Watermark
-   Pagination
-   Comment
-   Catalog

Roadmap
-------

1.  Table paging
2.  Control rules
3.  Improve performance
4.  CRDT

Snapshot
--------

Install
-------

`yarn`

Dev
---

`npm run dev`

Build
-----

#### app

`npm run build`

#### lib

`npm run lib`
