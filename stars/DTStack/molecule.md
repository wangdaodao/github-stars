---
project: molecule
stars: 912
description: :rocket: A lightweight Web IDE UI framework.
url: https://github.com/DTStack/molecule
---

Molecule
========

### A lightweight Web IDE UI Framework

中文 | English | 한국어

The **Molecule** is a lightweight **Web IDE UI** framework which is built with React.js and inspired by the VSCode. We have designed the Extension APIs similar to the VSCode, to help developers extend the Workbench in an easier way. It's convenient to integrate the Molecule with React.js applications. It has been applied to many products in DTStack

Online Preview

Features
--------

-   Built-in the Visual Studio Code **Workbench** UI
-   Compatible with the Visual Studio Code **ColorTheme**
-   Customize the Workbench via **React Component** easily
-   Built-in Monaco-Editor **Command Palette, Keybinding** features
-   Support the **i18n**, built-in Simplified Chinese, Korean and English
-   Built-in **Settings**, support to edit and extend via the Extension
-   Built-in basic **Explorer, Search** components, and support extending via the Extension
-   **Typescript** Ready

Installation
------------

npm install @dtinsight/molecule
# Or
yarn add @dtinsight/molecule

Basic Usage
-----------

import React from 'react';
import ReactDOM from 'react-dom';
import { create, Workbench } from '@dtinsight/molecule';
import '@dtinsight/molecule/esm/style/mo.css';

const moInstance \= create({
    extensions: \[\],
});

const App \= () \=> moInstance.render(<Workbench />);

ReactDOM.render(<App />, document.getElementById('root'));

The `extension` is the Extension applications entry, more details about Extension, please read the Quick Start.

Document
--------

-   Introduction
-   Quick Start
-   API
-   Extend Workbench
-   Examples

Development
-----------

git clone git@github.com:DTStack/molecule.git

Clone the source code into your local

**Development Mode**

yarn # Install dependencies

yarn dev # Start dev mode

The Molecule using the **Storybook** to manage and develop the React components, the default visiting address is `http://localhost:6006/`.

**Test**

yarn test -u

**Build & Preview**

yarn build # Compile to ESM
yarn web # Web Preview Mode

We compile the source code into the ES6 modules and output to the **`esm`** folder. Besides the Storybook development mode, there also builtin a **Web Preview** mode using the ESM modules.

Contributing
------------

Refer to the CONTRIBUTING.

Communication
-------------

-   We use DingTalk to communicate,You can search the group number `30537511` or scan the QR code below to join the communication group

License
-------

Copyright © DTStack. All rights reserved.

Licensed under the MIT license.
