---
project: maptalks.js
stars: 4455
description: A light and plugable JavaScript library for integrated 2D/3D maps.
url: https://github.com/maptalks/maptalks.js
---

maptalks-gl
===========

NOTICE
------

maptalks is upgrading to maptalks-gl, a webgl and webgpu driven 2D/3D map engine.

If you are looking for the old maptalks source codes, it has moved to packages/maptalks as a submodule.

About
-----

maptalks-gl will be a pure WebGL driven map engine with performance and rich features in 3D. maptalks-gl is in active development now, and will be officially published in few months.

With consistent API upgrade, you can easily migrate from legacy maptalks to maptalks-gl. (TBD)

If you are interested in what is going on, please refer to the previous releases notes of maptalks-gl.

Features
--------

-   Vector Tile format support
-   3DTiles format support
-   GLTF format support
-   Magnificant performance enhancement by WebGL
-   Rich 3D analysis functions
-   Traffic simulation animations

Usage
-----

### Install

npm i maptalks-gl

#or

yarn add maptalks-gl

#or

pnpm i maptalks-gl

### ESM

import {
    Map,
    GroupGLLayer,
    VectorTileLayer,
    GLTFMarker,
    GLTFLayer,
    PolygonLayer
} from 'maptalks-gl';

const map \= new Map('map', {
    center: \[0, 0\],
    zoom: 2
});
const vtLayer \= new VectorTileLayer('vt', {
    urlTemplate: 'http://tile.maptalks.com/test/planet-single/{z}/{x}/{y}.mvt'
});

const groupLayer \= new GroupGLLayer('group', \[vtLayer\]).addTo(map);

const gltfLayer \= new GLTFLayer('gltflayer');
groupLayer.addLayer(gltfLayer);

const polygonLayer \= new PolygonLayer('polygonlayer');
groupLayer.addLayer(polygonLayer);
//other layers

### CDN

You can also reference umd-formatted packages via CDN, note that all exported variables under the gl system are automatically mounted in the `maptalks` namespace.

<script type\="text/javascript" src\="https://unpkg.com/maptalks-gl/dist/maptalks-gl.js"\></script\>
<script type\="text/javascript"\>
    const map \= new maptalks.Map('map', {
        center: \[0, 0\],
        zoom: 2
    });
    const vtLayer \= new maptalks.VectorTileLayer('vt', {
        urlTemplate: 'http://tile.maptalks.com/test/planet-single/{z}/{x}/{y}.mvt'
    });

    const groupLayer \= new maptalks.GroupGLLayer('group', \[vtLayer\]).addTo(map);

    const gltfLayer \= new maptalks.GLTFLayer('gltflayer');
    groupLayer.addLayer(gltfLayer)
    const polygonLayer \= new maptalks.PolygonLayer('polygonlayer');
    groupLayer.addLayer(polygonLayer);
    //other layers
</script\>

### Optional transcoders

If you need to introduce optional draco, ktx2 and other gl format decoding plugins, just introduce the decoding plugins after introducing the summary package as before:

import {
    Map,
    Geo3DTilesLayer,
    GLTFLayer
} from 'maptalks-gl';
import '@maptalks/transcoders.draco';
import '@maptalks/transcoders.crn';
import '@maptalks/transcoders.ktx2';

or with umd bundle：

<link rel\="stylesheet" href\="https://unpkg.com/maptalks-gl/dist/maptalks-gl.css"\>
<script type\="text/javascript" src\="https://unpkg.com/maptalks-gl/dist/maptalks-gl.js"\></script\>
<script type\="text/javascript" src\="https://unpkg.com/@maptalks/transcoders.draco/dist/transcoders.draco.js"\></script\>
<script type\="text/javascript" src\="https://unpkg.com/@maptalks/transcoders.crn/dist/transcoders.crn.js"\></script\>
<script type\="text/javascript" src\="https://unpkg.com/@maptalks/transcoders.ktx2/dist/transcoders.ktx2.js"\></script\>

Packages introductions
----------------------

### basic libraries

-   `gltf-loader` gltf format parsing library.
-   `reshader.gl` A regl-based implementation of the 3D rendering interface, including renderer, scene, mesh, material and other commonly used rendering base classes and predefined rendering materials, such as PBR.

### Map

-   `maptalks` maptalks library source codes.

### Layers

-   `gl` WebGL base layer functionality, including GroupGLLayer, terrain, post-processing and various 3D mask implementations.
-   `layer-3dtiles` Implementation of the 3dtiles layer (Geo3DTilesLayer).
-   `layer-gltf` Implementation of gltf layer (GLTFLayer/GLTFMarker).
-   `layer-video` video layer (VideoLayer/VideoSurface) implementation

### Vector tiles

-   `vt-plugin` Interface definition for the vector tile rendering plugin.
-   `vt` Vector tile layer (VectorTileLayer/GeoJSONVectorTileLayer) implementation.

### Three-dimensional analysis

-   `analysis` Implementation of various 3D analysis functions.
-   `traffic` Implementation of traffic simulation.

### transcoders

-   `transcoders.crn` crn format parsing library
-   `transcoders.draco` draco format parser library
-   `transcoders.ktx` ktx2 compressed texture format parser library.

Installation and compilation
----------------------------

### node environment

The current minimum node environment is 18.16.1, if you don't meet the minimum node version requirement, you can use nvm / fnm to manage the node version.

### pnpm version

Currently this project is using pnpm@9.x.

### Install dependencies

pnpm i

### Compile

pnpm build

### Debugging

If you need to debug the code base in watch mode, and the target of the compilation contains the source code, run the following command in the root folder of package you are debugging:

pnpm run dev

Test
----

The project uses karma or electron-mocha (vt vs. layer-3dtiles) as the test framework, and the test cases are written based on mocha syntax.

### Run a full test of the project

Run `npm test` under each project.

### Run the tests for the specified use case

-   If the project is based on electron-mocha, run the

pnpm run tdd -- -g “spec keywords”

-   If the project is based on karma, you need to modify the test source code to specify the use cases to run via the only method in mocha, e.g..

it('spec name', () \=> {});

Change to:

it.only('spec name', () \=> {});
