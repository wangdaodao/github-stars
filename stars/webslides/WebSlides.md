---
project: WebSlides
stars: 6241
description: Create HTML presentations in seconds —
url: https://github.com/webslides/WebSlides
---

WebSlides = Create stories with Karma
=====================================

Finally, everything you need to make HTML presentations, landings, and longforms in a beautiful way. Just a basic knowledge of HTML and CSS is required. Designers, marketers, and journalists can now focus on the content. — https://webslides.tv/demos.

* * *

### Download

Simply choose a demo and customize it in seconds. Latest version: webslides.tv/webslides-latest.zip.

* * *

### What's in the download?

The download includes demos and images (devices and logos). All content is for demo purposes only. Images are property of their respective owners.

```
webslides/
├── index.html
├── css/
│   ├── base.css
│   └── colors.css
│   └── svg-icons.css (optional)
├── js/
│   ├── webslides.js
│   └── svg-icons.js (optional)
└── demos/
└── images/
```

Features
--------

-   Navigation (horizontal and vertical sliding): remote presenters, touchpad, keyboard shortcuts, and swipe.
-   Slide counter.
-   Permalinks: go to a specific slide.
-   Autoslide.
-   Click to nav.
-   Simple CSS alignments. Put content wherever you want (vertical centering...)
-   40+ components: background images/videos, quotes, cards, covers...
-   Flexible blocks with auto-fill and equal height.
-   Fonts: Roboto, Maitree (Serif), and San Francisco.
-   Vertical rhythm (use multiples of 8).

Markup
------

-   Code is clean and scalable. It uses intuitive markup with popular naming conventions. There's no need to overuse classes or nesting.
-   Each parent `<section>` in the `#webslides` element is an individual slide.

<article id\="webslides"\>
    <section\>
        <h1\>Slide 1</h1\>
    </section\>
    <section class\="bg-black aligncenter"\>
    <!-- .wrap = container 1200px -->
        <div class\="wrap"\>
            <h1\>Slide 2</h1\>
        </div\>
    </section\>
</article\>

### Vertical Sliding

<article id\="webslides" class\="vertical"\>

### CSS Syntax (classes)

-   Typography: `.text-landing`, `.text-data`, `.text-intro`...
-   Background Colors: `.bg-primary`, `.bg-apple`, `.bg-blue`...
-   Background Images: `.background`,`.background-center-bottom`...
-   Cards: `.card-50`, `.card-40`...
-   Flexible Blocks: `.flexblock.clients`, `.flexblock.metrics`...

### Extensions

You can add:

-   Unsplash photos
-   animate.css
-   particles.js
-   Animate on scroll (Useful for longform articles)
-   pt

### Dive In!

-   Do not miss our demos.
-   Want to get techie? Read our wiki:
    -   FAQ
    -   Core API
    -   Plugin Docs
    -   Plugin Development

### Credits

-   WebSlides was created by @jlantunez using Cactus.
-   Javascript: @Belelros and @LuisSacristan.
-   Based on SimpleSlides, by @JennSchiffer.
