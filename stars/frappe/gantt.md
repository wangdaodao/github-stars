---
project: gantt
stars: 4765
description: Open Source Javascript Gantt
url: https://github.com/frappe/gantt
---

Frappe Gantt
------------

A simple, interactive, modern gantt chart library for the web

**View the demo »**

### Install

```
npm install frappe-gantt
```

### Usage

Include it in your HTML:

```
<script src="frappe-gantt.min.js"></script>
<link rel="stylesheet" href="frappe-gantt.css">
```

Or from the CDN:

```
<script src="https://cdn.jsdelivr.net/npm/frappe-gantt/dist/frappe-gantt.umd.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/frappe-gantt/dist/frappe-gantt.css">
```

And start hacking:

var tasks \= \[
  {
    id: 'Task 1',
    name: 'Redesign website',
    start: '2016-12-28',
    end: '2016-12-31',
    progress: 20,
    dependencies: 'Task 2, Task 3',
    custom\_class: 'bar-milestone' // optional
  },
  ...
\]
var gantt \= new Gantt("#gantt", tasks);

You can also pass various options to the Gantt constructor:

var gantt \= new Gantt('#gantt', tasks, {
    header\_height: 50,
    column\_width: 30,
    step: 24,
    view\_modes: \['Quarter Day', 'Half Day', 'Day', 'Week', 'Month'\],
    bar\_height: 20,
    bar\_corner\_radius: 3,
    arrow\_curve: 5,
    padding: 18,
    view\_mode: 'Day',
    date\_format: 'YYYY-MM-DD',
    language: 'en', // or 'es', 'it', 'ru', 'ptBr', 'fr', 'tr', 'zh', 'de', 'hu'
    popup: null,
});

You can add `dark` class to the container element to apply dark theme.

<div class\="gantt-target dark"\></div\>

### Contributing

If you want to contribute enhancements or fixes:

1.  Clone this repo.
2.  `cd` into project directory
3.  `yarn`
4.  `yarn run dev`
5.  Open `index.html` in your browser, make your code changes and test them.

### Publishing

If you have publishing rights (Frappe Team), follow these steps to publish a new version.

Assuming the last commit (or a couple of commits) were enhancements or fixes,

1.  Run `yarn build`
    
    This will generate files in the `dist/` folder. These files need to be committed.
    
2.  Run `yarn publish`
    
3.  Type the new version at the prompt
    
    Depending on the type of change, you can either bump the patch version or the minor version. For e.g.,
    
    ```
    0.5.0 -> 0.6.0 (minor version bump)
    0.5.0 -> 0.5.1 (patch version bump)
    ```
    
4.  Now, there will be a commit named after the version you just entered. Include the generated files in `dist/` folder as part of this commit by running the command:
    
    ```
    git add dist
    git commit --amend
    git push origin master
    ```
    

License: MIT

* * *

Project maintained by frappe
