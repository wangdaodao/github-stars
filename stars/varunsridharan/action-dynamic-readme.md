---
project: action-dynamic-readme
stars: 43
description: ~ Dynamic ReadME Generator ~
url: https://github.com/varunsridharan/action-dynamic-readme
---

Dynamic ReadMe - _**Github Action**_
====================================

Convert Static Readme into Dynamic Readme

Motivation
----------

As an open-source software developer I use GitHub Repositories extensively to store my projects. I maintain over 100 projects, of which, about 85% of them have standardised content for the README.md file. That being said, I am finding it increasingly tedious to add, update or remove content in the README.md files across all my repositories because of two main challenges:

1.  Templating of files: The information which is common to README.md files across all my repositories such as Sponsor, Contribute, Contact, etc., cannot be templated and inserted into the README.md files of all my projects / repositories.
    
2.  Project / Repository-specific information: Github does not provide any repository-specific variables which can be used to dynamically insert repository information into the README.md file. As a result, repository-specific information needs to be hard-coded into the README file.
    

### Solution:

To overcome this limitation, and help developers such as myself automate this tedious task, I have created a GitHub action called “Github Action Dynamic ReadMe”. This action pulls repository-specific variables and also allows for templating of files, thereby easily creating dynamic file content for files such as README.md.

⚙️ Configuration
----------------

Option

Description

Default

`FILES`

list of files that should be compiled.

`false`

`DELIMITER`

you can change the default **DELIMITER** if it causes issue with your data.

`${{ }}`

`GLOBAL_TEMPLATE_REPOSITORY`

you can set a global repository template where all the files are stored.

`false`

`committer_name`

Specify the committer name

`Dynamic Readme`

`committer_email`

Specify the committer email

`githubactionbot+dynamicreadme@gmail.com`

`commit_message`

set a custom commit message

`💬 - File Rebuilt - Github Action Runner : ${GITHUB_RUN_NUMBER}`

`confirm_and_push`

Commit the changes and push directly to repository

`true`

✍️ Syntax
---------

-   Variables : `${{ VARIABLE_NAME }}`
-   Inline File Includes : `<!-- include {filepath} -->`
-   Reusable File Includes :
    -   Start : `<!-- START include {filepath} -->`
    -   END : `<!-- END include {filepath} -->`

### Variables

All Default vairables exposed by github actions runner can be accessed like `$‎{{ GITHUB_ACTIONS }}` OR `$‎{{ GITHUB_ACTOR }}`

**Dynamic Readme Github Action** Uses **Repository Meta - Github Action** which exposes useful metadata as environment variable and those variables can be used as template tags.

any variables exposed by **Repository Meta** can be accessed like below

Repository Owner : ${{ env.REPOSITORY\_OWNER }}
Repository Full Name : ${{ env.REPOSITORY\_FULL\_NAME }}

> ℹ️ **Note :** Any environment variable can be accessed just by using `env.` as prefix `${{ env.VARIABLE_NAME }}`

### File Includes

#### Source Options

-   Relative Path : `template/file.md`
-   Absolute path : `./template/file.md`
-   From Repository : `{owner}/{repository}/{filepath}` OR `{owner}/{repository}@{branch}/{filepath}`

#### Relative Path Syntax

Files are always searched from repository root path

Inline Includes : 
<!-- include template/file.md \-->

Reusable Includes : 
<!-- START template/file.md \-->

<!-- END template/file.md \-->

#### Absolute path Syntax

Files are searched from current repository. This can come in handy when writing nested includesType a message

Inline Includes : 
<!-- include ./template/file.md \-->

Reusable Includes : 
<!-- START ./template/file.md \-->

<!-- END ./template/file.md \-->

#### From Repository Syntax

You can include any type of file from any repository. If you want to include a file from a **Private Repository**, you have to provide **Github Personal Access** Token INSTEAD OF **Github Token** in the action's workflow file.

> ℹ️ If branch is not specified then default branch will be cloned

##### Without Branch

Inline Includes : 
<!-- include octocat/Spoon-Knife/README.md \-->

Reusable Includes : 
<!-- START octocat/Spoon-Knife/README.md \-->

<!-- END octocat/Spoon-Knife/README.md \-->

