---
project: FileSaver.js
stars: 21908
description: An HTML5 saveAs() FileSaver implementation
url: https://github.com/eligrey/FileSaver.js
---

If you need to save really large files bigger than the blob's size limitation or don't have enough RAM, then have a look at the more advanced StreamSaver.js that can save data directly to the hard drive asynchronously with the power of the new streams API. That will have support for progress, cancelation and knowing when it's done writing

FileSaver.js
============

FileSaver.js is the solution to saving files on the client-side, and is perfect for web apps that generates files on the client, However if the file is coming from the server we recommend you to first try to use Content-Disposition attachment response header as it has more cross-browser compatiblity.

Looking for `canvas.toBlob()` for saving canvases? Check out canvas-toBlob.js for a cross-browser implementation.

Supported Browsers
------------------

Browser

Constructs as

Filenames

Max Blob Size

Dependencies

Firefox 20+

Blob

Yes

800 MiB

None

Firefox < 20

data: URI

No

n/a

Blob.js

Chrome

Blob

Yes

2GB

None

Chrome for Android

Blob

Yes

RAM/5

None

Edge

Blob

Yes

?

None

IE 10+

Blob

Yes

600 MiB

None

Opera 15+

Blob

Yes

500 MiB

None

Opera < 15

data: URI

No

n/a

Blob.js

Safari 6.1+\*

Blob

No

?

None

Safari < 6

data: URI

No

n/a

Blob.js

Safari 10.1+  

Blob        

Yes        

n/a          

None

Feature detection is possible:

try {
    var isFileSaverSupported \= !!new Blob;
} catch (e) {}

### IE < 10

It is possible to save text files in IE < 10 without Flash-based polyfills. See ChenWenBrian and koffsyrup's `saveTextAs()` for more details.

### Safari 6.1+

Blobs may be opened instead of saved sometimes—you may have to direct your Safari users to manually press ⌘+S to save the file after it is opened. Using the `application/octet-stream` MIME type to force downloads can cause issues in Safari.

### iOS

saveAs must be run within a user interaction event such as onTouchDown or onClick; setTimeout will prevent saveAs from triggering. Due to restrictions in iOS saveAs opens in a new window instead of downloading, if you want this fixed please tell Apple how this WebKit bug is affecting you.

Syntax
------

### Import `saveAs()` from file-saver

import { saveAs } from 'file-saver';

FileSaver saveAs(Blob/File/Url, optional DOMString filename, optional Object { autoBom })

Pass `{ autoBom: true }` if you want FileSaver.js to automatically provide Unicode text encoding hints (see: byte order mark). Note that this is only done if your blob type has `charset=utf-8` set.

Examples
--------

### Saving text using `require()`

var FileSaver \= require('file-saver');
var blob \= new Blob(\["Hello, world!"\], {type: "text/plain;charset=utf-8"});
FileSaver.saveAs(blob, "hello world.txt");

### Saving text

var blob \= new Blob(\["Hello, world!"\], {type: "text/plain;charset=utf-8"});
FileSaver.saveAs(blob, "hello world.txt");

### Saving URLs

FileSaver.saveAs("https://httpbin.org/image", "image.jpg");

Using URLs within the same origin will just use `a[download]`. Otherwise, it will first check if it supports cors header with a synchronous head request. If it does, it will download the data and save using blob URLs. If not, it will try to download it using `a[download]`.

The standard W3C File API `Blob` interface is not available in all browsers. Blob.js is a cross-browser `Blob` implementation that solves this.

### Saving a canvas

var canvas \= document.getElementById("my-canvas");
canvas.toBlob(function(blob) {
    saveAs(blob, "pretty image.png");
});

Note: The standard HTML5 `canvas.toBlob()` method is not available in all browsers. canvas-toBlob.js is a cross-browser `canvas.toBlob()` that polyfills this.

### Saving File

You can save a File constructor without specifying a filename. If the file itself already contains a name, there is a hand full of ways to get a file instance (from storage, file input, new constructor, clipboard event). If you still want to change the name, then you can change it in the 2nd argument.

// Note: Ie and Edge don't support the new File constructor,
// so it's better to construct blobs and use saveAs(blob, filename)
var file \= new File(\["Hello, world!"\], "hello world.txt", {type: "text/plain;charset=utf-8"});
FileSaver.saveAs(file);

Installation
------------

# Basic Node.JS installation
npm install file-saver --save
bower install file-saver

Additionally, TypeScript definitions can be installed via:

# Additional typescript definitions
npm install @types/file-saver --save-dev
