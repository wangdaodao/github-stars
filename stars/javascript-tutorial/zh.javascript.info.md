---
project: zh.javascript.info
stars: 9963
description: 现代 JavaScript 教程（The Modern JavaScript Tutorial），以最新的 ECMAScript 规范为基准，通过简单但足够详细的内容，为你讲解从基础到高阶的 JavaScript 相关知识。
url: https://github.com/javascript-tutorial/zh.javascript.info
---

现代 JavaScript 教程中文版
===================

本教程为 React 官方文档 与 MDN 共同推荐的前端教程，持续更新，永久免费，欢迎扫码关注微信公众号，加入读者群。群内自由交流技术，群友帮忙答疑，共同进步！

微信扫码关注官方订阅号，订阅更多精彩内容

**加入读者交流群：**

-   **微信群**：加微信 **`imleviding`** 或 扫二维码，验证信息填写 **`JS 教程`**。
-   **QQ 群**：打开 QQ 搜索群号 **`955916282`** 或 扫二维码，验证信息填写 **`JS 教程`**。

本项目托管了现代 JavaScript 教程中文版的内容，此内容发布在 https://zh.javascript.info

目录
--

-   翻译
-   贡献指南
-   文件结构
-   翻译提示
    -   专有词条
    -   词条含义
    -   标点符号
    -   代码块中的文本
    -   外部链接
    -   诠释资料
    -   Anchors
-   与英文版同步更新
-   管理员注意事项
-   更多
-   在本地运行

翻译
--

我们希望本教程可以以更多语言呈现。如果你感兴趣，那就快来和我们一起翻译吧。

详见 翻译进度。

贡献指南
----

我们希望与更多人一起维护本教程。

发现有错误？发现有些主题教程中没有？那就赶快提交 Pull Request 来想大家分享你的知识吧 👏

**你可以在任何编辑器中编辑本项目中的文件**。本教程使用增强的 "MarkDown" 格式，易于掌握。而且，如果你想在本地预览效果，我们也提供了一个可以在本地运行本教程的服务端 https://github.com/javascript-tutorial/server。

详细贡献者列表请见 https://javascript.info/about#contributors。

### 翻译流程

-   检查 中文翻译进度 issue（Chinese Translate Progress issue）。
-   选择一篇还没有被选走（在 列表 中暂未被人勾选）的文章。
-   在 该 issue 中添加以文章标题为内容的评论，如 `An Introduction to JavaScript`。
    -   我们的 bot 会在 列表 中勾选上对应的文章，这样其他人就知道你正在翻译该文章了。
    -   不要在该评论中添加其他说明。
    -   如果你发现有些文章索然已经被勾选，但是勾选人在认领任务后 15 天内未提交译文，此时你仍可以发表以该文章标题为内容的评论（并 @leviding），如 `An Introduction to JavaScript @leviding`。
-   Fork 此仓库并开始翻译。完成翻译后，请提交一个 PR（请在认领翻译后的 15 天内提交）。
    -   PR 应以文章标题命名。Bot 会自动补充更多信息。

请给维护者时间来审核和 merge 你的翻译，或者提出对应的修改意见。

如果你想成为一个维护者，请在 给我们提新 issue。

**如果你愿意的话，请让其他人知道你在翻译这个教程，并尝试邀请他们参与翻译。你可以通过微博或群聊来号召。**

🎉 非常感谢！

目前中文版已上线，我们会在“关于本项目”页面写上你的名字和贡献。

注：https://javascript.info/translate 列出了完整的语言列表。

文件结构
----

每一个章节或任务都有它自己的文件夹。

文件夹以 `N-url` 命名，`N` 为用于排序的数字，`url` 是该内容在网站上的链接中带有内容标题的部分。

文件的类型是依据文件夹中的文件定义的：

-   `index.md` 对应一个章节，
-   `article.md` 对应一篇文章，
-   `task.md` 对应一个任务（对应的答案必须在 `solution.md` 文件中提供）。

每一个文件都以 `# 一级标题` 开始。

添加新内容非常容易。

翻译提示
----

请不要添加换行，段落或移除已有的行和段落。这样可以减少 merge 英文版中的新变化时出现的问题。

如果你觉得英文版可以被改善 —— 欢迎，请给 英文版教程发 PR。

### 专有词条

