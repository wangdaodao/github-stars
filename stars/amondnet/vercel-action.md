---
project: vercel-action
stars: 712
description: This action make a deployment with github actions instead of Vercel builder.
url: https://github.com/amondnet/vercel-action
---

Vercel Action
=============

This action was formerly Zeit Now Deployment. Migration Guide

Introduction to Vercel
----------------------

Vercel is a cloud platform for **static sites** and **Serverless Functions** that fits perfectly with your workflow. It enables developers to host **Jamstack** websites and web services that **deploy instantly**, **scale automatically**, and requires **no supervision**, all with **no configuration**.

This action make a Vercel deployment with github actions.

-   Deploy to Vercel.
-   Comment on pull request.
-   Comment on commit.
-   Password Protect ( Basic Auth )
-   Alias domain to deployment.
-   Create Deployment on github.

Result
------

pull request example

commit

Inputs
------

Name

Required

Default

Description

vercel-token

Vercel token. see https://vercel.com/account/tokens

github-comment

true

Its type can be either **string or boolean**. When string, it leaves PR a comment with the string. When boolean, it leaves PR a default comment(true) or does not leave a comment at all(false).

github-token

if you want to comment on pull request or commit. `${{ secrets.GITHUB_TOKEN }}` (GitHub token docs)

vercel-project-id

❗Vercel CLI 17+,The `name` property in vercel.json is deprecated (https://zeit.ink/5F)

vercel-org-id

❗Vercel CLI 17+,The `name` property in vercel.json is deprecated (https://zeit.ink/5F)

vercel-args

This is optional args for `vercel` cli. Example: `--prod`

working-directory

the working directory

scope

If you are working in a team scope, you should set this value to your `team ID`.

alias-domains

You can assign a domain to this deployment. Please note that this domain must have been configured in the project. You can use pull request number via `{{PR_NUMBER}}` and branch via `{{BRANCH}}`.

vercel-project-name

The name of the project; if absent we'll use the `vercel inspect` command to determine. #27 & #28

vercel-version

vercel-cli package version if absent we will use one declared in package.json

Outputs
-------

### `preview-url`

The url of deployment preview.

### `preview-name`

The name of deployment name.

How To Use
----------

### Disable Vercel for GitHub

> The Vercel for GitHub integration automatically deploys your GitHub projects with Vercel, providing Preview Deployment URLs, and automatic Custom Domain updates. link

We would like to to use `github actions` for build and deploy instead of `Vercel`.

Set `github.enabled: false` in `vercel.json`, see example `vercel.json` file below:

{
  "version": 2,
  "public": false,
  "github": {
    "enabled": false
  }
}

When `github.enabled` set to `false`, `Vercel for GitHub` will not deploy the given project regardless of the GitHub app being installed.

### Skip vercel's build step

Since we do the `build` in `github actions`, we don't need to build in `vercel`.

#### Method 1 - via vercel interface

-   Specify "Other" as the framework preset, and
-   Enable the Override option for the Build Command, and
-   Leave the Build Command **empty**.
-   This will prevent the build from being attempted and serve your content as-is.

See docs for more details

#### Method 2 - via `vercel.json`

If a Deployment defines the builds configuration property, the vercel's `Build & Development Settings` are ignored.

{
  "builds": \[
    { "src": "{{Source for distribution}}", "use": "@vercel/static" }
  \]
}

Set `builds` to `@vercel/static` to skip vercel's build step. `src` is the path to the directory containing the files to be deployed.

See docs for more details

### Project Linking

You should link a project via Vercel CLI in locally.

When running `vercel` in a directory for the first time, Vercel CLI needs to know which scope and Project you want to deploy your directory to. You can choose to either link an existing project or to create a new one.

> NOTE: Project linking requires at least version 17 of Vercel CLI. If you have an earlier version, please update to the latest version.

vercel

? Set up and deploy “~/web/my-lovely-project”? \[Y/n\] y
? Which scope do you want to deploy to? My Awesome Team
? Link to existing project? \[y/N\] y
? What’s the name of your existing project? my-lovely-project
🔗 Linked to awesome-team/my-lovely-project (created .vercel and added it to .gitignore)

Once set up, a new `.vercel` directory will be added to your directory. The `.vercel` directory contains both the organization(`vercel-org-id`) and project(`vercel-project-id`) id of your project.

{ "orgId": "example\_org\_id", "projectId": "example\_project\_id" }

You can save both values in the secrets setting in your repository. Read the Official documentation if you want further info on how secrets work on Github.

### Github Actions

-   This is a complete `.github/workflows/deploy.yml` example.

Set the `vercel-project-id` and `vercel-org-id` you found above.

name: deploy website
on: \[pull\_request\]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      #  your build commands
      # - run: |
      #    ng build --prod
      - uses: amondnet/vercel-action@v25 # deploy
        with:
          vercel-token: ${{ secrets.VERCEL\_TOKEN }} # Required
          github-token: ${{ secrets.GITHUB\_TOKEN }} # Optional
          vercel-args: \--prod # Optional
          vercel-org-id: ${{ secrets.ORG\_ID}} # Required
          vercel-project-id: ${{ secrets.PROJECT\_ID}} # Required
          working-directory: ./sub-directory

### Angular Example

See .github/workflows/example-angular.yml ,

### Basic Auth Example

How to add Basic Authentication to a Vercel deployment

See .github/workflows/example-express-basic-auth.yml

source code

| `@now/node-server` is deprecated and stopped working. Use `@vercel/node` instead. #61

### Alias Domains

You can assign a domain to this deployment. Please note that this domain must have been configured in the project.

If you want to assign domain to branch or pr, you should add Wildcard Domain.

You can use pull request number via `{{PR_NUMBER}}` and branch via `{{BRANCH}}`

#### Example

Wildcard Domains : \*.angular.vercel-action.amond.dev

_Per Pull Request_

https://pr-{{PR\_NUMBER}}.angular.vercel-action.amond.dev

-   PR-1 -> https://pr-1.angular.vercel-action.amond.dev
-   PR-2 -> https://pr-2.angular.vercel-action.amond.dev

_Per Branch_

https://{{BRANCH}}.angular.vercel-action.amond.dev

-   develop -> https://develop.angular.vercel-action.amond.dev
-   master -> https://master.angular.vercel-action.amond.dev
-   master -> https://master.angular.vercel-action.amond.dev

See .github/workflows/example-angular.yml

name: deploy website
on: \[pull\_request\]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: amondnet/vercel-action@v25
        with:
          vercel-token: ${{ secrets.VERCEL\_TOKEN }} # Required
          github-token: ${{ secrets.GITHUB\_TOKEN }} # Optional
          vercel-args: \--prod # Optional
          vercel-org-id: ${{ secrets.ORG\_ID}} # Required
          vercel-project-id: ${{ secrets.PROJECT\_ID}} # Required
          working-directory: ./sub-directory # Your Working Directory, Optional
          alias-domains: | # Optional
            staging.angular.vercel-action.amond.dev
            pr-{{PR\_NUMBER}}.angular.vercel-action.amond.dev

Migration from v2
-----------------

1.  Change action name in `workflows` from `now-deployment` to `vercel-action`
    
    \- name: Vercel Action
      uses: amondnet/vercel-action@v25
    
2.  Change input values.
    -   `zeit-token` -> `vercel-token`
    -   `now-org-id` -> `vercel-org-id`
    -   `now-project-id` -> `vercel-project-id`
