---
project: MathJax
stars: 10558
description: Beautiful and accessible math in all browsers
url: https://github.com/mathjax/MathJax
---

MathJax
=======

Beautiful math in all browsers
------------------------------

MathJax is an open-source JavaScript display engine for LaTeX, MathML, and AsciiMath notation that works in all modern browsers, with built-in support for assistive technology like screen readers, including automatic speech generation and an expression explorer that can be used to investigate typeset mathematics on a more granular level than the complete expression. It requires no setup on the part of the user (no plugins to download or software to install), so the page author can write web documents that include mathematics and be confident that users will be able to view it naturally and easily. Simply include MathJax and some mathematics in a web page, and MathJax does the rest.

Some of the main features of MathJax include:

-   High-quality display of LaTeX, MathML, and AsciiMath notation in HTML pages
    
-   Supported in most browsers with no plug-ins, extra fonts, or special setup for the reader
    
-   Easy for authors, flexible for publishers, extensible for developers
    
-   Supports math accessibility, cut-and-paste interoperability, and other advanced functionality
    
-   Powerful API for integration with other web applications
    

See http://www.mathjax.org/ for additional details about MathJax, and https://docs.mathjax.org for the MathJax documentation.

MathJax Components
------------------

MathJax uses files called _components_ that contain the various MathJax modules that you can include in your web pages or access on a server through NodeJS. Some components combine all the pieces you need to run MathJax with one or more input formats and a particular output format, while other components are pieces that can be loaded on demand when needed, or by a configuration that specifies the pieces you want to combine in a custom way. For usage instructions, see the MathJax documentation.

Components provide a convenient packaging of MathJax's modules, but it is possible for you to form your own custom components, or to use MathJax's modules directly in a node application on a server. There are web examples showing how to use MathJax in web pages and how to build your own components, and node examples illustrating how to use components in node applications or call MathJax modules directly.

What's in this Repository
-------------------------

This repository contains only the component files for MathJax, not the source code for MathJax (which are available in a separate MathJax source repository). These component files are the ones served by the CDNs that offer MathJax to the web. In version 2, the files used on the web were also the source files for MathJax, but in version 3 and above, the source files are no longer on the CDN, as they are not what are run in the browser.

The components are ES6 format as CommonJS modules.

Installation and Use
--------------------

### Using MathJax components from a CDN on the web

If you are loading MathJax from a CDN into a web page, there is no need to install anything. Simply use a `script` tag that loads MathJax from the CDN. E.g.,

<script src\="https://cdn.jsdelivr.net/npm/mathjax@4/tex-mml-chtml.js" defer\></script\>

See the MathJax documentation and the MathJax Web Demos, and the MathJax Node Demos for more information.

### Hosting your own copy of the MathJax Components

If you want to host MathJax from your own server, you can do so by installing the `mathjax` package using `npm` and moving the contents to an appropriate location on your server:

```
npm install mathjax@4
mv node_modules/mathjax <path-to-server-location>/mathjax
```

Alternatively, you can get the files via GitHub:

```
git clone https://github.com/mathjax/MathJax.git mathjax
mv mathjax <path-to-server-location>/mathjax
rm -rf mathjax
```

Then (in either case) you can use a script tag like the following:

<script src\="<url-to-your-site>/mathjax/tex-chtml.js" defer\></script\>

where `<url-to-your-site>` is replaced by the URL to the location where you moved the MathJax files above.

See the documentation for details.

### Using MathJax components in a node application

To use MathJax components in a node application, install the `mathjax` package:

npm install mathjax@4

Then import `mathjax` within your application and initialize it:

import MathJax from 'mathjax';
await MathJax.init({ ... });

where `{ ... }` is the MathJax configuration you want to use. E.g.,

import MathJax from 'mathjax';
await MathJax.init({
  loader: {load: \['input/tex', 'output/svg'\]}
});
const svg \= await MathJax.tex2svgPromise('\\\\frac{1}{x^2-1}', {display: true});
console.log(MathJax.startup.adaptor.outerHTML(svg));

Alternatively, in an ES5 node application, you can use

const MathJax \= require('mathjax');
MathJax.init({ ... }).then(() \=> { ... });

where the first `{ ... }` is a MathJax configuration, and the second `{ ... }` is the code to run after MathJax has been loaded. E.g.

const MathJax \= require('mathjax');
MathJax.init({
  loader: {load: \['input/tex', 'output/svg'\]}
}).then(() \=> {
  const svg \= MathJax.tex2svg('\\\\frac{1}{x^2-1}', {display: true});
  console.log(MathJax.startup.adaptor.outerHTML(svg));
}).catch((err) \=> console.log(err.message));

**Note:** the technique in the two examples above is for node-based application only, not for browser applications. This method sets up an alternative DOM implementation, which you don't need in the browser, and it depends on node and the local file system in other ways. This setup will not work properly in the browser, even if you webpack it or use some other bundler.

See the documentation and the MathJax Node Repository for more details.

Reducing the Size of the Components Directory
---------------------------------------------

Since the MathJax package contains _all_ the component files, so if you are only planning one use one configuration, you can reduce the size of the MathJax directory by removing unused components. For example, if you are using the `tex-chtml.js` component, then you can remove the `tex-mml-chtml.js`, `tex-svg.js`, `tex-mml-svg.js`, and the files ending in `-nofont.js`, which will save considerable space. Indeed, you should be able to remove everything other than `tex-chtml.js`, and the `input/tex/extensions`, `adaptors`, `a11y`, and `sre` directories. If you are using the results only on the web, you can remove `adaptors` as well. If you are using MathML input rather than TeX (e.g., `mml-chtml.js` rather than `tex-chtml.js`), then you can remove `input/tex/extensions` as well.

If you are using a font other than the default `mathjax-newcm` font in a node application, then you will need to install that font as well. E.g.,

npm install @mathjax/mathjax-stix2-font@4

to install the `mathjax-stix2` font locally. On the web, MathJax will look for the font and its dynamic ranges on the `cdn.jsdelivr.net` CDN service, so if you want to use the font from your own server, you will need to configure the path to the font. For example:

MathJax \= {
  loader: {
    paths: {
      'mathjax-stix2': '<url-to-your-server>/mathjax-stix2-font'
    }
  }
};

to set the location for the `mathjax-stix2` font to a URL on your server.

The Component Files and Pull Requests
-------------------------------------

The contents of this repository are generated automatically, so you should not submit pull requests that modify this repository. If you wish to submit a modification to MathJax, you should make a pull request in the MathJax source repository.

MathJax Community
-----------------

The main MathJax website is http://www.mathjax.org, and it includes announcements and other important information. A MathJax user forum for asking questions and getting assistance is hosted at Google, and the MathJax bug tracker is hosted at GitHub.

Before reporting a bug, please check that it has not already been reported. Also, please use the bug tracker (rather than the help forum) for reporting bugs, and use the user's forum (rather than the bug tracker) for questions about how to use MathJax.

MathJax Resources
-----------------

-   MathJax Documentation
-   MathJax Components
-   MathJax Source Code
-   MathJax Web Examples
-   MathJax Node Examples
-   MathJax Bug Tracker
-   MathJax Users' Group
