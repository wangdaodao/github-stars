---
project: x-prober
stars: 1383
description: 🐘 A probe program for PHP environment (一款精美的 PHP 探針, 又名X探針、劉海探針)
url: https://github.com/kmvan/x-prober
---

-   简体中文
-   繁体體中文（中國臺灣）
-   繁体體中文（中國香港）
-   日本語

😎 X Prober, Notch Prober
=========================

> A PHP environment probe program that not only displays server information intuitively.

Open Source License
-------------------

-   GPL-3.0

Online Demo
-----------

-   https://prober.inn-studio.com
-   https://tz.inn-studio.com (Same as above)

Download & Usage
----------------

-   Click INN Download Node or GitHub Node to download the probe file
-   You'll get a single file. Rename it to `x.php` and upload to your server
-   Access via browser: `your-domain/x.php`

Requirements
------------

-   Build Environment: PHP 8.4+
-   Runtime Environment: PHP 5.4+
-   Browser Compatibility: Chrome, Firefox, Edge, Android
-   OS Compatibility: Linux, Windows (basic features)

Extensions
----------

-   In development...

Development Guide
-----------------

1.  Fork the project
2.  Fetch your repository
3.  Install npm modules: `$ npx pnpm i`
4.  Install composer: `$ composer install && composer dumpautoload -o`
5.  Generate multilingual files: `$ npm run lang` to rebuild `./languages/lang.pot` template
6.  Start PHP backend: `$ npx pnpm dev:php`
7.  Start Vite frontend: `$ npx pnpm dev`
8.  Access: `http://localhost:5173/`

Production Build
----------------

-   Build frontend: `$ npx pnpm build`
-   Compile single file: `$ npx pnpm build:php` to get `./dist/prober.php`
-   Access: `http://localhost:8001/prober.php` or `http://path/to/dist/prober.php`

Contribute Translations
-----------------------

1.  Fork the project
2.  Use Poedit with `./languages/lang.pot` to translate
3.  Save translation file (e.g. `en_US.po`) in `./languages`
4.  Push your changes
5.  Submit Pull Request. Much appreciated! 😘

Notes for Contributors
----------------------

-   Your PHP code must be compatible with PHP 5.4+ environments

Contributors
------------

Backers
-------

Thank you to all our backers! 🙏 \[Become a backer\]

Sponsors
--------

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. \[Become a sponsor\]

-   Thanks to VPSPlayer.com - Jan 16, 2021 - ¥199
-   Thanks to 1529\*\*\*576 - Apr 4, 2019 – ¥150
-   Thanks to Vultr.com - Mar 13, 2019 - $50

Planned Features
----------------

-   Temperature detection
-   Multilingual support via Poedit
-   Detailed benchmark results
-   Email sending test
-   Network speed test
-   Additional server benchmarks
-   PING functionality

Keywords
--------

X-Prober/PHP 探针/X 探针/刘海探针
