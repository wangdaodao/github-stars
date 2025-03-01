---
project: rssbot
stars: 1613
description: Lightweight Telegram RSS notification bot. 用于消息通知的轻量级 Telegram RSS 机器人
url: https://github.com/iovxw/rssbot
---

rssbot
======

**Other Languages:** English

Telegram RSS 机器人 @RustRssBot

**支持:**

-   RSS 0.9
-   RSS 0.91
-   RSS 0.92
-   RSS 0.93
-   RSS 0.94
-   RSS 1.0
-   RSS 2.0
-   Atom 0.3
-   Atom 1.0
-   JSON Feed 1

使用
--

```
/rss       - 显示当前订阅的 RSS 列表
/sub       - 订阅一个 RSS: /sub http://example.com/feed.xml
/unsub     - 退订一个 RSS: /unsub http://example.com/feed.xml
/export    - 导出为 OPML
```

下载
--

可直接从 Releases 下载预编译的程序（带 `zh` 的为中文版）, Linux 版本为 _musl_ 静态链接, 无需其他依赖

编译
--

**请先尝试从上面下载, 如不可行或者有其他需求再手动编译**

先安装 _Rust Nightly_ 以及 _Cargo_ (推荐使用 `rustup`), 然后:

```
cargo build --release
```

编译好的文件位于: `./target/release/rssbot`

运行
--

```
USAGE:
    rssbot [FLAGS] [OPTIONS] <token>

FLAGS:
    -h, --help          Prints help information
        --insecure      DANGER: Insecure mode, accept invalid TLS certificates
        --restricted    Make bot commands only accessible for group admins
    -V, --version       Prints version information

OPTIONS:
        --admin <user id>...        Private mode, only specified user can use this bot. This argument can be passed
                                    multiple times to allow multiple admins
        --api-uri <tgapi-uri>       Custom telegram api URI [default: https://api.telegram.org/]
    -d, --database <path>           Path to database [default: ./rssbot.json]
        --max-feed-size <bytes>     Maximum feed size, 0 is unlimited [default: 2097152]
        --max-interval <seconds>    Maximum fetch interval [default: 43200]
        --min-interval <seconds>    Minimum fetch interval [default: 300]

ARGS:
    <token>    Telegram bot token

NOTE: You can get <user id> using bots like @userinfobot @getidsbot
```

`<token>` 请参照 这里 申请

环境变量
----

-   `HTTP_PROXY`: 用于 HTTP 的代理
-   `HTTPS_PROXY`: 用于 HTTPS 的代理
-   `RSSBOT_DONT_PROXY_FEEDS`: 设为 `1` 使所有订阅的 RSS 不通过代理（仅代理 Telegram）
-   `NO_PROXY`: 暂不支持，等待 reqwest#877

从旧的 RSSBot 迁移
-------------

对于 原先 Clojure 版本的 Bot, 可以使用以下脚本转换数据库

#!/bin/bash

DATABASE=$1
TARGET=$2

DATA=$(echo "SELECT url, title FROM rss;" | sqlite3 $DATABASE)
IFS=$'\\n'

echo -e "\[\\c" \> $TARGET
for line in ${DATA\[@\]}
do
    IFS='|'
    r=($line)
    link=${r\[0\]}
    title=${r\[1\]}

    echo -e "{\\"link\\":\\"$link\\"," \\
            "\\"title\\":\\"$title\\"," \\
            "\\"error\_count\\":0," \\
            "\\"hash\_list\\":\[\]," \\
            "\\"subscribers\\":\[\\c" \>> $TARGET

    subscribers=$(echo "SELECT subscriber FROM subscribers WHERE rss='$link';" | sqlite3 $DATABASE)
    IFS=$'\\n'
    for subscriber in ${subscribers\[@\]}
    do
        echo -e "$subscriber,\\c" \>> $TARGET
    done

    echo -e "\]},\\c" \>> $TARGET
done
echo "\]" \>> $TARGET
sed -i "s/,\]/\]/g" $TARGET

参数 1 为旧数据库地址, 2 为结果输出地址

需要注意的是已推送的 RSS 记录不会保留, 如果直接使用转换后的数据库, 会重复推送旧的 RSS

License
-------

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.
