---
project: fantong-action
stars: 1
description: null
url: https://github.com/binjoo/fantong-action
---

Douban sync for GitHub Actions
==============================

GitHub Action for douban movie/book/music marked data sync to csv file or notion automatically.

Input variables
---------------

See action.yml for more detailed information.

-   id: Douban ID
-   type: Douban data Type, enum value: movie, book, music, default `movie`
-   format: Douban data store format, enum value：csv, json, notion, default `csv`
-   dir: Target where douban data sync to. It's a file path for `csv` and `json` format, and a notion database id for `notion` format.
-   notion\_token: Notion Integration Token

Usage
-----

### Sync to CSV file

# .github/workflows/douban.yml
name: douban
on: 
  schedule:
  - cron: "30 \* \* \* \*"

jobs:
  douban:
    name: Douban mark data sync
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v2

    - name: movie
      uses: lizheming/doumark-action@master
      with:
        id: lizheming
        type: movie
        format: csv
        dir: ./data/douban

    - name: music
      uses: lizheming/doumark-action@master
      with:
        id: lizheming
        type: music
        format: csv
        dir: ./data/douban
  
    - name: Commit
      uses: EndBug/add-and-commit@v8
      with:
        message: 'chore: update douban data'
        add: './data/douban'

### Sync to Notion

1.  Create a Notion Integration at My Integrations - Notion. And here you can get `NOTION_TOKEN`.
    -   Associated workspace: You should select workspace which you should store.
    -   Capabilities: Both of `Read`, `Update` and `Insert` content abilities shoud checked.
2.  Duplicate database by click Duplicate at the top right postion of <Movie | Book | Music\> page.
3.  Share database to your Integration by inviting it with Share - Invite at the top right postion. And you can get database id, the first random string from url.

# .github/workflows/douban.yml
name: douban
on: 
  schedule:
  - cron: "30 \* \* \* \*"

jobs:
  douban:
    name: Douban mark data sync
    runs-on: ubuntu-latest
    steps:
    - name: movie
      uses: lizheming/doumark-action@master
      with:
        id: lizheming
        type: movie
        format: notion
        dir: xxxx
        notion\_token: ${{ secrets.notion\_token }}
        
    - name: music
      uses: lizheming/doumark-action@master
      with:
        id: lizheming
        type: music
        format: notion
        dir: xxxx
        notion\_token: 
        notion\_token: ${{ secrets.notion\_token }}
