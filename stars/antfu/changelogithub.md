---
project: changelogithub
stars: 860
description: Generate changelog for GitHub
url: https://github.com/antfu/changelogithub
---

changelogithub
==============

Generate changelog for GitHub releases from Conventional Commits, powered by changelogen.

👉 Changelog example

Features
--------

-   Support exclamation mark as breaking change, e.g. `chore!: drop node v10`
-   Grouped scope in changelog
-   Create the release note, or update the existing one
-   List contributors

Usage
-----

In GitHub Actions:

# .github/workflows/release.yml

name: Release

permissions:
  contents: write

on:
  push:
    tags:
      - 'v\*'

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - name: Set node
        uses: actions/setup-node@v4
        with:
          registry-url: https://registry.npmjs.org/
          node-version: lts/\*

      - run: npx changelogithub # or changelogithub@0.12 to ensure a stable result
        env:
          GITHUB\_TOKEN: ${{secrets.GITHUB\_TOKEN}}

It will be trigged whenever you push a tag to GitHub that starts with `v`.

Configuration
-------------

You can put a configuration file in the project root, named as `changelogithub.config.{json,ts,js,mjs,cjs}`, `.changelogithubrc` or use the `changelogithub` field in `package.json`.

Preview Locally
---------------

npx changelogithub --dry

Why?
----

I used to use `conventional-github-releaser` for almost all my projects. Until I found that it does NOT support using exclamation marks for breaking changes - hiding those important breaking changes in the changelog without the awareness from maintainers.

License
-------

MIT License © 2022 Anthony Fu
