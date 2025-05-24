---
project: am-editor
stars: 972
description: A rich text editor that supports collaborative editing and allows for the free use of front-end common libraries such as React and Vue to extend and define plugins.
url: https://github.com/red-axe/am-editor
---

> Here, we have a new rich text editor called Editable, which does not use the native editable property contenteditable, but instead uses a custom renderer. This approach allows us to better control the behavior of the editor.

am-editor
=========

A rich text editor that supports collaborative editing, you can freely use React, Vue and other front-end common libraries to extend and define plugins.

**Preview** · **Document** · **Plugins**

**`Vue2`**

**`Vue3`**

**`React`**

**`Vue2 Demo`**

**`Vue2 Nuxt Demo`**

Features
--------

-   🎁 Out-of-the-box solution with dozens of rich plugins to meet most needs
-   🚀 Highly extensible, in addition to basic plugins for mark, inline, and block types, we also provide card components combined with front-end libraries like React and Vue to render plugin UI
-   🎨 Rich multimedia support, not only supports images and audio/video, but also supports embedding multimedia content
-   📝 Supports Markdown syntax
-   🌍 Supports internationalization
-   💻 Engine written purely in JavaScript, without relying on any front-end libraries, plugins can be rendered using front-end libraries like React and Vue. Can easily handle complex architecture
-   👥 Built-in collaborative editing solution, lightweight configuration to use
-   📱 Compatible with most latest mobile browsers

Plugins
-------

**Package**

**Version**

**Size**

**description**

`@aomao/toolbar`

Toolbar, suitable for `React`

`@aomao/toolbar-vue`

Toolbar, suitable for `Vue3`

`am-editor-toolbar-vue2`

Toolbar, suitable for `Vue2`

`@aomao/plugin-alignment`

Alignment

`@aomao/plugin-embed`

Embed URL

`@aomao/plugin-backcolor`

Background color

`@aomao/plugin-bold`

Bold

`@aomao/plugin-code`

Inline code

`@aomao/plugin-codeblock`

CodeBlock, suitable for `React`

`@aomao/plugin-codeblock-vue`

CodeBlock, suitable for `Vue3`

`am-editor-codeblock-vue2`

CodeBlock, suitable for `Vue2`

`@aomao/plugin-fontcolor`

Font color

`@aomao/plugin-fontfamily`

Font Family

`@aomao/plugin-fontsize`

Font Size

`@aomao/plugin-heading`

Heading

`@aomao/plugin-hr`

Horizontal rule

`@aomao/plugin-indent`

Indentation

`@aomao/plugin-italic`

Italic

`@aomao/plugin-link`

Link, suitable for `React`

`@aomao/plugin-link-vue`

Link, suitable for `Vue3`

`am-editor-link-vue2`

Link, suitable for `Vue2`

`@aomao/plugin-line-height`

Line height

`@aomao/plugin-mark`

Mark

`@aomao/plugin-mention`

Mention

`@aomao/plugin-orderedlist`

Ordered list

`@aomao/plugin-paintformat`

Format painter

`@aomao/plugin-quote`

Blockquote

`@aomao/plugin-redo`

Redo

`@aomao/plugin-removeformat`

Remove format

`@aomao/plugin-selectall`

Select all

`@aomao/plugin-status`

Status

`@aomao/plugin-strikethrough`

Strikethrough

`@aomao/plugin-sub`

Sub

`@aomao/plugin-sup`

Sup

`@aomao/plugin-tasklist`

Task list

`@aomao/plugin-underline`

Underline

`@aomao/plugin-undo`

Undo

`@aomao/plugin-unorderedlist`

Unordered list

`@aomao/plugin-image`

Image

`@aomao/plugin-table`

Table

`@aomao/plugin-file`

File

`@aomao/plugin-mark-range`

Mark range

`@aomao/plugin-math`

Mathematical formula

`@aomao/plugin-video`

Video

Getting Started
---------------

### Installation

The editor consists of the `engine`, `toolbar`, and `plugins`. The `engine` provides us with the core editing capability.

Use `npm` or `yarn` to install the engine package.

$ npm install @aomao/engine
# or
$ yarn add @aomao/engine

### Usage

We'll start by outputting a "Hello world!" message as usual.

import React, { useEffect, useRef, useState } from 'react';
import Engine, { EngineInterface } from '@aomao/engine';

