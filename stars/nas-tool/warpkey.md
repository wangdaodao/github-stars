---
project: warpkey
stars: 67
description: CloudFlare Key Collection Tool CloudFlare WARP KEY收集工具，WARP KEY收集工具，每小时自动更新https://www.wanghaoyu.com.cn/archives/cloudflare-warp-key.html
url: https://github.com/nas-tool/warpkey
---

CloudFlare Warp KEY Collection Tool
===================================

English | 简体中文

Direct Access
-------------

You can directly access Warp KEY from the following URL (Update data every hour):

-   https://raw.githubusercontent.com/geeklinux-io/warpkey/main/data/lite
-   https://raw.githubusercontent.com/geeklinux-io/warpkey/main/data/full

You can also obtain it through my GitHub Pages:CloudFlare WARP Key (geeklinux-io.github.io)

Private Deployment
------------------

### 1\. Install Go

Make sure you have Go installed. You can download and install Go from the official Go website.

### 2\. Clone the Project

Clone this repository to your local environment:

git clone https://github.com/geeklinux-io/warpkey.git
cd warpkey

### 3\. Configure

If needed, you can edit the `main.go` file to adjust configurations.

### 4\. Run/Build

Once the Go environment is set up, you can use the following command to package the application:

chmod a+x build.sh
./build.sh

You can find the program you have compiled in the `./build` directory under the current directory.

The tool will collect keys from Telegram and save them in the `./data` directory under the current directory.

If you want to request the CloudFlare Key through a specific Socket or HTTP proxy, you can use the -- proxy parameter. Of course, you can also use the program - h to view specific usage help

5\. Auto Update
---------------

You can use crontab to schedule tasks to execute the `update.sh` script in your project and submit the updates to your GitHub repository

License
-------

This project is licensed under the MIT License. For more details, please see the LICENSE file.
