---
project: github-contributions-chart
stars: 5424
description: :octocat: Generate an image of all your Github contributions
url: https://github.com/sallar/github-contributions-chart
---

GitHub Contribution Chart Generator
===================================

Generates an image of all your **GitHub** contributions since you have signed up, so you can use it in social media.

The API for this project lives in the `src/pages/api` directory since GitHub doesn't provide a way to access user statistics through it's official API.

The drawing mechanism lives in the sallar/github-contributions-canvas repository.

Requirements
------------

-   A valid github account.
-   Open activity in setting (`Settings` > `Public profile` > `Contributions & Activity`).
    -   Make profile private and hide activity

Install
-------

Install the packages using NPM:

```
$ npm install
```

How to run
----------

Running locally:

```
$ npm run dev
```

Deployment
----------

This project is deployed on Vercel.

Adding themes
-------------

Add your theme to sallar/github-contribution-canvas repo and also send a PR here to add the name of the theme to the list.

Example
-------

Contributing
------------

Please read CONTRIBUTING.md for details on our code of conduct, and the process for submitting pull requests to us.

Changelog
---------

Every release, along with the migration instructions, is documented on the GitHub Releases page.

License
-------

MIT license
