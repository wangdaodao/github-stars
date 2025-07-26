---
project: vue-pdf-app
stars: 238
description: VUEjs v2 PDF viewer based on Mozilla's PDFJS
url: https://github.com/sandanat/vue-pdf-app
---

VUEjs v2 PDF viewer based on Mozilla's PDFJS.

100% PDFJS functionality:

-   zoom
-   open
-   print
-   download
-   rotate
-   text selection
-   search panel
-   pdf document password
-   thumbnail, outline, attachments, annotation layers

Easily localized configurable toolbar

NEW Toolbar custom UI

Cross-browser support (including IE11)

Color customization (IE11 not supported)

Buttons icons customization

Light/dark themes

Built-in typescript support

UMD/Unpkg support:

File

Size

Gzipped

vue-pdf-app.umd.min.js

1742.89 KiB

478.86 KiB

vue-pdf-app.umd.js

3115.59 KiB

677.87 KiB

vue-pdf-app.common.js

3115.12 KiB

677.71 KiB

icons/main.css

15 - 40 KiB (depends from browser)

Example
=======

<template\>
  <!-- used \`style="height: 100vh;"\` because without it in the Firefox 89 and Chrome 91 (June 2021) the \`vue-pdf-app\` is not rendering on the page, just empty space without any errors (since \`vue-pdf-app\` does not have height and it is the top tag in the generated markup ) \-->
  <!-- or you can just wrap \`vue-pdf-app\` in <div> tag and set height for it via CSS (like in \`Script tag (unpkg)\` example below) \-->
  <vue-pdf-app style\="height: 100vh;" pdf\="https://file-examples-com.github.io/uploads/2017/10/file-example\_PDF\_1MB.pdf"\></vue-pdf-app\>
</template\>

<script\>
import VuePdfApp from "vue-pdf-app";
// import this to use default icons for buttons
import "vue-pdf-app/dist/icons/main.css";
export default {
  components: {
    VuePdfApp
  }
};
</script\>

Live demo

Live demo 2

Examples source code

FAQ

API
===

:pdf
----

-   Type: `string | null | ArrayBuffer | TypedArray`
-   Required: `false`
-   Usage:

<vue-pdf-app pdf="https://example.com/sample.pdf" />
<vue-pdf-app :pdf\="ArrayBuffer" />

:title
------

-   Description: `true` renames document title to pdf file name.
-   Type: `boolean`
-   Required: `false`
-   Default: `false`
-   Usage:

<vue-pdf-app :title\="true" />

:theme.sync
-----------

-   Type: `"dark" | "light"`
-   Required: `false`
-   Usage:

<vue-pdf-app theme="dark" />
<vue-pdf-app :theme\="theme" />
<vue-pdf-app :theme.sync\="theme" />

new :fileName
-------------

-   Description: when pdf is passed like an array buffer default download file name is `document.pdf`. Set this prop to override it.
-   Type: `string`
-   Required: `false`
-   Usage:

<vue-pdf-app :pdf\="ArrayBuffer" file-name="file name" />

new :pageScale
--------------

-   Description: default page scale.
-   Type: `number | "page-actual"| "page-width"| "page-height"| "page-fit"| "auto"`
-   Required: `false`
-   Usage:

// 20%
<vue-pdf-app page-scale="20" />
<vue-pdf-app :page-scale\="20" />
<vue-pdf-app :page-scale\="page\-actual" />

new :pageNumber
---------------

-   Description: pdfjs stores last viewed page of a file in `window.localStorage.getItem("pdfjs.history")`. Specify the prop to override it.
-   Type: `number`
-   Required: `false`
-   Usage:

<vue-pdf-app :page-number\="1" />

:config
-------

-   Description: toolbar configuration. Toolbar is available by default. Specify `false` for buttons or whole group of buttons to disable them.
-   Type: `toolbar config (see below)`
-   Required: `false`
-   Default: `toolbar config`
-   Usage:

<vue-pdf-app :config\="config" />

<script\>
export default {
  data() {
    return {
      // disable "Previous page" button
      config: {
        toolbar: {
          toolbarViewerLeft: {
            previous: false
          }
        }
      },
      // disable whole page navigation panel
      config2: {
        toolbar: {
          toolbarViewerLeft: false
        }
      },
      // disable whole panel
      config3: {
        toolbar: false
      }
    };
  }
};
</script\>

Config specification

`{   sidebar: {     viewThumbnail: true,     viewOutline: true,     viewAttachments: true,   },   secondaryToolbar: {     secondaryPresentationMode: true,     secondaryOpenFile: true,     secondaryPrint: true,     secondaryDownload: true,     secondaryViewBookmark: true,     firstPage: true,     lastPage: true,     pageRotateCw: true,     pageRotateCcw: true,     cursorSelectTool: true,     cursorHandTool: true,     scrollVertical: true,     scrollHorizontal: true,     scrollWrapped: true,     spreadNone: true,     spreadOdd: true,     spreadEven: true,     documentProperties: true,   },   toolbar: {     toolbarViewerLeft: {       findbar: true,       previous: true,       next: true,       pageNumber: true,     },     toolbarViewerRight: {       presentationMode: true,       openFile: true,       print: true,       download: true,       viewBookmark: true,     },     toolbarViewerMiddle: {       zoomOut: true,       zoomIn: true,       scaleSelectContainer: true,     },   },   errorWrapper: true, };`

new :id-config
--------------

-   Description: If default toolbar UI doesn't suite you it is possible to build custom toolbar. The prop contains elements ID to which to bind functionality. If element ID is specified in this prop appropriate button will be hidden in a default toolbar. May not work with UI framework components. That is because pdfjs internally manages attributes specific to a certain HTML element (for instance pdfjs toggles `disabled` attribute of a button but it won't if a div is used instead of a button). So it is better to use native HTML element specified as recommended in ID config specification below. Four slots are specially designed to build custom toolbar (are situated near a pdf page): `viewer-header, viewer-prepend, viewer-append, viewer-footer` (refer slots API). It is also possible to use other slots or elements outside vue-pdf-app.
-   Type: `ID config (see below)`
-   Required: `false`
-   Usage:

<template\>
  <div\>
    <button :id\="idConfig.zoomOut" type\="button"\>Zoom out</button\>
    <vue-pdf-app :id-config\="idConfig"\>
      <template #viewer-prepend\>
        <div class\="viewer-prepend"\>
          <button :id\="idConfig.zoomIn" type\="button"\>Zoom in</button\>
        </div\>
      </template\>
    </vue-pdf-app\>
  </div\>
</template\>

<script\>
export default {
  data() {
    return {
      idConfig: { zoomIn: "zoomInId", zoomOut: "zoomOutId" }
    };
  }
};
</script\>

ID config specification`{  cursorHandTool?: string; // <button> is recommended cursorSelectTool?: string; // <button> is recommended documentProperties?: string; // <button> is recommended download?: string; // <button> is recommended findbar?: string; // <div> is recommended findEntireWord?: string; // <input type="checkbox"> is recommended findHighlightAll?: string; // <input type="checkbox"> is recommended findMessage?: string; // <span> is recommended findInput?: string; // <input type="text"> is recommended findMatchCase?: string; // <input type="checkbox"> is recommended findNext?: string; // <button> is recommended findPrevious?: string; // <button> is recommended findResultsCount?: string; // <span> is recommended firstPage?: string; // <button> is recommended lastPage?: string; // <button> is recommended nextPage?: string; // <button> is recommended numPages?: string; // total pages qty. <span> is recommended openFile?: string; // <button> is recommended pageNumber?: string; // input for page number. <input type="number"> is recommended pageRotateCcw?: string; // <button> is recommended pageRotateCw?: string; // <button> is recommended presentationMode?: string; // <button> is recommended previousPage?: string; // <button> is recommended print?: string; // <button> is recommended scrollHorizontal?: string; // <button> is recommended scrollVertical?: string; // <button> is recommended scrollWrapped?: string; // <button> is recommended sidebarToggle?: string; // <button> is recommended spreadEven?: string; // <button> is recommended spreadNone?: string; // <button> is recommended spreadOdd?: string; // <button> is recommended toggleFindbar?: string; // <button> is recommended viewAttachments?: string; // <button> is recommended viewBookmark?: string; // <a> tag is recommended viewOutline?: string; // <button> tag is recommended viewThumbnail?: string; // <button> tag is recommended zoomIn?: string; // <button> tag is recommended zoomOut?: string; // <button> tag is recommended }`

> ℹ️ Note that elements must be in HTML document by the time vue-pdf-app is mounting (use `v-show` instead of `v-if` directive if necessary). Otherwise an error occurs.

@after-created(PDFViewerApplication)
------------------------------------

-   Description: emitted only once when Pdfjs library is binded to vue component. Can be used to set Pdfjs config before pdf document opening.
-   Arguments:
    -   PDFViewerApplication - pdf application
-   Usage:

<vue-pdf-app @after-created\="afterCreated" />

@open(PDFViewerApplication)
---------------------------

-   Description: emitted when pdf is opened but pages are not rendered.
-   Arguments:
    -   PDFViewerApplication - pdf application
-   Usage:

<vue-pdf-app @open\="openHandler" />

@pages-rendered(PDFViewerApplication)
-------------------------------------

-   Description: emitted when pdf document pages are rendered. Can be used to set default pages scale, for instance.
-   Arguments:
    -   PDFViewerApplication - pdf application
-   Usage:

<vue-pdf-app @pages-rendered\="pagesRendered" />

<script\>
export default {
  methods: {
    pagesRendered(pdfApp) {
      setTimeout(() \=> (pdfApp.pdfViewer.currentScaleValue \= "page-height"));
    }
  }
};
</script\>

> ℹ️ Events are triggered in the following order `after-created (once) => open => pages-rendered`

Slots
-----

### Slot names

-   toolbar-left-prepend
-   toolbar-left-append
-   toolbar-middle-prepend
-   toolbar-middle-append
-   toolbar-right-prepend
-   toolbar-right-append
-   toolbar-sidebar-prepend
-   toolbar-sidebar-append
-   secondary-toolbar-prepend
-   secondary-toolbar-append
-   footer
-   NEW viewer-header: slot before `viewer-prepend` slot. Can be used to build custom toolbar.
-   NEW viewer-prepend: slot before `viewerContainer` div. Can be used to build custom toolbar.
-   NEW viewer-append: slot after `viewerContainer` div. Can be used to build custom toolbar.
-   NEW viewer-footer: slot after `viewer-append` slot. Can be used to build custom toolbar.

### Slot props

Each slot has props:

1.  toggleTheme
    
    Type: (): void.
    
    Description: toggle theme handler
    
2.  NEW isSidebarHidden
    
    Type: boolean
    
    Description: state of a sidebar (visible or hidden). Can be used to manage visibility of custom Attachments, Outline and Thumbnail buttons
    
3.  NEW isFindbarHidden
    
    Type: boolean
    
    Description: state of a findbar (visible or hidden). Can be used to manage visibility of custom findbar
    

<vue-pdf-app\>
  <template #toolbar-left-prepend="{ toggleTheme }">
    <button @click="toggleTheme" type="button">Toggle theme</button>
  </template>
</vue-pdf-app\>

Color customization (IE11 not supported)
========================================

Colors of the pdf viewer are customized via custom css properties:

<style\>
  /\* for dark theme \*/
  .pdf-app.dark {
    \--pdf-toolbar-color: black;
  }

  /\* for light theme \*/
  .pdf-app.light {
    \--pdf-toolbar-color: white;
  }
</style\>

Custom css properties specification

Property

Applied to selectors

Description

\--pdf-app-background-color

.pdf-app

Background color for root pdf container

\--pdf-button-hover-font-color

.pdf-app .toolbarButton:hover

* * *

.pdf-app .toolbarButton:focus

* * *

.pdf-app .dropdownToolbarButton:hover

* * *

.pdf-app .secondaryToolbarButton:hover

* * *

.pdf-app .secondaryToolbarButton:focus

* * *

Hover color for buttons of toolbar and secondary toolbar

\--pdf-button-toggled-color

.pdf-app .toolbarButton.toggled

* * *

.pdf-app .splitToolbarButton.toggled > .toolbarButton.toggled

* * *

.pdf-app .secondaryToolbarButton.toggled

* * *

.pdf-app .outlineItemToggler:hover

* * *

.pdf-app .outlineItemToggler:hover + a

* * *

.pdf-app .outlineItemToggler:hover ~ .outlineItems

* * *

.pdf-app .outlineItem > a:hover

* * *

.pdf-app .attachmentsItem > button:hover

Background color for toggleable buttons when selected, outline items on hover, attachment items on hover

\--pdf-dialog-button-color

.pdf-app .dialog .overlayButton

\--pdf-dialog-button-font-color

.pdf-app .dialog .overlayButton

\--pdf-error-more-info-color

.pdf-app #errorMoreInfo

\--pdf-error-more-info-font-color

.pdf-app #errorMoreInfo

\--pdf-error-wrapper-color

.pdf-app #errorWrapper

\--pdf-find-input-placeholder-font-color

.pdf-app #findInput::placeholder

\--pdf-find-message-font-color

.pdf-app #findMsg

\--pdf-find-results-count-color

.pdf-app #findResultsCount

\--pdf-find-results-count-font-color

.pdf-app #findResultsCount

\--pdf-horizontal-toolbar-separator-color

.pdf-app .horizontalToolbarSeparator

\--pdf-input-color

.pdf-app .toolbarField

\--pdf-input-font-color

.pdf-app .toolbarField

\--pdf-loading-bar-color

.pdf-app #loadingBar .progress

\--pdf-loading-bar-secondary-color

.pdf-app #loadingBar .progress.indeterminate .glimmer

\--pdf-not-found-color

.pdf-app #findInput.notFound

\--pdf-overlay-container-color

.pdf-app #overlayContainer

Background color for overlay container of dialogs

\--pdf-overlay-container-dialog-color

.pdf-app #overlayContainer > .container > .dialog

Background color for document properties, password, print dialogs

\--pdf-overlay-container-dialog-font-color

.pdf-app #overlayContainer > .container > .dialog

Font color for document properties, password, print dialogs

\--pdf-overlay-container-dialog-separator-color

.pdf-app .dialog .separator

\--pdf-sidebar-content-color

.pdf-app #sidebarContent

Background color for sidebar

\--pdf-split-toolbar-button-separator-color

.pdf-app .splitToolbarButtonSeparator

* * *

.pdf-app .verticalToolbarSeparator

\--pdf-thumbnail-selection-ring-selected-color

.pdf-app .thumbnail.selected > .thumbnailSelectionRing

Border color for selected thumbnail

\--pdf-thumbnail-selection-ring-color

.pdf-app a:focus > .thumbnail > .thumbnailSelectionRing

* * *

.pdf-app .thumbnail:hover > .thumbnailSelectionRing

Border color for thumbnail on hover and focus

\--pdf-toolbar-color

.pdf-app #toolbarContainer

* * *

.pdf-app .findbar

* * *

.pdf-app .secondaryToolbar

* * *

.pdf-app .doorHanger:after

* * *

.pdf-app .doorHangerRight:after

* * *

.pdf-app .dropdownToolbarButton > select

* * *

.pdf-app .dropdownToolbarButton > select > option

Background color for toolbar, findbar, secondary toolbar, page scale dropdown

\--pdf-toolbar-font-color

.pdf-app .toolbarButton

* * *

.pdf-app .dropdownToolbarButton

* * *

.pdf-app .secondaryToolbarButton

* * *

.pdf-app .dropdownToolbarButton > select

* * *

.pdf-app .toolbarLabel

* * *

.pdf-app .outlineItem > a

* * *

.pdf-app .attachmentsItem > button

Font color for toolbar, findbar, secondary toolbar, page scale dropdown, attachments name

\--pdf-toolbar-sidebar-color

.pdf-app #toolbarSidebar

Icons customization
===================

To use default icons `import "vue-pdf-app/dist/icons/main.css";`.

To use custom icons you have to implement icons.css:

.vue-pdf-app-icon::before,
.vue-pdf-app-icon::after {
  font-family: "your font family";
}

.vue-pdf-app-icon.zoom-out::before {
  content: "icon code";
}

Light/dark themes
=================

Algorithm of theme apply

Toggle theme button is not implemented by default. It's up to you to decide where to place it. The button can be implemented with slots:

<vue-pdf-app\>
  <template #footer="{ toggleTheme }">
    <button @click="toggleTheme" type="button">Toggle theme</button>
  </template>
</vue-pdf-app\>

Localized panel
===============

English is the default language for panel. Use `<link rel="resource" type="application/l10n" href="path-to-localization-file">` in your html for localization. See localization file examples.

Examples
========

Script tag (unpkg)
------------------

<!DOCTYPE html\>
<html lang\="en"\>
  <head\>
    <meta name\="viewport" content\="width=device-width, initial-scale=1.0" />
    <meta charset\="utf-8" />
    <title\>Vue-pdf-app demo</title\>
    <link
      rel\="stylesheet"
      href\="https://unpkg.com/vue-pdf-app@2.0.0/dist/icons/main.css"
    />
    <script src\="https://unpkg.com/vue"\></script\>
    <script src\="https://unpkg.com/vue-pdf-app@2.0.0"\></script\>
    <style\>
      body,
      html {
        padding: 0;
        margin: 0;
      }
    </style\>
  </head\>

  <body\>
    <div id\="app" style\="height: 100vh;"\>
      <vue-pdf-app pdf\="/sample.pdf"\></vue-pdf-app\>
    </div\>
    <script\>
      new Vue({
        components: {
          VuePdfApp: window\["vue-pdf-app"\]
        }
      }).$mount("#app");
    </script\>
  </body\>
</html\>

Typescript
----------

<template\>
  <div id\="app"\>
    <vue-pdf-app pdf\="/sample.pdf"\></vue-pdf-app\>
  </div\>
</template\>

<script lang="ts">
import "vue-pdf-app/dist/icons/main.css";
import VuePdfApp from "vue-pdf-app";
import { Component, Vue } from "vue-property-decorator";
@Component({
  components: {
    VuePdfApp
  }
})
export default class App extends Vue {}
</script\>

Lazy loading
------------

PDFJS is a huge package (see the library size table above). So use lazy loading to split your bundle into small pieces.

<template\>
  <div id\="app"\>
    <vue-pdf-app\></vue-pdf-app\>
  </div\>
</template\>

<script\>
import "vue-pdf-app/dist/icons/main.css";
import Loader from "./components/Loader.vue";
export default {
  name: "App",
  components: {
    "vue-pdf-app": () \=> ({
      component: new Promise((res) \=> {
        return setTimeout(
          () \=> res(import(/\* webpackChunkName: "pdf-viewer" \*/ "vue-pdf-app")),
          4000
        );
      }),
      loading: Loader
    })
  }
};
</script\>

PDFJS interaction
-----------------

You can interact with pdfjs library when pdf is opened via `open` event.

<template\>
  <div id\="app"\>
    <div id\="pdf-wrapper"\>
      <vue-pdf-app pdf\="/sample.pdf" @open\="openHandler"\></vue-pdf-app\>
    </div\>
    <div id\="info"\>
      <h1\>PDF info:</h1\>
      <div v-for\="item in info" :key\="item.name"\>
        <span\>{{ item.name }}: {{ item.value }}</span\>
        <br />
      </div\>
    </div\>
  </div\>
</template\>

<script\>
import "vue-pdf-app/dist/icons/main.css";
import VuePdfApp from "vue-pdf-app";
export default {
  name: "App",
  components: {
    VuePdfApp
  },
  data() {
    return {
      info: \[\]
    };
  },
  methods: {
    async openHandler(pdfApp) {
      this.info \= \[\];
      const info \= await pdfApp.pdfDocument
        .getMetadata()
        .catch(console.error.bind(console));
      if (!info) return;
      const props \= Object.keys(info.info);
      props.forEach((prop) \=> {
        const obj \= {
          name: prop,
          value: info.info\[prop\]
        };
        this.info.push(obj);
      });
    }
  }
};
</script\>
