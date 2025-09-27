---
project: siyuan
stars: 38114
description: A privacy-first, self-hosted, fully open source personal knowledge management software, written in typescript and golang.
url: https://github.com/siyuan-note/siyuan
---

  
_Refactor your thinking_  
  
  
  
  
  
  
  
  

中文 | 日本語

* * *

Table of Contents
-----------------

-   💡 Introduction
-   🔮 Features
-   🏗️ Architecture and Ecosystem
-   🌟 Star History
-   🗺️ Roadmap
-   🚀 Download Setup
    -   App Market
    -   Installation Package
    -   Docker Hosting
    -   Unraid Hosting
    -   Insider Preview
-   🏘️ Community
-   🛠️ Development Guide
-   ❓ FAQ
    -   How does SiYuan store data?
    -   Does it support data synchronization through a third-party sync disk?
    -   Is SiYuan open source?
    -   How to upgrade to a new version?
    -   What if some blocks (such as paragraph blocks in list items) cannot find the block icon?
    -   What should I do if the data repo key is lost?
    -   Do I need to pay for it?
-   🙏 Acknowledgement
    -   Contributors

* * *

💡 Introduction
---------------

SiYuan is a privacy-first personal knowledge management system, support fine-grained block-level reference and Markdown WYSIWYG.

Welcome to SiYuan English Discussion Forum to learn more.

🔮 Features
-----------

Most features are free, even for commercial use.

-   Content block
    -   Block-level reference and two-way links
    -   Custom attributes
    -   SQL query embed
    -   Protocol `siyuan://`
-   Editor
    -   Block-style
    -   Markdown WYSIWYG
    -   List outline
    -   Block zoom-in
    -   Million-word large document editing
    -   Mathematical formulas, charts, flowcharts, Gantt charts, timing charts, staffs, etc.
    -   Web clipping
    -   PDF Annotation link
-   Export
    -   Block ref and embed
    -   Standard Markdown with assets
    -   PDF, Word and HTML
    -   Copy to WeChat MP, Zhihu and Yuque
-   Database
    -   Table view
-   Flashcard spaced repetition
-   AI writing and Q/A chat via OpenAI API
-   Tesseract OCR
-   Multi-tab, drag and drop to split screen
-   Template snippet
-   JavaScript/CSS snippet
-   Android/iOS/HarmonyOS App
-   Docker deployment
-   API
-   Community marketplace

Some features are only available to paid members, for more details please refer to Pricing.

🏗️ Architecture and Ecosystem
------------------------------

Project

Description

Forks

Stars

lute

Editor engine

chrome

Chrome/Edge extension

bazaar

Community marketplace

dejavu

Data repo

petal

Plugin API

android

Android App

ios

iOS App

harmony

HarmonyOS App

riff

Spaced repetition

🌟 Star History
---------------

🗺️ Roadmap
-----------

-   SiYuan development plan and progress
-   SiYuan changelog

🚀 Download Setup
-----------------

It is recommended to give priority to installing through the application market on the desktop and mobile, so that you can upgrade the version with one click in the future.

### App Market

Mobile:

-   App Store
-   Google Play
-   F-Droid

Desktop:

-   Microsoft Store

### Installation Package

-   B3log
-   GitHub

### Docker Hosting

Docker Deployment

#### Overview

The easiest way to serve SiYuan on a server is to deploy it through Docker.

-   Image name `b3log/siyuan`
-   Image URL

#### File structure

The overall program is located under `/opt/siyuan/`, which is basically the structure under the resources folder of the Electron installation package:

-   appearance: icon, theme, languages
-   guide: user guide document
-   stage: interface and static resources
-   kernel: kernel program

#### Entrypoint

The entry point is set when building the Docker image: `ENTRYPOINT ["/opt/siyuan/entrypoint.sh"]`. This script allows changing the `PUID` and `PGID` of the user that will run inside the container. This is especially relevant to solve permission issues when mounting directories from the host. The `PUID` (User ID) and `PGID` (Group ID) can be passed as environment variables, making it easier to ensure correct permissions when accessing host-mounted directories.

