---
project: javascript-risingstars
stars: 1083
description: :stars: An overview of the JavaScript landscape in 2024: trends about frontend, Node.js, fullstack frameworks, build tools, testing, Vue.js, React, state management...
url: https://github.com/bestofjs/javascript-risingstars
---

JavaScript Rising Stars
=======================

An overview of the JavaScript landscape in 2024: trends about frontend, backend and fullstack frameworks, React and Vue.js ecosystems, build tools, AI tools, testing, state management...

Contributors
------------

-   Alexey Pyltsyn
-   Benjamin Blackwood
-   Frank Xu
-   Evan Trujillo
-   Jack Huan
-   Javier Valencia
-   Jusang Kim
-   Hamid Dinar
-   L1lith
-   Michael Rambeau
-   Mihai Badescu
-   Misol Goh
-   Nobuhiro Uchiyama
-   Oh TaeJun
-   Rana Kualu
-   Sacha Grief
-   Sebastien Lorber
-   Seognil LC
-   Shigeto Yatani
-   王仕军
-   Yohei Ice

Special thanks:

-   The content of 2021 and 2022 editions of the Rising Stars was double checked by L1lith.
-   Benjamin Blackwood was the co-author of the 2020 edition.
-   Sacha Grief did a lot of work about the design and the content of the first editions (2016, 2017, 2018, 2019).

Stack
-----

-   Built with Astro
-   Hosted on Vercel
-   Domain provided by js.org

How to contribute?
------------------

Requirements: PNPM, Node.js 20+

-   Clone the repo
-   Install the dependencies: `pnpm install`
-   Start the development server: `pnpm run dev`
-   Check the following URL: `http://localhost:4321/`
-   Update the comments in your language (see below)

Translations
------------

There are 2 types of file to translate:

-   markdown content inside the `src/content/comments` folder, used for comments related to each category: `introduction.md`, `react.md`...
-   key/values messages stored as JSON in the `src/content/messages` folder, used for simple strings used in the UI: `en.json`, `ja.json`...

File system overview:

```
./src/content
├── categories
├── comments
│   └── 2024
│       ├── en
│       │   ├── categories
│       │   └── guests
│       ├── es
│       │   ├── categories
│       │   └── guests
│       └── zh
│           ├── categories
│           └── guests
├── contributors
└── messages
    ├── 2024
    └── common
```