const EngineDemo \= () \=> {
	//Editor container
	const ref \= useRef<HTMLDivElement | null\>(null);
	//Engine instance
	const \[engine, setEngine\] \= useState<EngineInterface\>();
	//Editor content
	const \[content, setContent\] \= useState<string\>('<p>Hello world!</p>');

	useEffect(() \=> {
		if (!ref.current) return;
		//Instantiate the engine
		const engine \= new Engine(ref.current);
		//Set the editor value
		engine.setValue(content);
		//Listen to the editor value change event
		engine.on('change', () \=> {
			const value \= engine.getValue();
			setContent(value);
			console.log(\`value:${value}\`);
		});
		//Set the engine instance
		setEngine(engine);
	}, \[\]);

	return <div ref\={ref} />;
};
export default EngineDemo;

### Plugins

Import the `@aomao/plugin-bold` bold plugin.

import Bold from '@aomao/plugin-bold';

Add the `Bold` plugin to the engine.

//Instantiate the engine
const engine \= new Engine(ref.current, {
	plugins: \[Bold\],
});

### Card

A card is a separately defined area in the editor, with its UI and logic for rendering custom content inside the card using `React`, `Vue`, or other front-end libraries before being mounted onto the editor.

Introduce `@aomao/plugin-codeblock`, a code block plugin with a language drop-down that is rendered using React, which distinguishes it from Vue3 using `@aomao/plugin-codeblock-vue`.

import CodeBlock, { CodeBlockComponent } from '@aomao/plugin-codeblock';

Add the `CodeBlock` plugin and the `CodeBlockComponent` card component to the engine.

//Instantiate the engine
const engine \= new Engine(ref.current, {
	plugins: \[CodeBlock\],
	cards: \[CodeBlockComponent\],
});

The `CodeBlock` plugin supports `markdown` by default. You can trigger it by typing the code block syntax at the beginning of a line in the editor, followed by a space and the language name, such as \`\`\`javascript.

Node Constraints
----------------

To manage nodes more conveniently and reduce complexity, the editor abstracts node properties and functionality and defines four types of nodes: `mark`, `inline`, `block`, and `card`. They are composed of different attributes, styles, or `HTML` structures, and are uniformly constrained using a schema.

A simple `schema` looks like this:

{
  name:'p', // node name
  type:'block' // node type
}

In addition, properties, styles, etc. can also be described, for example:

{
  name:'span', // node name
  type:'mark', // node type
  attributes: {
    // The node has a style attribute
    style: {
      // Must contain a color style
      color: {
        required: true, // must contain
        value:'@color' // The value is a color value that conforms to the css specification. @color is the color validation defined in the editor. Here, methods and regular expressions can also be used to determine whether the required rules are met
      }
    },
    // Optional include a test attribute, its value can be arbitrary, but it is not required
    test:'\*'
  }
}

The following types of nodes conform to the above rules:

<span style\="color:#fff"\></span\>
<span style\="color:#fff" test\="test123" test1\="test1"\></span\>
<span style\="color:#fff;background-color:#000;"\></span\>
<span style\="color:#fff;background-color:#000;" test\="test123"\></span\>

But except that color and test have been defined in `schema`, other attributes (background-color, test1) will be filtered out by the editor during processing.

The nodes in the editable area have four types of combined nodes of `mark`, `inline`, block`, and` card`through the`schema`rule. They are composed of different attributes, styles or`html\` structures. Certain constraints are imposed on nesting.

### Toolbar

Import the `@aomao/toolbar` toolbar. Due to the complex interaction, the toolbar is basically rendered using `React` + `Antd` UI components, while `Vue3` uses `@aomao/toolbar-vue`

Except for UI interaction, most of the work of the toolbar is just to call the engine to execute the corresponding plugin commands after different button events are triggered. In the case of complicated requirements or the need to re-customize the UI, it is easier to modify after the fork.

import Toolbar, { ToolbarPlugin, ToolbarComponent } from '@aomao/toolbar';

Add the `ToolbarPlugin` plugin and `ToolbarComponent` card component to the engine, which allows us to use the shortcut key `/` in the editor to wake up the card toolbar

//Instantiate the engine
const engine \= new Engine(ref.current, {
	plugins: \[ToolbarPlugin\],
	cards: \[ToolbarComponent\],
});

Rendering toolbar, the toolbar has been configured with all plugins, here we only need to pass in the plugin name

return (
    ...
    {
        engine && (
            <Toolbar
                engine\={engine}
                items\={\[
                    \['collapse'\],
                    \[
                        'bold',
                    \],
                \]}
            />
        )
    }
    ...
)

For more complex toolbar configuration, please check the document https://editor.aomao.com/config/toolbar

### Collaborative Editing

This open-source library listens to changes in the `HTML` structure of the editing area (contenteditable root node), uses `MutationObserver` to reverse-engineer the data structure, and connects and interacts with Yjs through `WebSocket` to achieve multi-user collaborative editing.

#### Interactive mode

Each editor, as a client, communicates and interacts with the server through the `WebSocket` function in the `@aomao/plugin-yjs-websocket` plugin.

-   `@aomao/yjs` implements the conversion of editor and `Yjs` data
-   `@aomao/plugin-yjs-websocket` provides the `WebSocket` client function of the editor and `Yjs`
-   `@aomao/plugin-yjs-websocket/server` provides the `WebSocket` server of `Yjs`, written in Node.js, and supports data storage using `MongoDB` and `LevelDB`.

### Project icon

Iconfont

Development
-----------

### React

Before using this open-source library, you need to install dependencies in the project root directory.

```
yarn install

lerna bootstrap
```

After installing the dependencies, you only need to execute the following command in the root directory to start the project:

```
yarn start
```

The development directory structure of this open-source library is as follows:

-   `packages` contains the engine and toolbar-related code
-   `plugins` contains all plugins
-   `api` provides API access required by some plugins, and uses https://editor.aomao.com as the default API service
-   `yjs-server` contains collaborative server code, which can be started by `yarn dev`.

### Vue

am-editor vue example

Contribution
------------

Thanks pleasedmi、Elena211314、zb201307、cheon for donation

### Alipay

### WeChat Pay

### PayPal

https://paypal.me/aomaocom
