---
project: fullcalendar
stars: 19104
description: Full-sized drag & drop event calendar in JavaScript
url: https://github.com/fullcalendar/fullcalendar
---

FullCalendar
============

Full-sized drag & drop calendar in JavaScript

-   Project Website
-   Documentation
-   Changelog
-   Support
-   License
-   Roadmap

Connectors:

-   React
-   Angular
-   Vue 3 | 2

Bundle
------

The FullCalendar Standard Bundle is easier to install than individual plugins, though filesize will be larger. It works well with a CDN.

Installation
------------

Install the FullCalendar core package and any plugins you plan to use:

npm install @fullcalendar/core @fullcalendar/interaction @fullcalendar/daygrid

Usage
-----

Instantiate a Calendar with plugins and options:

import { Calendar } from '@fullcalendar/core'
import interactionPlugin from '@fullcalendar/interaction'
import dayGridPlugin from '@fullcalendar/daygrid'

const calendarEl \= document.getElementById('calendar')
const calendar \= new Calendar(calendarEl, {
  plugins: \[
    interactionPlugin,
    dayGridPlugin
  \],
  initialView: 'timeGridWeek',
  editable: true,
  events: \[
    { title: 'Meeting', start: new Date() }
  \]
})

calendar.render()

Development
-----------

You must install this repo with PNPM:

```
pnpm install
```

Available scripts (via `pnpm run <script>`):

-   `build` - build production-ready dist files
-   `dev` - build & watch development dist files
-   `test` - test headlessly
-   `test:dev` - test interactively
-   `lint`
-   `clean`

Info about contributing code »
