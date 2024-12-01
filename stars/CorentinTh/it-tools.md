---
project: it-tools
stars: 23262
description: Collection of handy online tools for developers, with great UX. 
url: https://github.com/CorentinTh/it-tools
---

Useful tools for developer and people working in IT. Have a look !.

Functionalities and roadmap
---------------------------

Please check the issues to see if some feature listed to be implemented.

You have an idea of a tool? Submit a feature request!

Self host
---------

Self host solutions for your homelab

**From docker hub:**

docker run -d --name it-tools --restart unless-stopped -p 8080:80 corentinth/it-tools:latest

**From github packages:**

docker run -d --name it-tools --restart unless-stopped -p 8080:80 ghcr.io/corentinth/it-tools:latest

**Other solutions:**

-   Cloudron
-   Tipi
-   Unraid

Contribute
----------

### Recommended IDE Setup

VSCode with the following extensions:

-   Volar (and disable Vetur)
-   TypeScript Vue Plugin (Volar).
-   ESLint
-   i18n Ally

with the following settings:

{
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "i18n-ally.localesPaths": \["locales", "src/tools/\*/locales"\],
  "i18n-ally.keystyle": "nested"
}

### Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need TypeScript Vue Plugin (Volar) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a Take Over Mode that is more performant. You can enable it by the following steps:

1.  Disable the built-in TypeScript Extension
    1.  Run `Extensions: Show Built-in Extensions` from VSCode's command palette
    2.  Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2.  Reload the VSCode window by running `Developer: Reload Window` from the command palette.

### Project Setup

pnpm install

### Compile and Hot-Reload for Development

pnpm dev

### Type-Check, Compile and Minify for Production

pnpm build

### Run Unit Tests with Vitest

pnpm test

### Lint with ESLint

pnpm lint

### Create a new tool

To create a new tool, there is a script that generate the boilerplate of the new tool, simply run:

pnpm run script:create:tool my-tool-name

It will create a directory in `src/tools` with the correct files, and a the import in `src/tools/index.ts`. You will just need to add the imported tool in the proper category and develop the tool.

Contributors
------------

Big thanks to all the people who have already contributed!

Credits
-------

Coded with ❤️ by Corentin Thomasset.

This project is continuously deployed using vercel.com.

Contributor graph is generated using contrib.rocks.

License
-------

This project is under the GNU GPLv3.
