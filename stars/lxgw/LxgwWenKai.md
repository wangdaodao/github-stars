---
project: LxgwWenKai
stars: 18484
description: An open-source Chinese font derived from Fontworks' Klee One. 一款开源中文字体，基于 FONTWORKS 出品字体 Klee One 衍生。  
url: https://github.com/lxgw/LxgwWenKai
---

Important

-   添字请在 Issue #33 反馈，字形调整请在 Issue #14 反馈，不要另开议题，以便于整理。**由于字体文件越发臃肿，v1.330 更新发布后，加字反馈通道暂时关闭，不会接受用户加字请求，敬请谅解。**
-   若需要在网站上使用这款字体，请参阅 Issue #24，或者在 ZSFT 查找「霞鹜文楷」系列字体。
-   有关 Magisk 字体模块等手机字体替换有关的问题，请移步模块模板的 Issues 里反馈，不要在本项目开议题。
-   更多版本 _（可能会随时变动）_ ：
    -   霞鹜文楷屏幕阅读版 / LXGW WenKai Screen：适用于部分 Android 手机免 ROOT 更换第三方字体。
    -   霞鹜文楷 轻便版 / LXGW WenKai Lite：与完整版相比剔除一些较不常用的字符，便于开发者将字体嵌入软件中。
    -   霞鹜文楷 GB / LXGW WenKai GB：进一步调整字形和笔形，符合 G 源字形规范。轻便版
    -   霞鹜文楷 TC / LXGW WenKai TC：旧字形版参考「一点字坊」的「传承字形标准化文件」对部件进行修改，适用于繁体中文用户及旧字形爱好者。
    -   与其他西文字体合并的字体：LXGW Bright（与 Ysabeau Office 搭配）、LXGW Bright Code（与 Monaspace Argon 搭配）。

LXGW WenKai / 霞鹜文楷
==================

An open-source Chinese font derived from Fontworks' Klee One. 一款开源中文字体，基于 FONTWORKS 出品字体 Klee One 衍生。

项目简介
----

2020 年 12 月，日本著名字体厂商 FONTWORKS 在 GitHub 上发布了 7 款日文字体，分别为 **Train、Klee、Stick、Rock-n-Roll、Reggae、Rampart 和 DotGothic16**，根据 SIL Open Font License 1.1 授权许可开源。7 款开源日文字体各有各的特点，而这 7 款字体中，字符数量最多的是 Klee。

这是一款有着日本教科书体风格的字体，兼有仿宋和楷体的特点。一些 DIY 字体爱好者曾先后用仿宋等字体补全这款字体，作为手机系统的美化字体移植在 iOS、Android 等手机系统中，受到很多玩机发烧友的欢迎。不过这样补全的字体有一些不足之处。 **第一**，原有字体和后补字体之间有着一定的差异，致使一些不同的文字（如 Klee 原有汉字与后补简体字）混排之后会有一定的违和感。 **第二**，由于补字所用的字体为商业版权字体，补全之后不可用于商业用途，还会有侵权的风险。此外，目前现有的开源中文字库里，楷体类寥寥无几，仿宋类则几乎没有。

鉴于此，也为了丰富开源中文字体中的楷体门类，2021 年 1 月 20 日起，本人开始了为 Klee One 这一高质量的日文开源字体补全简繁常用字的尝试。因该字体具有一定的「文艺气息」，命名 **「霞鹜文楷」**_（其实当初是感觉这款字体适合正文阅读定名「文楷」，后来发现这款字体可能并不太适合大段正文排版，相比之下更加适合诗词之类的中等长度文本排版，或者注释排版）_。由于 Klee One 字体的 Regular 字重太细不太适合阅读，选取原字体 SemiBold 字重作为 Regular 字重。经过长时间的积累，目前已发展成简繁日韩均支持的 3 字重字体家族 （虽然拙劣粗糙了点） 。

有关补字过程的更多信息，请参阅本人 GitHub.io 博客里的文章：《为 Klee 试制简化字》。

「霞鹜文楷」支持 Unicode 变体序列（Unicode Variation Sequences, UVS），用于蝌蚪引号`“‘’”`宽度的选择，点击此处查看一览表。

字体预览
----

历史版本的 Release，请在 Release 页面查看。文字版本的更新记录 `HISTORY.MD` 不再维护，敬请谅解。

字汇
--

### 主要汉字部分

请参阅「霞鹜文楷 轻便版」加字计划。

### 其他部分

