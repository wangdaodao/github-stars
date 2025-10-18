---
project: osmosfeed
stars: 968
description: Turn GitHub into an RSS reader
url: https://github.com/osmoscraft/osmosfeed
---

中文

osmos::feed
===========

An RSS reader running entirely from your GitHub repo.

-   Free hosting on GitHub Pages.
-   No need for backend. Content updates via GitHub Actions.
-   Customizable layouts and styles via templating and theming API. Just bring your HTML and CSS.
-   Free and open source. No ads. No third party tracking.

Want a host-free alternative? Check out the sister project: Fjord.

Demos
-----

### More examples

-   💻 Default template + Gruvbox dark | View source
-   😎 Default template + Solarized dark
-   ☀ Default template + Solarized light
-   🔨 Unstyled template for building from scratch.
-   📺 YouTube feed template + Material dark
-   🎧 Unstyled template for building a podcast feed

Browse all sources and more examples

Get started
-----------

### Create a repository

1.  Open Create a new repository from osmosfeed-template.
2.  Set visibility to "Public".  
    
3.  Click "Create repository from template" button.

### Turn on GitHub Pages

1.  In the repository you just created, navigate to **Settings** tab > **Pages** section.
    
2.  In **Source** option, select `gh-pages`, click "Save" button. If `gh-pages` doesn't exist, wait for a couple of seconds and refresh the page. It will eventually show up.  
    
3.  Refresh the page until it shows `Your site is published at https://<github_username>.github.io/<repo>`. This may take up to a minute.  
    

### Customize the feed

1.  In the repository root, open `osmosfeed.yaml` file, click the "Pencil (Edit this file)" button to edit.
    
2.  Remove `#` to uncommend the `cacheUrl` property, replace `<github_username>` with your GitHub username, and replace `<repo>` with your GitHub repo name.
    
3.  In the sources, update the items to the sources you want to follow. The final content of the file should look similar to this:
    
    cacheUrl: https://<github\_username>.github.io/<repo>/cache.json
    sources:
      - href: https://my-rss-source-1/feed/
      - href: https://my-rss-source-2/rss/
      - href: https://my-rss-source-3/feed
      - href: https://my-rss-source-4/news/rss
      - href: https://my-rss-source-5/rss/
    
4.  Scroll to the bottom of the page, click "Commit changes" button.
    
5.  Once the rebuild finishes, your feed will be available at `https://<github_username>.github.io/<repo>`.
    

Guides and references
---------------------

-   Customization guide
    -   Changing theme
    -   Changing template
    -   Add inline HTML, CSS, JavaScript
    -   Add static files
-   Configuration reference
-   Headless usage guide

To contribute
-------------

-   How to contribute
-   Developer guide

FAQ
---

### Can I update the content more frequently?

> Yes, you can make it as frequent as you want. In the `.github/workflows/update-feed.yaml` file, change the cron schedule. But be aware that there is a limit to the free tier of GitHub Actions. My rough estimate shows that even with hourly update, you should still have plenty of unused time. You can monitor spending on Billing & plans page in Account settings.

### Can I make the site private so only I can see it?

> It is not possible with GitHub Pages. However, if you move the site to a different hosting service, you should be able to set up authorization on the host level. For example, if you deploy to Netlify, there is a paid plan for password protection.

### Do I have to type `index.html` at the end of the URL?

> No. There is a known issue with GitHub, so you might have to type it until it starts to work. See discussion from GitHub Community and some solutions from Stack Overflow

### How to trigger a manual site update?

> You can make some changes to the `osmosfeed.yaml` file to trigger an update. For example, add an empty comment like this `#` on a new line.

### How to reset cache?

> You can browse to the `gh-pages` branch on GitHub at `https://github.com/<owner>/<repo>/tree/gh-pages`. Manually delete the `cache.json` file. Then trigger a manual site update.

Ecosystem
---------

Ecosystem
---------

Browse other projects from the OsmosCraft ecosystem.

-   Read the web with Fjord
-   Manage bookmarks with Memo
-   Take notes with Tundra
