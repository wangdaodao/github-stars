---
project: typeflow-editor
stars: 103
description: vue + mxGraph to build the draw tool for Typeflow
url: https://github.com/yvettemuki/typeflow-editor
---

typeflow-editor
===============

#### build with the vue and mxGraph

#### backend resource: https://github.com/yvettemuki/editor-service

Introduction
------------

###### ATTENTION: LATEST VERSION MAY NOT AS TOTALLY SAME AS THE BELOW INTRO DISPLAYED

### Core appearance

### Left side is the element bar including different types of draggable resources, and also including the graph page setting bar of its size

### To add custom element, click the "+" icon in specific element bar and input the new type name to create new one

### To set the specific element type group, click the "gear" icon to open the element type setting panel

### After drag one of the elements in three types of Definition(PureFunction/InputEndpoint/OutputEndpoint), the form will display to fill

##### You should select the variable type in the type selector and input the variable value

##### If you create the Array type, you need to choose the Array type in second type selector

##### If you create Object type, you need to click "Object" option and you will get into the create panel

###### note: all the array type and object type you create will be saved in default (Type Setting function will soon be available)

### After fill some Definition creating forms, you can connect them in the rule:

###### only the same name output of one Definition instance can connect to another Definition instance's input with the same name

### After finish dragging elements, filling their forms and connecting them, you will get the typeflow model

### To check or update the created elements you can _double click_ the Definition vertex (InputEndpoint, OutputEndpoint, PureFunction)

### To _undo_, _redo_, _delete_, _zoom_(in/out), you can click the right-side float toolbar

### To _import model_, _export model_, _generate code_ and _save model_, you can click the buttons on the top side

###### export can choose 3 types: png, svg and xml

### When import, you can choose import _from local_ or _from database_

### When from _database_, and you can delete model when click the "delete" button on the right top side of each item

### To check some model information

### When you click the "?" icon, you can get the guidance about how to use typeflow editor

About vue-cli installation
--------------------------

###### This project use vue-cli3, please make sure you have installed vue-cli3 and update node version to at least 8.9

###### More details about installation, go to https://cli.vuejs.org/zh/guide/installation.html

Project setup
-------------

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

Attention:
----------

Default port is 8080, if you need see vue-cli3 document to change the default port

When you change the backend server address(port), you need to change the proxy in vue.config.js file