-   补完 CJK 统一汉字基本区 20992 个汉字、扩展 A 区 6592 个汉字 _（目前完整版有 1 万多个字形由 zi2zi 深度学习生成，字形较粗糙。）_ ；
-   补全常用谚文（韩语/朝鲜语）音节 2376 个。 _（做得比较拙劣。轻便版不包含。）_

获取字体
----

### ⅰ. 直接下载

1.  进入 Release 界面下载对应版本的 TTF 格式文件，或在本仓库 `fonts/TTF` 文件夹中下载。
2.  在 Gitee 官方镜像仓库 `fonts/TTF` 文件夹中下载。
3.  进入 猫啃网、Zfont.cn、自由字体 进行下载。GitHub 项目更新后，会联系站长进行更新，更新会稍晚些。 **注意：** 其它收录免费商用字体的网站上可能也收录了本字体，但可能不是最新版。
4.  永硕Ｅ盘、蓝奏云（密码：8ppk） 会在 GitHub 项目更新后 72 小时之内更新。
5.  如果您使用 macOS，已经安装过 Homebrew，可以在终端输入命令：`brew install font-lxgw-wenkai` 来安装本字体。
6.  如果您使用 Windows，已经安装过 Scoop，可以在终端输入命令：`scoop bucket add nerd-fonts && scoop install LXGWWenKai` 或者 `scoop bucket add nerd-fonts && scoop install LXGWWenKaiMono` 来安装本字体。亦可查看微软官方教程：如何在 Windows 中安装或删除字体。

### ⅱ. 从源代码生成

请运行 `./sources/build.bat` 或 `./sources/build.sh`。需要安装 `fontmake`：`pip3 install fontmake` 和 `fontTools`：`pip3 install fonttools`。

注意事项
----

1.  截至目前，完整版本字体含有全部 CJK 基本区和扩展 A 区汉字，以及零星扩展 B~I 区汉字。 **如有补字需求，请在 Issue #33 提出，不要另开 Issue**，以便于整理。 **由于字体文件越发臃肿，v1.330 更新发布后，加字反馈通道暂时关闭，不会接受用户加字请求，敬请谅解。**
2.  本人并不是专业的设计师，并未考虑设计美感，所以看起来可能略丑，补进去的字与原版可能略有违和感，且在 Medium 字重中部分字的轮廓曲线会有毛刺，Light 字重中部分字的轮廓会存在飞点；此外由于时间仓促，并没有多余的时间细修，部分字的部件拼接会很生硬。**如有字形优化建议，请在 Issue #14 提出，不要另开 Issue**，以便于整理。 _（以上两个 issue 均已加上 long term 标签，且均已在 Issues 页面置顶。）_
3.  **若需要在网站上使用这款字体，请参阅 Issue #24，或者在 ZSFT 查找「霞鹜文楷」系列字体。**
4.  对于搭配的西文字体，个人推荐 Ysabeau 系列字体。另有 Ysabeau Office 与霞鹜文楷轻便版的合并字体 LXGW Bright，采用 字体合并补全工具 将两款字体合并而成。亦有中英文合并的等宽字体 LXGW Bright Code，采用 Monaspace Argon 经缩窄调整后与霞鹜文楷轻便版合并而成。
5.  该字体的更多版本 _（可能会随时变动）_
    1.  霞鹜文楷屏幕阅读版 / LXGW WenKai Screen：以 Medium 字重为基准，调整度量数据与 Android 默认西文字体 Roboto 一致，适用于部分 Android 手机免 ROOT 更换第三方字体。
    2.  霞鹜文楷 轻便版 / LXGW WenKai Lite：剔除谚文及较不常用的汉字，便于开发者将字体嵌入软件中。若完整版有字形优化或特性更新，精简版也将会跟进。
    3.  霞鹜文楷 GB / LXGW WenKai GB：在文楷基础上进一步调整字形和笔形，符合 G 源字形规范。包含 GB 18030-2022 实现级别 2 范围内所有汉字。另有文楷 GB 轻便版。
    4.  霞鹜文楷 TC / LXGW WenKai TC：供繁体中文用户和旧字形爱好者使用，基于轻便版制作，采用旧字形写法，主要采用 Klee One 的隐藏字形，部分部件手动修改 （大部分部件参考一点字坊「传承字形标准化文件」，借助「汉文博士」「国学迷」「字统网」 等工具按部件查字，对字形进行修改）。此外已有基于 Klee One 改造的繁体中文字体 芫荽 / Iansui，采用台湾地区的教育标准字形；另有采用香港地区字形标准的 芫茜雅楷 / JyunsaiKaai。
