---
project: sayTheMoney-svelte
stars: 51
description: null
url: https://github.com/sayTheMoney/sayTheMoney-svelte
---

_Looking for a shareable component template? Go here --> sveltejs/component-template_

* * *

svelte app
==========

This is a project template for Svelte apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using degit:

npx degit sveltejs/template svelte-app
cd svelte-app

_Note that you will need to have Node.js installed._

Get started
-----------

Install the dependencies...

cd svelte-app
npm install

...then start Rollup:

npm run dev

Navigate to localhost:5000. You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using Visual Studio Code we recommend installing the official extension Svelte for VS Code. If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

Building and running in production mode
---------------------------------------

To create an optimised version of the app:

npm run build

You can run the newly built app with `npm run start`. This uses sirv, which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like Heroku.

Single-page app mode
--------------------

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for _any_ path. You can make it so by editing the `"start"` command in package.json:

"start": "sirv public --single"

Using TypeScript
----------------

This template comes with a script to set up a TypeScript development environment, you can run it immediately after cloning the template with:

node scripts/setupTypeScript.js

Or remove the script via:

rm scripts/setupTypeScript.js

Deploying to the web
--------------------

### With Vercel

Install `vercel` if you haven't already:

npm install -g vercel

Then, from within your project folder:

cd public
vercel deploy --name my-project

### With surge

Install `surge` if you haven't already:

npm install -g surge

Then, from within your project folder:

npm run build
surge public my-project.surge.sh
