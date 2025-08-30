---
project: three.js
stars: 108332
description: JavaScript 3D Library.
url: https://github.com/mrdoob/three.js
---

three.js
========

#### JavaScript 3D library

The aim of the project is to create an easy-to-use, lightweight, cross-browser, general-purpose 3D library. The current builds only include WebGL and WebGPU renderers but SVG and CSS3D renderers are also available as addons.

Examples — Docs — Manual — Wiki — Migrating — Questions — Forum — Discord

### Usage

This code creates a scene, a camera, and a geometric cube, and it adds the cube to the scene. It then creates a `WebGL` renderer for the scene and camera, and it adds that viewport to the `document.body` element. Finally, it animates the cube within the scene for the camera.

import \* as THREE from 'three';

const width \= window.innerWidth, height \= window.innerHeight;

// init

const camera \= new THREE.PerspectiveCamera( 70, width / height, 0.01, 10 );
camera.position.z \= 1;

const scene \= new THREE.Scene();

const geometry \= new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
const material \= new THREE.MeshNormalMaterial();

const mesh \= new THREE.Mesh( geometry, material );
scene.add( mesh );

const renderer \= new THREE.WebGLRenderer( { antialias: true } );
renderer.setSize( width, height );
renderer.setAnimationLoop( animate );
document.body.appendChild( renderer.domElement );

// animation

function animate( time ) {

	mesh.rotation.x \= time / 2000;
	mesh.rotation.y \= time / 1000;

	renderer.render( scene, camera );

}

If everything goes well, you should see this.

### Cloning this repository

Cloning the repo with all its history results in a ~2 GB download. If you don't need the whole history you can use the `depth` parameter to significantly reduce download size.

git clone --depth=1 https://github.com/mrdoob/three.js.git

### Change log

Releases
