---
project: i18nTool
stars: 6
description: NodeJS处理国际化
url: https://github.com/goldEli/i18nTool
---

NodeJS处理国际化
===========

国际化具体步骤
-------

1.  提取代码中全量的中文，并生成资源文件。
2.  开发过程中，新增了中文，需要提取出来，供翻译。翻译完成后合并到资源文件。
3.  开发完成， 将项目代码中的中文全部替换成变量，然后打包发布。

start
-----

### 安装依赖：

```
npm install
```

### 运行

提取代码中所有的的中文，并生成资源文件(`/zh` `/en`)

```
node forBegin.js
```

开发过程中(提取全部中文，并对比，生成增量资源`/inResource`)

```
node forDev.js
```

开发完成（替换中文, 生成`src_translate`）

```
node forBuild.js
```

note
----

为方便正则匹配，应规范中文书写：

-   中文需要加英文双引号，比如:

```
"这里是中文"
```

-   中文下在jsx中需要加{}，比如:

```
<p>{"这里是中文"}</p>
```

-   考虑正则匹配的准确性，请将中文尽可能的单独一行
