---
project: Luckyexcel
stars: 468
description: Luckysheet import export library
url: https://github.com/dream-num/Luckyexcel
---

English| 简体中文

Introduction
------------

Luckyexcel is an excel import and export library adapted to Luckysheet. It only supports .xlsx format files (not .xls).

Demo
----

Demo

Features
--------

Support excel file import to Luckysheet adaptation list

-   Cell style
-   Cell border
-   Cell format, such as number format, date, percentage, etc.
-   Formula

### Plan

The goal is to support all features supported by Luckysheet

-   Conditional Formatting
-   Pivot table
-   Chart
-   Sort
-   Filter
-   Annotation
-   Excel export

Usage
-----

### CDN

<script src\="https://cdn.jsdelivr.net/npm/luckyexcel/dist/luckyexcel.umd.js"\></script\>
<script\>
    // Make sure to get the xlsx file first, and then use the global method window.LuckyExcel to convert
    LuckyExcel.transformExcelToLucky(
        file, 
        function(exportJson, luckysheetfile){
            // After obtaining the converted table data, use luckysheet to initialize or update the existing luckysheet workbook
            // Note: Luckysheet needs to introduce a dependency package and initialize the table container before it can be used
            luckysheet.create({
                container: 'luckysheet', // luckysheet is the container id
                data:exportJson.sheets,
                title:exportJson.info.name,
                userInfo:exportJson.info.name.creator
            });
        },
        function(err){
            logger.error('Import failed. Is your fail a valid xlsx?');
        });
</script\>

> Case Demo index.html shows the detailed usage

### ES and Node.js

#### Installation

npm install luckyexcel

#### ES import

import LuckyExcel from 'luckyexcel'

// After getting the xlsx file
LuckyExcel.transformExcelToLucky(data, 
    function(exportJson, luckysheetfile){
        // Get the worksheet data after conversion
    },
    function(error){
        // handle error if any thrown
    }
)

> Case luckysheet-vue

#### Node.js import

var fs \= require("fs");
var LuckyExcel \= require('luckyexcel');

// Read an xlsx file
fs.readFile("House cleaning checklist.xlsx", function(err, data) {
    if (err) throw err;

    LuckyExcel.transformExcelToLucky(data, function(exportJson, luckysheetfile){
        // Get the worksheet data after conversion
    });
    
});

> Case Luckyexcel-node

Development
-----------

### Requirements

Node.js Version >= 6

### Installation

```
npm install -g gulp-cli
npm install
```

### Development

```
npm run dev
```

### Package

```
npm run build
```

A third-party plug-in is used in the project: JSZip, thanks!

Communication
-------------

-   Any questions or suggestions are welcome to submit Issues
    
-   Gitter
    

Chinese community

Authors and acknowledgment
--------------------------

-   @wbfsa
-   @wpxp123456
-   @Dushusir
-   @xxxDeveloper

License
-------

MIT

Copyright (c) 2020-present, mengshukeji
