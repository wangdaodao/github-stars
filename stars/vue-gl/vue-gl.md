---
project: vue-gl
stars: 682
description: Vue.js components rendering 3D WebGL graphics reactively with three.js
url: https://github.com/vue-gl/vue-gl
---

VueGL
=====

Vue.js components rendering 3D WebGL graphics reactively with three.js.

  

Usage
-----

<!-- Load scripts -->
<script src\="https://unpkg.com/vue"\></script\>
<script src\="https://unpkg.com/three"\></script\>
<script src\="https://unpkg.com/vue-gl"\></script\>

<!-- Define canvas and objects -->
<vgl-renderer id\="my-canvas"\>
  <template #scene\>
    <vgl-scene\>
      <vgl-mesh\>
        <template #geometry\>
          <vgl-sphere-geometry\></vgl-sphere-geometry\>
        </template\>
        <template #material\>
          <vgl-mesh-basic-material\></vgl-mesh-basic-material\>
        </template\>
      </vgl-mesh\>
    </vgl-scene\>
  </template\>
  <template #camera\>
    <vgl-perspective-camera position\="spherical" :position-radius\="5"\></vgl-perspective-camera\>
  </template\>
</vgl-renderer\>

<!-- Register components and start vue -->
<script\>
  new Vue({ el: "#my-canvas", components: VueGL });
</script\>

See the documentation for more information.

Available components
--------------------

Components reference shows a list of available core components. Example components reference also introduces additional components you can use immediately.

The list of components not implemented yet can be found at this project.

Contribution
------------

Are you interested in enhance this product? We're really glad and thanks a lot!  
See Contributing guidelines to get started.

### Code Contributors

This project exists thanks to all the people who contribute. \[Contribute\].

### Financial Contributors

Become a financial contributor and help us sustain our community. \[Contribute\]

#### Individuals

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website. \[Contribute\]

License
-------
