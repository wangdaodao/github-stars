---
project: vue-document-editor
stars: 327
description: :page_facing_up: Paper-sized WYSIWYG document editor for Vue apps
url: https://github.com/motla/vue-document-editor
---

**vue-document-editor** is a rich-text editor built on top of Vue.js, using the native _contenteditable_ browser implementation and some JavaScript trickery to spread content over paper-sized pages. It is mainly designed to allow **targeted modifications** to pre-formatted documents using HTML or **interactive templates**.

###### 💬 This package does not intend to replace a proper document editor with full functionality. If you're looking for a powerful word processor, check out CKEditor for Vue.js or Collabora Online Development Edition.

Features
--------

### 🚀 See live demo

-   Use Vue.js components as interactive page templates
-   Word-by-word page splitting (_still experimental - only for plain HTML content_)
-   Native Print compatible
-   Dynamic document format and margins in millimeters
-   Custom page overlays (headers, footers, page numbers)
-   Page breaks
-   Smart zoom and page display modes
-   Computes text style at caret position
-   Migrated to Vue.js 3.x (to use with Vue 2.x, select library version 1.x)

###### 💬 This package doesn't include any toolbar. The demo features vue-file-toolbar-menu for the toolbar.

Installation
------------

##### In your Vue.js 3.x project:

```
npm install vue-document-editor
```

##### In your Vue.js 2.x project:

```
npm install vue-document-editor@1
```

###### 💬 If you prefer static files, import assets from the `dist` folder

Basic example
-------------

###### MyComponent.vue

<template\>
  <div style\="font-family: Avenir, sans-serif"\>
    <vue-document-editor v-model:content\="content" /> <!-- Vue 3 syntax \-->
    <!-- <vue-document-editor :content.sync="content" /> \--> <!-- Vue 2 syntax \-->
  </div\>
</template\>

<script\>
import VueDocumentEditor from 'vue-document-editor'
export default {
  components: { VueDocumentEditor },
  data () {
    return { 
      content: \["<h1>Hello!</h1>Fill this page with text and new pages will be created as it overflows."\]
    }
  }
}
</script\>

same example using static files loaded with a CDN (Vue 3)

<html\>
<head\>
  <script src\="https://cdn.jsdelivr.net/npm/vue@3/dist/vue.global.prod.js"\></script\>
  <script src\="https://cdn.jsdelivr.net/npm/vue-document-editor@2/dist/VueDocumentEditor.umd.min.js"\></script\>
  <link href\="https://cdn.jsdelivr.net/npm/vue-document-editor@2/dist/VueDocumentEditor.css" rel\="stylesheet"\>
</head\>
<body\>
  <div id\="app"\>
    <div style\="font-family: Avenir, sans-serif"\>
      <vue-document-editor v-model:content\="content" />
    </div\>
  </div\>
  <script\>
  const app \= Vue.createApp({
    components: { VueDocumentEditor },
    data () {
      return { 
        content: \["<h1>Hello!</h1>Fill this page with text and new pages will be created as it overflows."\]
      }
    }
  }).mount('#app');
  </script\>
</body\>
</html\>

same example using static files loaded with a CDN (Vue 2)

<html\>
<head\>
  <script src\="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"\></script\>
  <script src\="https://cdn.jsdelivr.net/npm/vue-document-editor@1/dist/VueDocumentEditor.umd.min.js"\></script\>
  <link href\="https://cdn.jsdelivr.net/npm/vue-document-editor@1/dist/VueDocumentEditor.css" rel\="stylesheet"\>
</head\>
<body\>
  <div id\="app"\>
    <div style\="font-family: Avenir, sans-serif"\>
      <vue-document-editor :content.sync\="content" />
    </div\>
  </div\>
  <script\>
  var app \= new Vue({
    el: '#app',
    components: { VueDocumentEditor },
    data () {
      return { 
        content: \["<h1>Hello!</h1>Fill this page with text and new pages will be created as it overflows."\]
      }
    }
  })
  </script\>
</body\>
</html\>

Complete example
----------------

See the Demo.vue file and the InvoiceTemplate.ce.vue file corresponding to the live demo.

API
---

For the list of props, data and styling variables: **📘 read the API**.

Known issues / limitations
--------------------------

-   **Undo / Redo**: Native undo/redo needs to be rewritten as the split mechanism modifies the HTML content at every input, so the navigator is lost. You have to implement it yourself by watching `content` updates and storing them in a stack, then restoring them. Demo.vue implements this. Also your interactive templates need to have a custom undo/redo management if their editable fields are not synced with the `content`.
-   **Performance**: For now, large texts must be divided into multiple paragraphs and large page numbers can slow down the entire document (see Issue 14).
-   **Safari print**: Safari adds print margins unless you choose a borderless paper format in the print box. This has to be done manually. I guess there is no workaround for this issue yet.
-   **Tables, images**: Image/table placement and sizing is not included. You can implement it specifically for your needs. However, table rows split fine over multiple pages.
-   **Page splitting doesn't work with Vue page templates**: This library cannot act on the content managed by Vue (like .vue page templates), because then Vue is lost and the template pages are no longer interactive. The only choice you have is writing plain HTML in the content instead of using .vue templates. You can do interactivity by using HTML elements with the attributes `contenteditable="false"` and `onclick="..."` containing your own JavaScript code.

Project development
-------------------

-   `npm run serve` compiles, serves and hot-reloads demo for development
-   `npm run build` compiles and minifies production files and demo

Licensing
---------

Copyright (c) 2020 Romain Lamothe, MIT License
