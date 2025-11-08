---
project: checkboxland
stars: 944
description: Render anything as HTML checkboxes
url: https://github.com/bryanbraun/checkboxland
---

Checkboxland
============

Checkboxland is a JavaScript library for rendering anything as HTML checkboxes.

You can use it to display animations, text, images, video, and arbitrary data. It also supports plugins, so you can add your own APIs.

Checkboxland is dependency-free, framework-agnostic, and fun! 🙃

**For more details see the docs.**

Setup
-----

Install this package via npm:

```
npm install checkboxland
```

Example
-------

Import it into your application, and create a checkbox grid:

```
import { Checkboxland } from 'checkboxland';

const cbl = new Checkboxland({ dimensions: '8x7', selector: '#my-container' });

// Create a data representation of the heart.
const heart = [
  [0,1,1,0,0,1,1,0],
  [1,0,0,1,1,0,0,1],
  [1,0,0,0,0,0,0,1],
  [1,0,0,0,0,0,0,1],
  [0,1,0,0,0,0,1,0],
  [0,0,1,0,0,1,0,0],
  [0,0,0,1,1,0,0,0],
];

// This updates the grid with the data we provided.
cbl.setData(heart);
```

Contributing
------------

Checkboxland is designed to be extendable. If you want to add a feature, first ask yourself if it could be done as an external plugin.

If you contribution requires a change to the core library, follow these steps:

1.  Fork/Clone the repo.
2.  Make your changes on a feature branch.
3.  Run the docs site locally (`npm run dev`) to confirm that the demos still work as expected.
4.  Submit a Pull Request.

License
-------

MIT
