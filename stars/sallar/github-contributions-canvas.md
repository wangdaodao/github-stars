---
project: github-contributions-canvas
stars: 183
description: A tool for drawing a heat-map of Github contributions on HTML Canvas
url: https://github.com/sallar/github-contributions-canvas
---

Github Contributions on Canvas
==============================

A tool for drawing a heat-map of Github contributions on HTML Canvas.

This module is used for drawing user contributions in this project.

Install
-------

$ npm install github-contributions-canvas

Usage
-----

import { drawContributions } from "github-contributions-canvas";

drawContributions(canvasEl, {
  data: contributionData,
  username: "myusername",
  themeName: "standard",
  footerText: "Made by @sallar - github-contributions.now.sh"
});

Available Themes
----------------

The themes are defined in the `src/themes.js` file. Currently the available themes are:

-   `standard`
-   `halloween`
-   `teal`
-   `leftPad`
-   `dracula`
-   `blue`
-   `panda`
-   `sunny`
-   `pink`
-   `YlGnBu`
-   `solarizedDark`
-   `solarizedLight`

Data Format
-----------

This module accepts the output from sallar/github-contributions-api API. Check that project for more info.

License
-------

Sallar Kaboli © MIT License