##### Custom Branch

Inline Includes : 
<!-- include octocat/Spoon-Knife/@master/README.md \-->

Reusable Includes : 
<!-- START octocat/Spoon-Knife/@master/README.md \-->

<!-- END octocat/Spoon-Knife/@master/README.md \-->

#### Builtin Markdown Handlers

blow options can be used with **inline** / **resuable** includes.

-   code - `[code]` OR `[code:{code_type}]` - will print the contents of the file inside a codeblock
-   blockquote - `[blockquote]` - will print the contents of the file inside a blockquote
-   raw - `[raw]` OR `[escape]` - will print the actual contents without rendering it.

##### Example

Inline Includes With Custom Markdown Below file will be included inside HTML blockquote element
<!-- include \[code\] template/thankyou.md \--> 

Inline Includes With Custom Markdown Below file will be included inside HTML blockquote element
<!-- include \[code:json\] template/contents.json \--> 

Reusable Includes Custom Markdown :
<!-- START \[code\] template/file.md \-->
<!-- END \[code\] template/file.md \-->

Reusable Includes Custom Markdown :
<!-- START \[code:json\] template/contents.json \-->
<!-- END \[code:json\] template/contents.json \-->

> ℹ️ **Inline includes** can come in handy when you want to parse the data once and save it. It can also be used inside a nested include.
> 
> ℹ️ Even though **Reusable includes** and **Inline Includes** do the same work, they can come in handy when you are generating a template and saving it in the same file. It preserves the include comment which will be parsed again when re-generating the template, and the contents of the include will be updated accordingly.

### Pull Request Support

This action modifies the files, creates a commit and uploads them directly to the default branch of the repository.

If the default branch of the repository is protected by the rule `Require a pull request before merging` then you will need to set the option `confirm_and_push: false` so that the commit is not made and the changes are not uploaded to the default branch.

\- name: "💫  Dynamic Template Render"
  uses: varunsridharan/action-dynamic-readme@main
  with:
    GLOBAL\_TEMPLATE\_REPOSITORY: {repository-owner}/{repository-name}
    files: |
      FILE.md
      FILE2.md=output\_filename.md
      folder1/file.md=folder2/output.md
    confirm\_and\_push: false # Important if use "Require a pull request before merging" rule
  env:
    GITHUB\_TOKEN: ${{ secrets.GITHUB\_TOKEN }}

In addition to the previous configuration, it is necessary to use other actions to be able to confirm the changes and generate a Pull Request towards the default branch

\- name: "📥  Fetching Repository Contents"
  uses: actions/checkout@main

- name: "💫  Dynamic Template Render"
  uses: varunsridharan/action-dynamic-readme@main
  with:
    GLOBAL\_TEMPLATE\_REPOSITORY: {repository-owner}/{repository-name}
    files: |
      FILE.md
      FILE2.md=output\_filename.md
      folder1/file.md=folder2/output.md
    confirm\_and\_push: false # Important if use "Require a pull request before merging" rule
  env:
    GITHUB\_TOKEN: ${{ secrets.GITHUB\_TOKEN }}

- name: Create pull request
  uses: peter-evans/create-pull-request@v3
  with:
    token: ${{ secrets.GITHUB\_TOKEN }}

Thanks to this configuration, the necessary files can be dynamically generated by adding them to a different branch that then we can merge with the default branch, complying with the rule `Require a pull request before merging`.

Check out the example workflow (Pull Request Support) for a more advanced configuration

* * *

### For live Demo Please Check Demo Repository

* * *

🚀 Example Workflow File
------------------------

name: Dynamic Template

on:
  push:
    branches:
      - main
  workflow\_dispatch:

jobs:
  update\_templates:
    name: "Update Templates"
    runs-on: ubuntu-latest
    steps:
      - name: "📥  Fetching Repository Contents"
        uses: actions/checkout@main

      - name: "💾  Github Repository Metadata"
        uses: varunsridharan/action-repository-meta@main
        env:
          GITHUB\_TOKEN: ${{ secrets.GITHUB\_TOKEN }}

      - name: "💫  Dynamic Template Render"
        uses: varunsridharan/action-dynamic-readme@main
        with:
          GLOBAL\_TEMPLATE\_REPOSITORY: {repository-owner}/{repository-name}
          files: |
            FILE.md
            FILE2.md=output\_filename.md
            folder1/file.md=folder2/output.md
        env:
          GITHUB\_TOKEN: ${{ secrets.GITHUB\_TOKEN }}

