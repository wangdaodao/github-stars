---
project: masonry
stars: 16597
description: :love_hotel: Cascading grid layout plugin
url: https://github.com/desandro/masonry
---

Masonry
=======

_Cascading grid layout library_

Masonry works by placing elements in optimal position based on available vertical space, sort of like a mason fitting stones in a wall. You’ve probably seen it in use all over the Internet.

See masonry.desandro.com for complete docs and demos.

Install
-------

### Download

-   masonry.pkgd.js un-minified, or
-   masonry.pkgd.min.js minified

### CDN

Link directly to Masonry files on unpkg.

<script src\="https://unpkg.com/masonry-layout@4/dist/masonry.pkgd.js"\></script\>
<!-- or -->
<script src\="https://unpkg.com/masonry-layout@4/dist/masonry.pkgd.min.js"\></script\>

### Package managers

npm: `npm install masonry-layout --save`

Bower: `bower install masonry-layout --save`

Support Masonry development
---------------------------

Masonry has been actively maintained and improved upon for 8 years, with 900 GitHub issues closed. Please consider supporting its development by purchasing a license for one of Metafizzy's commercial libraries.

Initialize
----------

With jQuery

$('.grid').masonry({
  // options...
  itemSelector: '.grid-item',
  columnWidth: 200
});

With vanilla JavaScript

// vanilla JS
// init with element
var grid \= document.querySelector('.grid');
var msnry \= new Masonry( grid, {
  // options...
  itemSelector: '.grid-item',
  columnWidth: 200
});

// init with selector
var msnry \= new Masonry( '.grid', {
  // options...
});

With HTML

Add a `data-masonry` attribute to your element. Options can be set in JSON in the value.

<div class\="grid" data-masonry\='{ "itemSelector": ".grid-item", "columnWidth": 200 }'\>
  <div class\="grid-item"\></div\>
  <div class\="grid-item"\></div\>
  ...
</div\>

License
-------

Masonry is released under the MIT license. Have at it.

* * *

Made by David DeSandro
