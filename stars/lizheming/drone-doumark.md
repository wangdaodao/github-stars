---
project: drone-doumark
stars: 37
description: Douban movie/book/music marked data sync plugin | 豆瓣观影/阅读/音乐记录同步
url: https://github.com/lizheming/drone-doumark
---

drone-doumark
-------------

Drone plugin for Douban movie/book/music/game marked data sync automatically.

Configuration
-------------

-   `PLUGIN_ID`: Douban ID
-   `DOUBAN_ID`: Same as `PLUGIN_ID`
-   `PLUGIN_TYPE`: Douban data Type, enum value: movie, book, music, game default `movie`
-   `DOUBAN_TYPE`: Same as `PLUGIN_TYPE`
-   `PLUGIN_STATUS`: Douban data status, enum value: mark, doing, done, default `done`
-   `DOUBAN_STATUS`: Same as `PLUGIN_STATUS`
-   `PLUGIN_FORMAT`: Douban data store format, enum value：csv, json, notion, neodb default `csv`
-   `DOUBAN_FORMAT`: Same as `PLUGIN_FORMAT`
-   `PLUGIN_DIR`: Target where douban data sync to. It's a file path for `csv` and `json` format, and a notion database id for `notion` format.
-   `DOUBAN_DIR`: Same as `PLUGIN_DIR`
-   `PLUGIN_NOTION_TOKEN`: Notion Integration Token
-   `DOUBAN_NOTION_TOKEN`: Same as `PLUGIN_NOTION_TOKEN`
-   `NOTION_TOKEN`: Same as `PLUGIN_NOTION_TOKEN`
-   `PLUGIN_NEODB_TOKEN`: NeoDB Access Token
-   `DOUBAN_NEODB_TOKEN`: Same as `PLUGIN_NEODB_TOKEN`
-   `NEODB_TOKEN`: Same as `PLUGIN_NEODB_TOKEN`

How to use
----------

### Sync to CSV file

Copy as `.drone.yml` file into your repo. Then set a `@houly` schedule cronjob at drone web page.

# .drone.yml
kind: pipeline
type: docker
name: default

clone:
  disable: true

steps:
- name: douban
  image: lizheming/drone-doumark
  settings:
    id: lizheming
    type: movie
    format: csv
    dir: ./data/douban

RUN with docker directly:

```
docker run --rm \
  -e PLUGIN_ID=lizheming
  -e PLUGIN_TYPE=movie
  -e PLUGIN_FORMAT=csv
  -e PLUGIN_DIR=./data/douban
  lizheming/drone-doumark
```

### Sync to Notion

1.  Create a Notion Integration at My Integrations - Notion. And here you can get `NOTION_TOKEN`.
    -   Associated workspace: You should select workspace which you should store.
    -   Capabilities: Both of `Read`, `Update` and `Insert` content abilities shoud checked.
2.  Duplicate database by click Duplicate at the top right postion of <Movie | Book | Music\> page.
3.  Share database to your Integration by inviting it with Share - Invite at the top right postion. And you can get database id, the first random string from url.
4.  Copy as `.drone.yml` file into your repo. Then set a `@houly` schedule cronjob at drone web page.

# .drone.yml
kind: pipeline
type: docker
name: default

clone:
  disable: true

steps:
- name: douban
  image: lizheming/drone-doumark
  settings:
    id: lizheming
    type: movie
    format: notion
    notion\_token: xxxxxx
    dir: xxxxxx

RUN with docker directly:

```
docker run --rm \
  -e PLUGIN_ID=lizheming
  -e PLUGIN_TYPE=movie
  -e PLUGIN_FORMAT=notion
  -e PLUGIN_NOTION_TOKEN=xxxxxx
  -e PLUGIN_DIR=xxxxxx
  lizheming/drone-doumark
```

### Sync to NeoDB

1.  Create a NeoDB Access Token at NeoDB API Developer Console.

# .drone.yml
kind: pipeline
type: docker
name: default

clone:
  disable: true

steps:
- name: douban
  image: lizheming/drone-doumark
  settings:
    id: lizheming
    type: movie
    format: neodb
    neodb\_token: xxxxx

RUN with docker directly:

```
docker run --rm \
  -e PLUGIN_ID=lizheming
  -e PLUGIN_TYPE=movie
  -e PLUGIN_FORMAT=neodb
  -e PLUGIN_NEODB_TOKEN=xxxxxx
  lizheming/drone-doumark
```