Use the following parameters when running the container with `docker run b3log/siyuan`:

-   `--workspace`: Specifies the workspace folder path, mounted to the container via `-v` on the host
-   `--accessAuthCode`: Specifies the access authorization code

More parameters can be found using `--help`. Here’s an example of a startup command with the new environment variables:

docker run -d \\
  -v workspace\_dir\_host:workspace\_dir\_container \\
  -p 6806:6806 \\
  -e PUID=1001 -e PGID=1002 \\
  b3log/siyuan \\
  --workspace=workspace\_dir\_container \\
  --accessAuthCode=xxx

-   `PUID`: Custom user ID (optional, defaults to `1000` if not provided)
-   `PGID`: Custom group ID (optional, defaults to `1000` if not provided)
-   `workspace_dir_host`: The workspace folder path on the host
-   `workspace_dir_container`: The path of the workspace folder in the container, as specified in `--workspace`
    -   In alternative, it's possible to set the path via the `SIYUAN_WORKSPACE_PATH` env variable. The commandline will always have the priority, if both are set
-   `accessAuthCode`: Access authorization code (please **be sure to modify**, otherwise anyone can access your data)
    -   In alternative, it's possible to set the auth code via the `SIYUAN_ACCESS_AUTH_CODE` env variable. The commandline will always have the priority, if both are set
    -   To disable the Access authorization code set the env variable `SIYUAN_ACCESS_AUTH_CODE_BYPASS=true`

To simplify things, it is recommended to configure the workspace folder path to be consistent on the host and container, such as having both `workspace_dir_host` and `workspace_dir_container` configured as `/siyuan/workspace`. The corresponding startup command would be:

docker run -d \\
  -v /siyuan/workspace:/siyuan/workspace \\
  -p 6806:6806 \\
  -e PUID=1001 -e PGID=1002 \\
  b3log/siyuan \\
  --workspace=/siyuan/workspace/ \\
  --accessAuthCode=xxx

#### Docker Compose

For users running Siyuan with Docker Compose, the environment variables `PUID` and `PGID` can be passed to customize the user and group IDs. Here's an example of a Docker Compose configuration:

version: "3.9"
services:
  main:
    image: b3log/siyuan
    command: \['--workspace=/siyuan/workspace/', '--accessAuthCode=${AuthCode}'\]
    ports:
      - 6806:6806
    volumes:
      - /siyuan/workspace:/siyuan/workspace
    restart: unless-stopped
    environment:
      # A list of time zone identifiers can be found at https://en.wikipedia.org/wiki/List\_of\_tz\_database\_time\_zones
      - TZ=${YOUR\_TIME\_ZONE}
      - PUID=${YOUR\_USER\_PUID}  # Customize user ID
      - PGID=${YOUR\_USER\_PGID}  # Customize group ID

In this setup:

-   `PUID` and `PGID` are set dynamically and passed to the container
-   If these variables are not provided, the default `1000` will be used

By specifying `PUID` and `PGID` in the environment, you avoid the need to explicitly set the `user` directive (`user: '1000:1000'`) in the compose file. The container will dynamically adjust the user and group based on these environment variables at startup.

#### User Permissions

In the image, the `entrypoint.sh` script ensures the creation of the `siyuan` user and group with the specified `PUID` and `PGID`. Therefore, when the host creates a workspace folder, pay attention to setting the user and group ownership of the folder to match the `PUID` and `PGID` you plan to use. For example:

chown -R 1001:1002 /siyuan/workspace

If you use custom `PUID` and `PGID` values, the entrypoint script will ensure that the correct user and group are created inside the container, and ownership of mounted volumes will be adjusted accordingly. There’s no need to manually pass `-u` in `docker run` or `docker-compose` as the environment variables will handle the customization.

#### Hidden port

Use NGINX reverse proxy to hide port 6806, please note:

-   Configure WebSocket reverse proxy `/ws`

#### Note

-   Be sure to confirm the correctness of the mounted volume, otherwise the data will be lost after the container is deleted
-   Do not use URL rewriting for redirection, otherwise there may be problems with authentication, it is recommended to configure a reverse proxy
-   If you encounter permission issues, verify that the `PUID` and `PGID` environment variables match the ownership of the mounted directories on your host system

