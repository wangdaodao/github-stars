---
project: vue-json-edit
stars: 287
description: Visual JSON editor built as an vue component. Provides a basic GUI
url: https://github.com/jinkin1995/vue-json-edit
---

Vue-Json-Edit
=============

> Visual JSON Editor built as an vue component. Provides a basic GUI

  

**DEMO**
--------

  

Getting Started
---------------

```
npm install vue-json-edit --save
```

  

Usage
-----

//import it in your project At your entry point

import Vue from 'vue'
import JsonEditor from 'vue-json-edit'
  
Vue.use(JsonEditor)

### Props

-   objData: json data
-   options
    -   confirmText: strings of the confirm button
    -   cancelText: strings of the cancel button

  

Example
-------

Single file component

<template\>
    <JsonEditor
        :options\="{
            confirmText: 'confirm',
            cancelText: 'cancel',
        }"
        :objData\="jsonData" 
        v-model\="jsonData" \>
    </JsonEditor\>
</template\>
<script\>
export default {
    ...
    data: function() {
        return {
            jsonData: {
                name: 'mike',
                age: 23,
                phone: '18552129932',
                address: \['AAA C1', 'BBB C2'\]
            }
        }
    }
}
</script\> 

  

..
--

Aplipay:  

USDT:
