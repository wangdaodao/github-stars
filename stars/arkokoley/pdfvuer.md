---
project: pdfvuer
stars: 932
description: A PDF viewer for Vue using Mozilla's PDF.js that supports both Vue2 and Vue3
url: https://github.com/arkokoley/pdfvuer
---

Pdfvuer
=======

> A PDF viewer for Vue using Mozilla's PDF.js

Install
-------

For Vue 2:

```
npm install --save pdfvuer
```

For Vue 3:

```
npm i pdfvuer@next --save
```

Example - basic
---------------

<template\>
  <pdf src\="./static/relativity.pdf" :page\="1"\>
    <template slot="loading">
      loading content here...
    </template\>
  </pdf\>
</template\>

<script\>
import pdf from 'pdfvuer'
import 'pdfjs-dist/build/pdf.worker.entry' // not needed since v1.9.1
export default {
  components: {
    pdf
  }
}
</script\>

Example - Advanced
------------------

<template\>
  <div id\="pdfvuer"\>
    <div id\="buttons" class\="ui grey three item inverted bottom fixed menu transition hidden"\>
      <a class\="item" @click\="page > 1 ? page-- : 1"\>
        <i class\="left chevron icon"\></i\>
        Back
      </a\>
      <a class\="ui active item"\>
        {{page}} / {{ numPages ? numPages : '∞' }}
      </a\>
      <a class\="item" @click\="page < numPages ? page++ : 1"\>
        Forward
        <i class\="right chevron icon"\></i\>
      </a\>
    </div\>
    <div id\="buttons" class\="ui grey three item inverted bottom fixed menu transition hidden"\>
      <a class\="item" @click\="scale -= scale > 0.2 ? 0.1 : 0"\>
        <i class\="left chevron icon" />
          Zoom -
      </a\>
      <a class\="ui active item"\>
        {{ formattedZoom }} %
      </a\>
      <a class\="item" @click\="scale += scale < 2 ? 0.1 : 0"\>
        Zoom +
        <i class\="right chevron icon" />
      </a\>
    </div\>
    <pdf :src\="pdfdata" v-for\="i in numPages" :key\="i" :id\="i" :page\="i"
      :scale.sync\="scale" style\="width:100%;margin:20px auto;"
        :annotation\="true"
        :resize\="true"
        @link-clicked\="handle\_pdf\_link"\>
      <template slot="loading">
        loading content here...
      </template\>
    </pdf\>
  </div\>
</template\>

<script\>
import pdfvuer from 'pdfvuer'
import 'pdfjs-dist/build/pdf.worker.entry' // not needed since v1.9.1
export default {
  components: {
    pdf: pdfvuer
  },
  data () {
    return {
      page: 1,
      numPages: 0,
      pdfdata: undefined,
      errors: \[\],
      scale: 'page-width'
    }
  },
  computed: {
    formattedZoom () {
        return Number.parseInt(this.scale \* 100);
    },
  },
  mounted () {
    this.getPdf()
  },
  watch: {
    show: function (s) {
      if(s) {
        this.getPdf();
      }
    },
    page: function (p) {
      if( window.pageYOffset <= this.findPos(document.getElementById(p)) || ( document.getElementById(p+1) && window.pageYOffset \>= this.findPos(document.getElementById(p+1)) )) {
        // window.scrollTo(0,this.findPos(document.getElementById(p)));
        document.getElementById(p).scrollIntoView();
      }
    }
  },
  methods: {
    handle\_pdf\_link: function (params) {
      // Scroll to the appropriate place on our page - the Y component of
      // params.destArray \* (div height / ???), from the bottom of the page div
      var page \= document.getElementById(String(params.pageNumber));
      page.scrollIntoView();
    },
    getPdf () {
      var self \= this;
      self.pdfdata \= pdfvuer.createLoadingTask('./static/relativity.pdf');
      self.pdfdata.then(pdf \=> {
        self.numPages \= pdf.numPages;
        window.onscroll \= function() { 
          changePage() 
          stickyNav()  
        }
        // Get the offset position of the navbar
        var sticky \= $('#buttons')\[0\].offsetTop
        // Add the sticky class to the self.$refs.nav when you reach its scroll position. Remove "sticky" when you leave the scroll position
        function stickyNav() {
          if (window.pageYOffset \>= sticky) {
            $('#buttons')\[0\].classList.remove("hidden")
          } else {
            $('#buttons')\[0\].classList.add("hidden")
          }
        }
        function changePage () {
          var i \= 1, count \= Number(pdf.numPages);
          do {
            if(window.pageYOffset \>= self.findPos(document.getElementById(i)) && 
                window.pageYOffset <= self.findPos(document.getElementById(i+1))) {
              self.page \= i
            }
            i++
          } while ( i < count)
          if (window.pageYOffset \>= self.findPos(document.getElementById(i))) {
            self.page \= i
          }
        }
      });
    },
    findPos(obj) {
      return obj.offsetTop;
    }
  }
}
</script\>
<style src="pdfvuer/dist/pdfvuer.css"></style\>
<style lang="css" scoped>
  #buttons {
    margin-left: 0 !important;
    margin-right: 0 !important;
  }
  /\* Page content \*/
  .content {
    padding: 16px;
  }
</style\>

API
---

### Props

#### :src String / Object - default: ''

The url of the pdf file. `src` may also be a `string|TypedArray|DocumentInitParameters|PDFDataRangeTransport` for more details, see `PDFJS.getDocument()`.

#### :page Number - default: 1

The page number to display.

#### :rotate Number - default: 0

The page rotation in degrees, only multiple of 90 are valid.

#### :scale Number / String - default: 'page-width' - .sync

The scaling factor. By default, the pdf will be scaled to match the page width with the container width. When passed value `page-width` and / or using `resize` prop, will send back the scale computed accordingly via `update:scale` event (use it with `scale.sync="scale"`)

#### :resize Boolean - default: false

Enable Auto Resizing on window resize. By default, autoresizing is disabled.

#### :annotation Boolean - default: false

Show the annotations in the pdf. By default, annotation layer is disabled.

#### :text Boolean - default: true

Show the text layer in the pdf. By default, text layer is enabled.

### Events

#### @numpages Number

The total number of pages of the pdf.

#### @loading Boolean

The provided PDF's loading state

#### @error Function

Function handler for errors occurred during loading/drawing PDF source.

#### @link-clicked Function

Function handler for errors occurred during loading/drawing PDF source. Example:

    handle\_pdf\_link: function (params) {
      // Scroll to the appropriate place on our page - the Y component of
      // params.destArray \* (div height / ???), from the bottom of the page div
      var page \= document.getElementById(String(params.pageNumber));
      page.scrollIntoView();
    }

### Public static methods

#### createLoadingTask(src)

-   `src`: see `:src` prop  
    This function creates a PDFJS loading task that can be used and reused as `:src` property.

Public Demo
-----------

Advanced Example - https://arkokoley.github.io/pdfvuer

Used in production by Gratia

> Made with ❤️ in Bangalore, India

License
-------

MIT © Gaurav Koley, 2021
