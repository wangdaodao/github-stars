---
project: snk
stars: 5401
description: 🟩⬜ Generates a snake game from a github user contributions graph and output a screen capture as animated svg or gif
url: https://github.com/Platane/snk
---

snk
===

Generates a snake game from a github user contributions graph

Pull a github user's contribution graph. Make it a snake Game, generate a snake path where the cells get eaten in an orderly fashion.

Generate a gif or svg image. Colors can be customized.

Available as github action. It can automatically generate a new image each day. Which makes for great github profile readme

Usage
-----

### **github action**

\- uses: Platane/snk@v3
  with:
    # github user name to read the contribution graph from (\*\*required\*\*)
    # using action context var \`github.repository\_owner\` or specified user
    github\_user\_name: ${{ github.repository\_owner }}

    # list of files to generate.
    # one file per line. Each output can be customized with options as query string.
    #
    #  supported options:
    #  - palette:           A preset of color, one of \[github, github-dark, github-light\]
    #  - color\_snake:       Color of the snake
    #  - color\_dots:        Coma separated list of dots color.
    #                       The first one is 0 contribution, then it goes from the low contribution to the highest.
    #                       Exactly 5 colors are expected.
    #  - color\_background:  Color of the background (for gif only)
    outputs: |
      dist/github-snake.svg
      dist/github-snake-dark.svg?palette=github-dark
      dist/ocean.gif?color\_snake=orange&color\_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9&color\_background=#aaaaaa

example with cron job

### **svg**

If you are only interested in generating a svg (not a gif), consider using this faster action: `uses: Platane/snk/svg-only@v3`

### **dark mode**

For **dark mode** support on github, use this special syntax in your readme.

<picture\>
  <source media\="(prefers-color-scheme: dark)" srcset\="github-snake-dark.svg" />
  <source media\="(prefers-color-scheme: light)" srcset\="github-snake.svg" />
  <img alt\="github-snake" src\="github-snake.svg" />
</picture\>

### **interactive demo**

platane.github.io/snk

### **local**

```
npm install

npm run dev:demo
```

Implementation
--------------

solver algorithm

Contribution Policy
-------------------

This project does not accept pull request.

Reporting or fixing issues is appreciated, but change in the API or implementation should be discussed in issue first and is likely not going be greenlighted.
