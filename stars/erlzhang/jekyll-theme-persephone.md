---
project: jekyll-theme-persephone
stars: 217
description: A minimal jekyll theme for building books and blog.
url: https://github.com/erlzhang/jekyll-theme-persephone
---

jekyll-theme-persephone
=======================

Welcome to your new Jekyll theme! In this directory, you'll find the files you need to be able to package up your theme into a gem. Put your layouts in `_layouts`, your includes in `_includes`, your sass files in `_sass` and any other assets in `assets`.

To experiment with this code, add some sample content and run `bundle exec jekyll serve` – this directory is setup just like a Jekyll site!

DEMO with full functions.

A simple blog demo

Demo
----

`layout: home` Demo

`layout: blog` Demo

`layout: post` Demo

`layout: page` Demo

**\*** `layout: book` Demo

**\*** `layout: chapter` Demo

The layout with red \* relied on a jekyll books generator plugin: `jekyll-books`

Installation
------------

Add this line to your Jekyll site's `Gemfile`:

gem "jekyll-theme-persephone"

And add this line to your Jekyll site's `_config.yml`:

theme: jekyll-theme-persephone

And then execute:

```
$ bundle
```

Or install it yourself as:

```
$ gem install jekyll-theme-persephone
```

Usage
-----

-   Settings
-   Layouts
-   Comments
-   `jekyll-books` generator

Contributing
------------

Bug reports and pull requests are welcome on GitHub at https://github.com/erlzhang/jekyll-theme-persephone. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the Contributor Covenant code of conduct.

Development
-----------

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled. To add a custom directory to your theme-gem, please edit the regexp in `jekyll-theme-persephone.gemspec` accordingly.

License
-------

The theme is available as open source under the terms of the MIT License.