-   一些具体的专有词不应被翻译。如 “Function Declaration”。
-   对于其他专有词，如 `resolved promise`、`slash` 和 `regexp` 等等，请先找找本项目 WIKI 中的「英文－中文」术语对照表 中是否已有对应的词条。
    -   若没有对应或近似的近似，则可以寻找其他教程（如：MDN）的翻译。

**补充：**

-   专有词条翻译完，在其后方以括号加英文的方式补上原词条，例如：同源政策（Same Origin Policy）或转义（transpile），等等。
    -   若一篇文章出現两次以上相同专有词条，则在第一次之后补上原词条即可。
-   若都无法找到对应的词条翻译，请直接留下原文词条。

### 词条含义

在英文中很多词条有明确的含义在內，但对于一个不了解英文的人来说，会忽略该含义。

请谨记有必要时可以多加解释或增加额外的翻译，例如：

\`ReadableStream\` objects allows to read data chunk-by-chunk.

\`ReadableStream\` objects 允许一个个资料块（chunk）地读取资料。

### 标点符号

-   本教程标点符号格式采用 此份指南。
    
-   资料链接、**粗体**，都须 留下空白。
    
-   中文无斜体形式，英文的斜体翻译至中文改为 **加粗**。
    
-   斜线号 `/` 较为特殊，若用于分隔两同类型词条时，请维持半形斜线且两侧不加空白，**但在词汇们整体的前后要留一空白做分隔：**
    
    -   `Increment/decrement can only be applied to variables.`：`递增/递减 只能被套用在变量上。`
    -   `If the result of increment/decrement is not used, ...`：`如果 递增/递减 的結果没被使用，...`
-   英文一句话只能有一个逗号，但中文无此限制，可依据语气通顺程度将一些英文句点转为逗号。
    
-   列举项目后的文字需加句号。<- 像这样
    

### 代码块中的文本

-   翻译注释。
-   翻译展示给用户的信息和用来举例的字符串。
-   不要翻译变量（variables）、类（classes）和标识符（identifiers）。
-   确保翻译后的代码可以正常运行。 :)

例：

// Example
const text \= "Hello, world";
document.querySelector('.hello').innerHTML \= text;

✅ 请这样翻译（翻译注解）：

// 范例
const text \= 'Hello, world';
document.querySelector('.hello').innerHTML \= text;

❌ 別翻译成（不要翻译类）：

// 范例
const text \= 'Hello, world';
// ".hello" 是一个类
// 不要翻译
document.querySelector('.你好').innerHTML \= text;

### 外部链接

**本翻译教程以维持原本外部链接为原则。**

但如果这个外部链接是指向 Wikipedia 的，如 `https://en.wikipedia.org/wiki/JavaScript`，并且其有质量优良的目标语言的译文，请将链接指向该译文。

例如：

\[JavaScript\](https://en.wikipedia.org/wiki/JavaScript) is a programming language.

✅ OK (en -> zh):

\[JavaScript\](https://zh.wikipedia.org/wiki/JavaScript) 是一种编程语言。

对于指向 MDN 的外部链接，可以使用部分翻译的版本。

如果外部链接没有翻译的版本，请不要修改该链接。

### 诠释资料

一些文件，通常是练习题，顶部会有 YAML 的诠释资料（Metadata）并以 `---` 分隔：

importance: 5

\---
...

请不要翻译 “importance”（和其他放置在顶端的诠释资料）。

### Anchors

某些标题以 `[#anchor]` 结尾，如：

\## 扩散运算符 \[#spread-operator\]

请不要翻译或者去掉 `[#...]` 部分，它是 URL 锚点元素的依赖。

与英文版同步更新
--------

详见 WIKI 中的「如何进行此教程的后续更新」。

管理员注意事项
-------

详见 WIKI 中的「管理员注意事项」。

更多
--

更多说明请见 WIKI。

在本地运行
-----

你可以在本地运行本教程的服务端来预览你的翻译。

运行服务端的教程请见 https://github.com/javascript-tutorial/server。

* * *

本中文版教程的核心维护者 🚀

-   LeviDing @leviding
-   Martin @MartinsYong
-   Bemself bemself
-   LycheeEng @lycheeEng

我们希望与大家合作维护本教程。本教程的详细贡献者列表请见：https://zh.javascript.info/about。
