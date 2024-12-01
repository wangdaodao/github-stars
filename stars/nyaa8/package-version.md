---
project: package-version
stars: 16
description: 📦 A GitHub Action to extract package version from package.json to an environment variable
url: https://github.com/nyaa8/package-version
---

📦 package-version
==================

An Action to extract package version from package.json and export it to an environment variable

📖 Docs (kind of)
-----------------

\- uses: nyaa8/package-version@v1
  with:
    path: 'uwu/package.json' # Optional
    follow-symlinks: 'false' # Optional

And then you can use `${{ env.PACKAGE_VERSION }}` 🎉

Thank you for reading this 🙇🏼‍♀️

_Made using heavily modified actions/typescript-action template_
