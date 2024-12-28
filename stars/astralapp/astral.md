---
project: astral
stars: 3243
description: Organize Your GitHub Stars With Ease
url: https://github.com/astralapp/astral
---

Astral
======

An open source application that allows you to organize your GitHub Stars with ease. Use the hosted version free, or self-host your own instance with the instructions below!

Installation
------------

### Prerequisites

-   To run this project, you must have PHP 7 Node.js, and Yarn installed.
-   You should setup a host on your web server for your local domain. For this you could also configure Laravel Homestead or Valet.
-   Create a new GitHub OAuth App so you can plug in your API keys.

### Step 1

Begin by cloning this repository to your machine, and installing all Composer & NPM dependencies.

git clone git@github.com:astralapp/astral.git
cd astral && composer install && yarn
php artisan astral:install
yarn dev

### Step 2

Next, boot up a server to visit the app. If you're using a tool like Laravel Valet, the URL will likely default to `http://astral.test`. That's pretty much it!

Deploying
---------

-   1-Click Install with Cloudron

Contributing
------------

As the `next` branch is the future of this project, I kindly ask that you do _not_ submit any pull requests to the `master` branch with new features, as it may have already been covered in the `next` branch, or your code may be incompatible. If you have found a bug or security issue that you would like to fix, I will still accept any pull requests for these cases. Thank you for understanding!
