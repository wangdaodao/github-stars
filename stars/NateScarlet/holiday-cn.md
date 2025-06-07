---
project: holiday-cn
stars: 1507
description: 📅🇨🇳中国法定节假日数据 自动每日抓取国务院公告
url: https://github.com/NateScarlet/holiday-cn
---

holiday-cn
==========

中国法定节假日数据 自动每日抓取国务院公告

-   提供 JSON 格式节假日数据
-   CI 自动更新
-   数据变化时自动发布新版本 ( `Watch` - `Release only` 以获取邮件提醒! )
-   发布页面提供 JSON 打包下载

数据格式:

JSON Schema

interface Holidays {
  /\*\* 完整年份, 整数。\*/
  year: number;
  /\*\* 所用国务院文件网址列表 \*/
  papers: string\[\];
  days: {
    /\*\* 节日名称 \*/
    name: string;
    /\*\* 日期, ISO 8601 格式 \*/
    date: string;
    /\*\* 是否为休息日 \*/
    isOffDay: boolean;
  }\[\]
}

注意事项
----

-   年份是按照国务院文件标题年份而不是日期年份，12 月份的日期可能会被下一年的文件影响，因此应检查两个文件。
    
-   `与周末连休` 的周末不是法定节假日，数据里不会包含，见《全国年节及纪念日放假办法》 #213 #221
    

通过互联网使用
-------

提示：任何第三方服务都可能故障或停止服务，如果稳定性要求高请自己搭建静态文件服务。

数据地址格式:

`https://raw.githubusercontent.com/NateScarlet/holiday-cn/master/{年份}.json`

或使用 JSDelivr：

`https://cdn.jsdelivr.net/gh/NateScarlet/holiday-cn@master/{年份}.json`

`https://fastly.jsdelivr.net/gh/NateScarlet/holiday-cn@master/{年份}.json`

也可尝试使用 ghproxy 或其他 Github 加速：

`https://{ghproxy服务}/https://raw.githubusercontent.com/NateScarlet/holiday-cn/master/{年份}.json`

访问 github 不方便时可使用国内镜像仓库 2022-08-05: coding 现在要求登录才能下载开源仓库的文件。

`https://natescarlet.coding.net/p/github/d/holiday-cn/git/raw/master/{年份}.json`

ICalendar 订阅
------------

网址格式参见上一节

`{年份}.ics` 为对应年份的节假日

`holiday-cn.ics` 为 3 年前至次年的节假日

感谢 @retanoj 的 ics 格式转换实现

作为 git 子模块使用
------------

参见 Git 工具 - 子模块
