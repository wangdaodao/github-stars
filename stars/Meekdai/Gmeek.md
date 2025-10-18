---
project: Gmeek
stars: 2211
description: Gmeek is a Blog All in Github
url: https://github.com/Meekdai/Gmeek
---

**简体中文** | **English** | **Русский**

Gmeek
=====

一个博客框架，超轻量级个人博客模板。完全基于`Github Pages` 、 `Github Issues` 和 `Github Actions`。不需要本地部署，从搭建到写作，只需要18秒，2步搭建好博客，第3步就是写作。

-   Demo页面
-   Gmeek更新日志
-   Gmeek快速上手

### 安装

1.  【创建仓库】点击通过模板创建仓库，建议仓库名称为`XXX.github.io`，其中`XXX`为你的github用户名。
    
2.  【启用Pages】在仓库的`Settings`中`Pages->Build and deployment->Source`下面选择`Github Actions`。
    
3.  【开始写作】打开一篇issue，开始写作，并且**必须**添加一个`标签Label`（至少添加一个），再保存issue后会自动创建博客内容，片刻后可通过https://XXX.github.io 访问（可进入Actions页面查看构建进度）。
    
4.  【手动全局生成】这个步骤只有在修改`config.json`文件或者出现奇怪问题的时候，需要执行。
    

```
通过Actions->build Gmeek->Run workflow->里面的按钮全局重新生成一次
```

### 提交问题

1.  如果有问题可参考Gmeek快速上手
2.  在本仓库提交Issues之前，请手动全局生成一次。如果还有错误，提交`Issues`后，我会帮忙查看构建流程，定位问题出处。

### 特性

-   UI界面和Github同源，只引入了Github原生CSS：primer.style
-   博客写作在Issues中完成后，自动触发Actions执行部署任务
-   评论系统引入utteranc.es
-   使用`jinja2`对html进行渲染，可通过模板自定义UI主题

### 赞赏

如果本项目对你有帮助，可以用微信赞赏一下作者，让项目有继续更新维护下去的动力，谢谢！

### 鸣谢

-   jinja2
-   utteranc.es
-   primer.style
-   gitblog

### License

请保留页面底部和console界面版权信息，谢谢！