🚀 Example Workflow File (Pull Request Support)
-----------------------------------------------

name: Dynamic Template

on:
  push:
    branches:
      - main
  workflow\_dispatch:

jobs:
  update\_templates:
    name: "Update Templates"
    runs-on: ubuntu-latest
    steps:
      - name: "📥  Fetching Repository Contents"
        uses: actions/checkout@main

      - name: "💾  Github Repository Metadata"
        uses: varunsridharan/action-repository-meta@main
        env:
          GITHUB\_TOKEN: ${{ secrets.GITHUB\_TOKEN }}

      - name: "💫  Dynamic Template Render"
        uses: varunsridharan/action-dynamic-readme@main
        with:
          GLOBAL\_TEMPLATE\_REPOSITORY: {repository-owner}/{repository-name}
          files: |
            FILE.md
            FILE2.md=output\_filename.md
            folder1/file.md=folder2/output.md
          committer\_name: github-actions\[bot\]
          committer\_email: github-actions\[bot\]@users.noreply.github.com
          commit\_message: 'docs: update readme file \[skip ci\]'
          confirm\_and\_push: false
        env:
          GITHUB\_TOKEN: ${{ secrets.GITHUB\_TOKEN }}

      - name: Create pull request
        id: cpr
        uses: peter-evans/create-pull-request@v3
        with:
          token: ${{ secrets.GITHUB\_TOKEN }}
          commit-message: 'docs: documentation files updated \[skip ci\]'
          committer: github-actions\[bot\] <github-actions\[bot\]@users.noreply.github.com>
          author: github-actions\[bot\] <github-actions\[bot\]@users.noreply.github.com>
          signoff: false
          branch: github-actions/repository-maintenance
          delete-branch: true
          title: Update documentation files
          body: All documentation files has been updated to last recent version
          labels: |
            skip-changelog
            docs
      - name: Enable pull request automerge
        if: steps.cpr.outputs.pull-request-operation == 'created'
        uses: peter-evans/enable-pull-request-automerge@v1
        with:
          token: ${{ secrets.PAT }}
          pull-request-number: ${{ steps.cpr.outputs.pull-request-number }}

      - name: Auto approve
        if: steps.cpr.outputs.pull-request-operation == 'created'
        uses: juliangruber/approve-pull-request-action@v1
        with:
          github-token: ${{ secrets.PAT }}
          number: ${{ steps.cpr.outputs.pull-request-number }}

* * *

📝 Changelog
------------

All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog, and this project adheres to Semantic Versioning.

Checkout CHANGELOG.md

🤝 Contributing
---------------

If you would like to help, please take a look at the list of issues.

📜 License & Conduct
--------------------

-   **MIT License** © Varun Sridharan
-   Code of Conduct

📣 Feedback
-----------

-   ⭐ This repository if this project helped you! 😉
-   Create An 🔧 Issue if you need help / found a bug

💰 Sponsor
----------

I fell in love with open-source in 2013 and there has been no looking back since! You can read more about me here. If you, or your company, use any of my projects or like what I’m doing, kindly consider backing me. I'm in this for the long run.

-   ☕ How about we get to know each other over coffee? Buy me a cup for just **$9.99**
-   ☕️☕️ How about buying me just 2 cups of coffee each month? You can do that for as little as **$9.99**
-   🔰 We love bettering open-source projects. Support 1-hour of open-source maintenance for **$24.99 one-time?**
-   🚀 Love open-source tools? Me too! How about supporting one hour of open-source development for just **$49.99 one-time ?**

Connect & Say 👋
----------------

-   **Follow** me on 👨‍💻 Github and stay updated on free and open-source software
-   **Follow** me on 🐦 Twitter to get updates on my latest open source projects
-   **Message** me on 📠 Telegram
-   **Follow** my pet on Instagram for some _dog-tastic_ updates!

* * *

_Built With ♥ By Varun Sridharan_  
  

* * *