#### Limitations

-   Does not support desktop and mobile application connections, only supports use on browsers
-   Export to PDF, HTML and Word formats is not supported
-   Import Markdown file is not supported

### Unraid Hosting

Unraid Deployment

Note: First run `chown -R 1000:1000 /mnt/user/appdata/siyuan` in the terminal

Template reference:

```
Web UI: 6806
Container Port: 6806
Container Path: /home/siyuan
Host path: /mnt/user/appdata/siyuan
PUID: 1000
PGID: 1000
Publish parameters: --accessAuthCode=******(Access authorization code)
```

### Insider Preview

We release insider preview before major updates, please visit https://github.com/siyuan-note/insider.

🏘️ Community
-------------

-   English Discussion Forum
-   User community summary
-   Awesome SiYuan

🛠️ Development Guide
---------------------

See Development Guide.

❓ FAQ
-----

### How does SiYuan store data?

The data is saved in the workspace folder, in the workspace data folder:

-   `assets` is used to save all inserted assets
-   `emojis` is used to save emoji images
-   `snippets` is used to save code snippets
-   `storage` is used to save query conditions, layouts and flashcards, etc.
-   `templates` is used to save template snippets
-   `widgets` is used to save widgets
-   `plugins` is used to save plugins
-   `public` is used to save public data
-   The rest of the folders are the notebook folders created by the user, files with the suffix of `.sy` in the notebook folder are used to save the document data, and the data format is JSON

### Does it support data synchronization through a third-party sync disk?

Data synchronization through third-party synchronization disks is not supported, otherwise data may be corrupted.

Although it does not support third-party sync disks, it supports connect with third-party cloud storage (Member's privileges).

In addition, you can also consider manually exporting and importing data to achieve data synchronization:

-   Desktop: Settings - Export - Export Data / Import Data
-   Mobile: Right column - About - Export Data / Import Data

### Is SiYuan open source?

SiYuan is completely open source, and contributions are welcome:

-   User Interface and Kernel
-   Android
-   iOS
-   HarmonyOS
-   Chrome Clipping Extension

For more details, please refer to Development Guide.

### How to upgrade to a new version?

-   If installed via app store, please update via app store
-   If it is installed through the installation package on the desktop, you can open the option of Settings - About - Automatically download update installation package, so that SiYuan will automatically download The latest version of the installation package and prompts to install
-   If it is installed by manual installation package, please download the installation package again to install

You can Check update in Settings - About - Current Version, or pay attention to Official Download or GitHub Releases to get the new version.

### What if some blocks (such as paragraph blocks in list items) cannot find the block icon?

The first sub-block under the list item is the block icon omitted. You can move the cursor into this block and trigger its block menu with Ctrl+/ .

### What should I do if the data repo key is lost?

-   If the data repo key is correctly initialized on multiple devices before, the key is the same on all devices and can be set in Settings - About - Data repo key - Copy key string retrieve
    
-   If it has not been configured correctly before (for example, the keys on multiple devices are inconsistent) or all devices are unavailable and the key string cannot be obtained, you can reset the key by following the steps below:
    
    1.  Manually back up the data, you can use Export Data or directly copy the workspace/data/ folder on the file system
    2.  Settings - About - Data rep key - Reset data repo
    3.  Reinitialize the data repo key. After initializing the key on one device, other devices import the key
    4.  The cloud uses the new synchronization directory, the old synchronization directory is no longer available and can be deleted
    5.  The existing cloud snapshots are no longer available and can be deleted

### Do I need to pay for it?

Most features are free, even for commercial use.

Member's privileges can only be used after payment, please refer to Pricing.

🙏 Acknowledgement
------------------

The birth of SiYuan is inseparable from many open source projects and contributors, please refer to the project source code kernel/go.mod, app/package.json and project homepage.

The growth of SiYuan is inseparable from user feedback and promotion, thank you for everyone's help to SiYuan ❤️

### Contributors

Welcome to join us and contribute code to SiYuan together.
