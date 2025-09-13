---
project: react-pdf-viewer
stars: 2536
description: A React component to view a PDF document
url: https://github.com/react-pdf-viewer/react-pdf-viewer
---

React PDF viewer
================

A React component to view a PDF document. It's written in TypeScript, and powered by React hooks completely.

// Core viewer
import { Viewer } from '@react-pdf-viewer/core';

// Plugins
import { defaultLayoutPlugin } from '@react-pdf-viewer/default-layout';

// Import styles
import '@react-pdf-viewer/core/lib/styles/index.css';
import '@react-pdf-viewer/default-layout/lib/styles/index.css';

// Create new plugin instance
const defaultLayoutPluginInstance \= defaultLayoutPlugin();

<Viewer
    fileUrl\='/assets/pdf-open-parameters.pdf'
    plugins\={\[
        // Register plugins
        defaultLayoutPluginInstance,
        ...
    \]}
/>

Features
--------

**Basic features**

-   Support password protected document
-   Zooming: Support custom levels such as actual size, page fit, and page width
-   Navigation between pages
-   Can go to the first and last pages quickly
-   Search for text
-   Preview page thumbnails
-   View and navigate the table of contents
-   List and download attachments
-   Rotating
-   Text selection and hand tool modes
-   Different scrolling modes
-   Full screen mode
-   Can open a file from local. Users can drag and drop a local file to view it
-   Download file
-   View the document properties
-   Support SSR
-   Print
-   Theming
-   Dark mode
-   Accessibility

**Customization**

-   The toolbar can be customized easily
-   All text items can be localized in another language

License
-------

You have to purchase a Commercial License at the official website.

About
-----

This project is developed by _Nguyen Huu Phuoc_. I love building products and sharing knowledge.

-   DEV
-   Github
