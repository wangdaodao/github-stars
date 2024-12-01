---
project: actionsflow-trigger-rsshub
stars: 25
description: Actionsflow trigger for rsshub
url: https://github.com/theowenyoung/actionsflow-trigger-rsshub
---

`@actionsflow/trigger-rsshub`
=============================

This is an Actionsflow `rsshub` trigger. With this trigger, you can easily get rsshub updates.

Install
-------

npm i @actionsflow/trigger-rsshub

Usage
=====

Single path:

on:
  rsshub:
    path: /smzdm/keyword/女装

Multiple paths:

on:
  rsshub:
    path:
      - /smzdm/keyword/女装
      - /36kr/news/latest
    config:
      limit: 15

Or, you can pass them separately:

on:
  rsshub:
    path:
      - path: /smzdm/keyword/女装
        query:
          param1: value
      - path: /36kr/news/latest
        query:
          param1: value
    config:
      limit: 15

Options
-------

-   `path`, required, `string` or `string[]` or `object[]`, when `path` is `string[]`, then multiple rsshub feeds can trigger the action. For path value, you should check at rsshub, all rsshub routes are supported.
    
-   `globalQuery`, optional, `object`, rsshub global query, it will set to every rsshub request search. For example: `{"limit":10,"filter":"test"}`, for more query params, please see here
    
-   `rsshubConfig`, optional, `object`, rsshub init config, for more config settings, please see here
    

> You can use General Config for Actionsflow Trigger for more customization.

Outputs
-------

An outputs example:

{
  "title": "UNIQLO 优衣库 426026 女士牛仔抽绳连衣裙 - 79元",
  "description": "UNIQLO 优衣库 426026 女士牛仔抽绳连衣裙 ，采用100%棉质，舒适透气，款型舒适，腰部附带抽绳，便于调节松紧度。下单到手价79元，近期好价，喜欢的可以购买了。<br>天猫精选<br><img src=\\"http://qny.smzdm.com/202003/24/5e796b40660e23474.jpg\_d200.jpg\\" referrerpolicy=\\"no-referrer\\"\>",
  "pubDate": "Wed, 23 Sep 2020 16:40:00 GMT",
  "link": "https://www.smzdm.com/p/25102718/",
  "\_\_channel\_title": "女装 - 什么值得买",
  "\_\_channel\_link": "http://search.smzdm.com/?c=home&s=%E5%A5%B3%E8%A3%85&order=time&v=b"
}

You can use the outputs like this:

on:
  rsshub:
    path: /smzdm/keyword/女装
jobs:
  print:
    name: Print
    runs-on: ubuntu-latest
    steps:
      - name: Print Outputs
        env:
          title: ${{on.rsshub.outputs.title}}
          description: ${{on.rsshub.outputs.description}}
          link: ${{on.rsshub.outputs.link}}
        run: |
          echo title: $title
          echo description: $description
          echo link: $link
