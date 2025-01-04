---
project: javascript-risingstars
stars: 1027
description: :stars: An overview of the JavaScript landscape in 2023: trends about frontend, Node.js, fullstack frameworks, build tools, testing, Vue.js, React, state management...
url: https://github.com/bestofjs/javascript-risingstars
---

JavaScript Rising Stars
=======================

An overview of the JavaScript landscape in 2023: trends about frontend, backend and fullstack frameworks, React and Vue.js ecosystems, build tools, testing, state management, GraphQL...

Team members
------------

-   Alexey Pyltsyn
-   Benjamin Blackwood
-   Frank Xu
-   Evan Trujillo
-   Javier Valencia
-   Jusang Kim
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

Requirements: PNPM, Node.js 18+

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
│   └── 2023
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
    ├── 2023
    └── common
```
