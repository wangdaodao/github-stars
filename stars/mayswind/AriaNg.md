---
project: AriaNg
stars: 12104
description: AriaNg, a modern web frontend making aria2 easier to use.
url: https://github.com/mayswind/AriaNg
---

AriaNg
======

Introduction
------------

AriaNg is a modern web frontend making aria2 easier to use. AriaNg is written in pure html & javascript, thus it does not need any compilers or runtime environment. You can just put AriaNg in your web server and open it in your browser. AriaNg uses responsive layout, and supports any desktop or mobile devices.

Features
--------

1.  Pure Html & Javascript, no runtime required
2.  Responsive design, supporting desktop and mobile devices
3.  User-friendly interface
    -   Sort tasks (by name, size, progress, remaining time, download speed, etc.), files, bittorrent peers
    -   Search tasks
    -   Retry tasks
    -   Adjust task order by dragging
    -   More information of tasks (health percentage, client information of bt peers, etc.)
    -   Filter files by specified file types (videos, audios, pictures, documents, applications, archives, etc.) or file extensions
    -   Tree view for multi-directory task
    -   Download / upload speed chart for aria2 or single task
    -   Full support for aria2 settings
4.  Dark theme
5.  Url command line api support
6.  Download finished notification
7.  Multi-languages support
    -   Czech
    -   English
    -   Spanish
    -   French
    -   Italian
    -   Polish
    -   Russian
    -   Chinese (Simplified Chinese / Traditional Chinese)
8.  Multi aria2 RPC host support
9.  Exporting and Importing settings support
10.  Less bandwidth usage, only requesting incremental data

Screenshots
-----------

#### Desktop

#### Mobile Device

Installation
------------

AriaNg now provides three versions, standard version, all-in-one version and AriaNg Native. Standard version is suitable for deployment in the web server, and provides on-demand loading. All-In-One version is suitable for local using, and you can download it and just open the only html file in browser. AriaNg Native is also suitable for local using, and is no need for browser.

#### Prebuilt release

Latest Release: https://github.com/mayswind/AriaNg/releases

Latest Daily Build (Standard Version): https://github.com/mayswind/AriaNg-DailyBuild/archive/master.zip

#### Building from source

Make sure you have Node.js, NPM and Gulp installed. Then download the source code, and follow these steps.

##### Standard Version

```
$ npm install
$ gulp clean build
```

##### All-In-One Version

```
$ npm install
$ gulp clean build-bundle
```

The builds will be placed in the dist directory.

#### Usage Notes

Since AriaNg standard version loads language resources asynchronously, you may not open index.html directly on the local file system to run AriaNg. It is recommended that you can use the all-in-one version or deploy AriaNg in a web container or download AriaNg Native that does not require a browser to run.

Translating
-----------

Everyone is welcome to contribute translations. All translations files are put in `/src/langs/`. You can just modify and commit a new pull request.

If you want to translate AriaNg to a new language, you can add language configuration to `/src/scripts/config/languages.js`, then copy `/i18n/en.sample.txt` to `/src/langs/` and rename it to the language code to be translated, then you can start the translation work.

Documents
---------

1.  English
2.  Simplified Chinese (简体中文)

Demo
----

Please visit http://ariang.mayswind.net/latest

Third Party Extensions
----------------------

There are some third-party applications based on AriaNg, so you can use AriaNg in more scenarios or devices. Please visit Third Party Extensions for more information.

License
-------

MIT
