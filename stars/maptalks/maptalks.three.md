---
project: maptalks.three
stars: 577
description: A maptalks layer to render with three.js.
url: https://github.com/maptalks/maptalks.three
---

maptalks.three
==============

A maptalks Layer to render with three.js

20220116\_213033.mp4

Examples
--------

-   Demos.

Install
-------

-   Install with npm: `npm install maptalks.three`.
-   Download from dist directory.
-   Use unpkg CDN: `https://unpkg.com/maptalks.three/dist/maptalks.three.min.js`

Incompatible changes
--------------------

-   three.js >=128 the default umd package is ES6
-   Starting from version 0.16.0, the default umd package is ES6,To fit the new version of three.js about three umd package change
-   If your running environment does not support ES6, we also provide Es5 version maptalks.three.es5.js,This requires the version of three.js < = 127,

Migration from <=v0.5.x to v0.6.0
---------------------------------

-   Re-implementated locateCamera, sync with map's projMatrix and viewMatrix.
-   Model's z position is reversed from v0.5.0. So if you have models rendered with v0.5.x, rotation needs to be updated.
-   For THREE <= 0.94, material's side need to set to THREE.BackSide or THREE.DoubleSide to render correctly
    -   THREE >= 0.95 doesn't need, maybe due to #14379
-   Add support for THREE >= 0.93
-   Add support for GroupGLLayer

Usage
-----

As a plugin, `maptalks.three` must be loaded after `maptalks.js` and `three.js` in browsers.

<script type\="text/javascript" src\="https://unpkg.com/three@0.138.0/build/three.min.js"\></script\>
<script type\="text/javascript" src\="https://unpkg.com/maptalks/dist/maptalks.min.js"\></script\>
<script type\="text/javascript" src\="https://unpkg.com/maptalks.three/dist/maptalks.three.js"\></script\>
<script\>
var threeLayer \= new maptalks.ThreeLayer('t');
threeLayer.prepareToDraw \= function (gl, scene, camera) {
    var light \= new THREE.DirectionalLight(0xffffff);
    light.position.set(0, \-10, \-10).normalize();
    scene.add(light);

    var material \= new THREE.MeshPhongMaterial();
    countries.features.forEach(function (g) {
        //g is geojson Feature
        var num \= g.properties.population;

        var extrudePolygon\=threeLayer.toExtrudePolygon(g, { height: num }, material);
        threeLayer.addMesh(extrudePolygon)
    });
};

map.addLayer(threeLayer);
</script\>

With ES Modules:

import \* as THREE from 'three';
import \* as maptalks from 'maptalks';
import { ThreeLayer } from 'maptalks.three';

const map \= new maptalks.Map('map', { /\* options \*/ });

const threeLayer \= new ThreeLayer('t');
threeLayer.prepareToDraw \= function (gl, scene, camera) {
    const light \= new THREE.DirectionalLight(0xffffff);
    light.position.set(0, \-10, \-10).normalize();
    scene.add(light);
    //...
};

threeLayer.addTo(map);

Supported Browsers
------------------

IE 11, Chrome, Firefox, other modern and mobile browsers that support WebGL;

API Reference
-------------

### API

Contributing
------------

We welcome any kind of contributions including issue reportings, pull requests, documentation corrections, feature requests and any other helps.

Develop
-------

The only source file is `index.js`.

It is written in ES6, transpiled by babel and tested with mocha and expect.js.

### Scripts

-   Install dependencies

$ npm install

-   Watch source changes and generate runnable bundle repeatedly

$ npm run dev

-   Package and generate minified bundles to dist directory

$ npm run build

-   Lint

$ npm run lint

Publication
-----------

npm version ${version}
npm publish
npm push master ${version}
