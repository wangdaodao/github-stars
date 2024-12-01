---
project: vuex-iframe-sync
stars: 104
description: Vuex state synchronization between iframe/window
url: https://github.com/L-Chris/vuex-iframe-sync
---

vuex-iframe-sync
================

English | 中文

Vuex **state synchronization** _between_ **iframe/window**

_Your star is the greatest encouragement to me._

✨ Features:
-----------

-   support iframes/window sync
-   initialization sync when iframe loaded
-   configure the sync behavior for your specific needs

🔧 Requirements
---------------

-   Vue.js (v2.0.0+)
-   Vuex (v2.1.0+)

**Note** window.postMessage has limition on message, works like JSON.parse() and JSON.stringfy().If you have trouble with it, configure a convert function in broadcast and transfer API.

-   MDN window.postMessage
-   MDN Structured\_clone\_algorithm

🔧 Installation
---------------

### CDN

<script src="https://cdn.jsdelivr.net/npm/vuex-iframe-sync/dist/vuex-iframe-sync.umd.js"\></script\>

### NPM

npm install vuex-iframe-sync --save

### YARN

yarn add vuex-iframe-sync

📦 Examples
-----------

-   live example
-   with webpack
-   simple

📦 Usage
--------

// in parent's component with iframe
<iframe id\="frameId1"/\>
<iframe id\="frameId2"/\>

// in parent's store.js
import {broadcast} from 'vuex-iframe-sync'

export default new Vuex.store({
  // ...
  plugins: \[
    broadcast('frameId1,frameId2')
  \]
})

// in iframe's store.js
import {transfer} from 'vuex-iframe-sync'

export default new Vuex.store({
  // same state and mutations with parent
  plugins: \[
    transfer()
  \]
})

🔧 API
------

### broadcast(ids: String, \[options\])

Send state changes payload to iframes through postMessage API while parent state change.

`ids <String|Array>`: frameIds split by ',' or \[{id: iframeId, origin: iframeOrigin}...\]

`options` : The following options can be provided to configure the parent behavior for your specific needs:

-   `convert <Function(payload)>`: convert payload before pass to iframes.

### transfer(\[options\])

Receive state changes from parent. Send state changes to parent while self state change.

`options` : The following options can be provided to configure the iframe behavior for your specific needs:

-   `convert <Function(payload)>`: convert payload before pass to parent.
-   `created <Function(id, store, send)>`: call after iframe created. id: iframeId、store: this.store、send<Function(type, payload)>：parent.$store.commit
-   `destroyed <Function(id, store, send)>`: call after iframe destroyed. id: iframeId、store: this.store、send<Function(type, payload)>：parent.$store.commit

Build Setup
-----------

# serve with with-webpack example at localhost:8080
npm run dev

# serve with simple example at localhost:8080
npm run dev:simple

# test with jest
npm run test

# build for production with minification
npm run build

# build for production with live example
npm run build:docs

🛣 Pending
----------

-   Need your advice

🥂 License
----------

MIT
