---
project: sys-shim
stars: 282
description: You can quickly develop desktop applications using simple front-end languages, with a program size of less than 1M.
url: https://github.com/wll8/sys-shim
---

Documentation  |  Examples

  

You can quickly develop desktop applications using simple front-end languages, with a program size of less than 1M.

Features
--------

-   No need to write in any language other than JavaScript; use JavaScript to call system APIs.
-   Super lightweight, less than 1M.
-   Super simple, develop and generate programs without installing complex development environments.
-   System interfaces are ready to use out of the box. For example, read and write local files, execute system commands, run in the background, tray menus, etc.

Contribution
------------

If you want to participate in the development of this project, it's recommended to prepare the following environment:

-   node v18.19.0
-   vscode v1.94.2
-   pnpm v9

Directory structure description:

store/
  bin/ - Source code for binary programs that provide service calls.
  demo/ - Some usage examples.
  doc/ - Source code for project and usage documentation.
  play/ - Playground program.
  sdk/ - Source code for the JavaScript API.

Acknowledgments
---------------

-   LuaRT