6.  **本项目为字体项目，有关 Magisk 字体模块等手机字体替换有关的问题，请移步模块模板的 Issues 里反馈，不要在本项目开议题。**

协助完善
----

霞鹜文楷仍是一款完成度不算高的字体，诸多地方仍然存在瑕疵。欢迎更多志同道合的朋友在此基础上完善这款字体，您可以通过以下方式与本人联系。

-   **Telegram：** @lxgwtg | 频道
-   **微信公众号：** 霞鹜 _（ID: lxgwshare）_
-   **即刻、少数派、小红书、站酷、酷安：** @落霞孤鹜lxgw
-   **微博：** @孤鹜先森
-   **哔哩哔哩：** @霞鹜lxgw
-   **Email：** calxgw2018@gmail.com srtong2006@126.com lxgw1999@qq.com

授权信息
----

本字体是基于 SIL Open Font License 1.1 改造的 FONTWORKS 开发并发布的 Klee 开源项目。Klee 是 FONTWORKS 的商标。

> 猫啃网提供 SIL Open Font License 1.1 非官方简体中文译本便于理解，仅供参考。

### 许可

-   这款字体无论是个人还是企业都可以自由商用，无需付费，也无需知会或者标明原作者。 _（但如果告知，我会很感激。）_
-   这款字体可以自由传播、分享，或者将字体安装于系统、软件或APP中也是允许的，可以与任何软件捆绑再分发以及／或一并销售。
-   这款字体可以自由修改、改造，制作衍生字体。修改或改造后的字体也必须同样以 SIL OFL 公开。

### 限制

-   在制作衍生字体时，字体名称不可使用原有字体的「保留名称」。本字体保留名称「霞鹜」「LXGW」，基于本字体二次衍生的字体，名称不可出现「霞鹜」或「LXGW」字样；而在没有对字体源代码进行修改的情况下，重新编译出来的字体，可以继续使用本字体的保留名称「霞鹜」「LXGW」。
-   根据 SIL Open Font License 1.1「许可与条件」中第 1 条的规定， **禁止单独出售字体文件(OTF/TTF文件)的行为。**
-   该字体不可在 SIL Open Font License 1.1 以外的授权许可下发行。

鸣谢
--

-   FONTWORKS 株式会社 提供原始开源字体； 开发者 GitHub 主页
-   原始字体的设计师周建豪（Francis Chow）先生，以及 @CL-Jeremy、@夜煞之乐 等为字形设计提供指导；
-   @夜煞之乐 等为本项目的运营提供帮助；
-   @北辰極致卑微、@Georgome、@Magmeta、@Steve-Yuu 等协助完善字体；
-   Iosevka / Nerd-Fonts 提供等宽字体所用的 Powerline 符号；
-   zi2zi\_pytorch 以及深度学习生成字形的源头字体 思源宋体；
-   制表符、表意文字结构描述符（Ideographic Description Character, IDC）等字符借自 思源黑体；
-   吉祥图案、CC 许可图标等字符衍生自 煮豆黑体；
-   缺字标记 `.notdef` 的「🤔」外部轮廓取自 Noto Emoji (Monochrome)。

由本字体衍生的字体
---------

-   澳声通拼音文楷 (需配合 选音编辑器 使用)
-   计划楷 / PlanKai
-   秋水书体 / Qiushui Shotai

更多「霞鹜」系列字体
----------

### 「霞鹜文楷」系列

-   **霞鹜文楷 / LXGW WenKai** | Lite
-   霞鹜文楷 GB / LXGW WenKai GB | Lite
-   霞鹜文楷 TC / LXGW WenKai TC

### 「晰致尚铭」系列

-   霞鹜新晰黑 / LXGW Neo XiHei
-   霞鹜新致宋 / LXGW Neo ZhiSong
-   霞鹜晰黑 / LXGW XiHei
-   霞鹜致宋 / LXGW ZhiSong
-   霞鹜尚智黑 / LXGW Fasmart Gothic 停止维护
-   霞鹜铭心宋 / LXGW Heart Serif 停止维护

### 其他

-   霞鹜漫黑 / LXGW Marker Gothic
-   霞鹜臻楷 / LXGW ZhenKai
-   小赖字体 / Xiaolai
-   悠哉字体 / Yozai

打赏支持
----

点击进入打赏页面。

Stargazers over time
--------------------
