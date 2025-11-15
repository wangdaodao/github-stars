---
project: malinajs
stars: 1153
description: Frontend compiler, inspired by Svelte
url: https://github.com/malinajs/malinajs
---

Malina.js
=========

Malina.js helps you create a fast and thin web application that runs **without a front-end framework**

-   High performance, look at benchmark
-   One of the best in startup metrics
-   Compact bundle size of an app (starts from 185 bytes), TodoMVC example **2.7kb** (gzipped) source code
-   Familiar syntax based of standard HTML, CSS and JavaScript

### Links

-   **Try Malina.js online (REPL)**
-   Documentation
-   Telegram community
-   Syntax Highlighter for VS-Code

### Benchmark

### Startup metrics

### Articles

-   Comparision with Svelte.js
-   Comparision with Vue 3
-   Passing CSS classes to child components
-   Using fragments

Example
-------

<script\>
  let name \= 'world';
    
  function rename() {
    name \= 'user';
  }
</script\>

<h1\>Hello {name.toUpperCase()}!</h1\>
<button @click\={rename}\>Rename</button\>

Quick Start
-----------

You can get started with a simple app by running the following in your terminal:

```
npm create malina myapp
cd myapp
npm run dev
# open http://localhost:7000/
```

License
-------

MIT
