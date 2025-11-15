---
project: github-contributions-api
stars: 205
description: :octocat: Github contributions API (bootleg)
url: https://github.com/sallar/github-contributions-api
---

⚠️ \[Deprecation Notice\]
-------------------------

This repository is now deprecated and the code lives within it's parent project sallar/github-contributions-chart which uses Next.js and serverless functions to run it.

Github Contributions API
========================

> A simple API that returns number of Github contributions based on a users Github profile. This API is used for generating an image of user contributions in this site

How to run
----------

Install the packages using NPM:

```
$ npm install ./github-contributions-api
```

Or download as ZIP.

Example
-------

Send a request to the API in the following format:

```
https://github-contributions-api.now.sh/v1/GITHUB_USERNAME
```

And you will receive an object with history of that user's contributions:

{
  ...
  "contributions": \[
    {
      "date": "2018-04-30",
      "count": 2,
      "color": "#c6e48b"
    },
    {
      "date": "2018-04-29",
      "count": 29,
      "color": "#239a3b"
    },
    ...
  \]
}

You can return the results as an object keyed by year, month and day by using the `format=nested` query param:

```
https://github-contributions-api.now.sh/v1/GITHUB_USERNAME?format=nested
```

{
  ...
  "contributions": {
     "2018": {
       "4": {
         "29": {
           "date": "2018-04-29",
           "count": 29,
           "color": "#239a3b"
         },
         "30": {
           "date": "2018-04-30",
           "count": 2,
           "color": "#c6e48b"
         }
       },
    },
    ...
  }
}

Contributing
------------

Please read CONTRIBUTING.md for details on our code of conduct, and the process for submitting pull requests to us.

Changelog
---------

Every release, along with the migration instructions, is documented on the Github Releases page.

License
-------

MIT license © Sallar Kaboli
