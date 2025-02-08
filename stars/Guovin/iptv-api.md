---
project: iptv-api
stars: 13060
description: 📺IPTV电视直播源更新项目『✨秒播级体验🚀』：支持IPv4/IPv6；支持自定义频道；支持本地源、组播源、酒店源、订阅源、关键字搜索；每天自动更新两次，结果可用于TVBox等播放软件；支持工作流、Docker(amd64/arm64/arm v7)、命令行、GUI运行方式 | IPTV live TV source update project
url: https://github.com/Guovin/iptv-api
---

IPTV-API
========

一个可高度自定义的IPTV接口更新项目📺，自定义频道菜单，自动获取直播源，测速验效后生成可用的结果，可实现『✨秒播级体验🚀』

  

English | 中文

-   ✅ 特点
-   🔗 最新结果
-   ⚙️ 配置参数
-   🚀 快速上手
    -   工作流
    -   命令行
    -   GUI软件
    -   Docker
-   📖 详细教程
-   🗓️ 更新日志
-   ❤️ 赞赏
-   👀 关注(更新订阅+答疑交流)
-   📣 免责声明
-   ⚖️ 许可证

📍订阅源来自：

-   iptv-org/iptv
-   suxuang/myIPTV
-   kimwang1978/collect-tv-txt
-   xzw832/cmys
-   asdjkl6/tv
-   yuanzl77/IPTV
-   fanmingming/live
-   vbskycn/iptv
-   YueChan/Live
-   YanG-1989/m3u

📍频道图标来自：

-   fanmingming/live

特点
--

-   ✅ 自定义模板，生成您想要的频道
-   ✅ 支持多种获取源方式：本地源、组播源、酒店源、订阅源、关键字搜索
-   ✅ 接口测速验效，获取延迟、速率、分辨率，过滤无效接口
-   ✅ 偏好设置：IPv4、IPv6、接口来源排序优先级与数量配置、接口白名单
-   ✅ 定时执行，北京时间每日 6:00 与 18:00 执行更新
-   ✅ 支持多种运行方式：工作流、命令行、GUI 软件、Docker(amd64/arm64/arm v7)
-   ✨ 更多功能请见配置参数

最新结果
----

-   接口源：

https://raw.githubusercontent.com/Guovin/iptv-api/gd/output/result.m3u

https://raw.githubusercontent.com/Guovin/iptv-api/gd/output/result.txt

或

https://cdn.jsdelivr.net/gh/Guovin/iptv-api@gd/output/result.m3u

https://cdn.jsdelivr.net/gh/Guovin/iptv-api@gd/output/result.txt

-   数据源：

https://raw.githubusercontent.com/Guovin/iptv-api/gd/source.json

或

https://cdn.jsdelivr.net/gh/Guovin/iptv-api@gd/source.json

配置
--

配置项

描述

默认值

open\_driver

开启浏览器运行，若更新无数据可开启此模式，较消耗性能

False

open\_empty\_category

开启无结果频道分类，自动归类至底部

False

open\_filter\_resolution

开启分辨率过滤，低于最小分辨率（min\_resolution）的接口将会被过滤，GUI用户需要手动安装FFmpeg，程序会自动调用FFmpeg获取接口分辨率，推荐开启，虽然会增加测速阶段耗时，但能更有效地区分是否可播放的接口

True

open\_filter\_speed

开启速率过滤，低于最小速率（min\_speed）的接口将会被过滤

True

open\_hotel

开启酒店源功能，关闭后所有酒店源工作模式都将关闭

True

open\_hotel\_foodie

开启 Foodie 酒店源工作模式

True

open\_hotel\_fofa

开启 FOFA、ZoomEye 酒店源工作模式

True

open\_keep\_all

开启保留所有检索结果，会保留非模板频道名称的结果，推荐手动维护时开启

False

open\_local

开启本地源功能，将使用模板文件与本地源文件中的数据

True

open\_m3u\_result

开启转换生成 m3u 文件类型结果链接，支持显示频道图标

True

open\_multicast

开启组播源功能，关闭后所有组播源工作模式都将关闭

True

open\_multicast\_foodie

开启 Foodie 组播源工作模式

True

open\_multicast\_fofa

开启 FOFA 组播源工作模式

True

open\_online\_search

开启关键字搜索源功能

False

open\_proxy

开启代理，自动获取免费可用代理，若更新无数据可开启此模式

False

open\_request

开启查询请求，数据来源于网络（仅针对酒店源与组播源）

False

open\_service

开启页面服务，用于控制是否启动结果页面服务；如果使用青龙等平台部署，有专门设定的定时任务，需要更新完成后停止运行，可以关闭该功能

True

open\_sort

开启排序功能（响应速度、日期、分辨率）

True

open\_subscribe

开启订阅源功能

False

open\_supply

开启补偿机制模式，用于控制当频道接口数量不足时，自动将不满足条件（例如低于最小速率）但可能可用的接口添加至结果中，从而避免结果为空的情况

True

open\_update

开启更新，用于控制是否更新接口，若关闭则所有工作模式（获取接口和测速）均停止

True

open\_update\_time

开启显示更新时间

True

open\_url\_info

开启显示接口说明信息，用于控制是否显示接口来源、分辨率、协议类型等信息，为$符号后的内容，播放软件使用该信息对接口进行描述，若部分播放器（如PotPlayer）不支持解析导致无法播放可关闭

False

open\_use\_cache

开启使用本地缓存数据，适用于查询请求失败场景（仅针对酒店源与组播源）

True

open\_history

开启使用历史更新结果（包含模板与结果文件的接口），合并至本次更新中

True

app\_port

页面服务端口，用于控制页面服务的端口号

8000

final\_file

生成结果文件路径

output/result.txt

hotel\_num

结果中偏好的酒店源接口数量

10

hotel\_page\_num

酒店地区获取分页数量

1

hotel\_region\_list

酒店源地区列表，"全部"表示所有地区

全部

ipv4\_num

结果中偏好的 IPv4 接口数量

5

ipv6\_num

结果中偏好的 IPv6 接口数量

5

ipv6\_support

强制认为当前网络支持IPv6，跳过检测

False

ipv\_type

生成结果中接口的协议类型，可选值：ipv4、ipv6、全部、all

全部

ipv\_type\_prefer

接口协议类型偏好，优先将该类型的接口排在结果前面，可选值：ipv4、ipv6、自动、auto

ipv6,ipv4

local\_file

本地源文件路径

config/local.txt

local\_num

结果中偏好的本地源接口数量

10

min\_resolution

接口最小分辨率，需要开启 open\_filter\_resolution 才能生效

1920x1080

min\_speed

接口最小速率（单位M/s），需要开启 open\_filter\_speed 才能生效

0.2

multicast\_num

结果中偏好的组播源接口数量

10

multicast\_page\_num

组播地区获取分页数量

1

multicast\_region\_list

组播源地区列表，"全部"表示所有地区

全部

online\_search\_num

结果中偏好的关键字搜索接口数量

0

online\_search\_page\_num

关键字搜索频道获取分页数量

1

origin\_type\_prefer

结果偏好的接口来源，结果优先按该顺序进行排序，逗号分隔，例如：local,hotel,multicast,subscribe,online\_search；local：本地源，hotel：酒店源，multicast：组播源，subscribe：订阅源，online\_search：关键字搜索；不填写则表示不指定来源，按照接口速率排序

recent\_days

获取最近时间范围内更新的接口（单位天），适当减小可避免出现匹配问题

30

request\_timeout

查询请求超时时长，单位秒(s)，用于控制查询接口文本链接的超时时长以及重试时长，调整此值能优化更新时间

10

sort\_timeout

单个接口测速超时时长，单位秒(s)；数值越大测速所属时间越长，能提高获取接口数量，但质量会有所下降；数值越小测速所需时间越短，能获取低延时的接口，质量较好；调整此值能优化更新时间

10

sort\_duplicate\_limit

相同域名接口允许重复执行次数，用于控制执行测速、获取分辨率时的重复次数，数值越大结果越准确，但耗时会增加

3

source\_file

模板文件路径

config/demo.txt

subscribe\_num

结果中偏好的订阅源接口数量

10

time\_zone

时区，可用于控制更新时间显示的时区，可选值：Asia/Shanghai 或其它时区编码

Asia/Shanghai

urls\_limit

单个频道接口数量

10

update\_time\_position

更新时间显示位置，需要开启 open\_update\_time 才能生效，可选值：top、bottom，top: 显示于结果顶部，bottom: 显示于结果底部

top

快速上手
----

### 工作流

Fork 本项目并开启工作流更新，具体步骤请见详细教程

### 命令行

pip install pipenv

pipenv install --dev

启动更新：

pipenv run dev

启动服务：

pipenv run service

### GUI 软件

1.  下载IPTV-API 更新软件，打开软件，点击更新，即可完成更新
    
2.  或者在项目目录下运行以下命令，即可打开 GUI 软件：
    

pipenv run ui

### Docker

-   iptv-api（完整版本）：性能要求较高，更新速度较慢，稳定性、成功率高；修改配置 open\_driver = False 可切换到 Lite 版本运行模式（推荐酒店源、组播源、关键字搜索使用此版本）
-   iptv-api:lite（精简版本）：轻量级，性能要求低，更新速度快，稳定性不确定（推荐订阅源使用此版本）

#### 1\. 拉取镜像

-   iptv-api

docker pull guovern/iptv-api:latest

🚀 代理加速（推荐国内用户使用）：

docker pull docker.1ms.run/guovern/iptv-api:latest

-   iptv-api:lite

docker pull guovern/iptv-api:lite

🚀 代理加速（推荐国内用户使用）：

docker pull docker.1ms.run/guovern/iptv-api:lite

#### 2\. 运行容器

-   iptv-api

docker run -d -p 8000:8000 guovern/iptv-api

-   iptv-api:lite

docker run -d -p 8000:8000 guovern/iptv-api:lite

##### 挂载（推荐）：

实现宿主机文件与容器文件同步，修改模板、配置、获取更新结果文件可直接在宿主机文件夹下操作

以宿主机路径/etc/docker 为例：

-   iptv-api

\-v /etc/docker/config:/iptv-api/config
-v /etc/docker/output:/iptv-api/output

-   iptv-api:lite

\-v /etc/docker/config:/iptv-api-lite/config
-v /etc/docker/output:/iptv-api-lite/output

##### 环境变量：

-   端口

\-e APP\_PORT=8000

-   定时执行时间

\-e UPDATE\_CRON1="0 22 \* \* \*"
-e UPDATE\_CRON2="0 10 \* \* \*"

#### 3\. 更新结果

-   接口地址：`ip:8000`
-   m3u 接口：`ip:8000/m3u`
-   txt 接口：`ip:8000/txt`
-   接口内容：`ip:8000/content`
-   测速日志：`ip:8000/log`

更新日志
----

更新日志

赞赏
--

开发维护不易，请我喝杯咖啡☕️吧~

支付宝

微信

关注
--

微信公众号搜索 Govin，或扫码，接收更新推送、学习更多使用技巧：

免责声明
----

本项目仅供学习交流用途，接口数据均来源于网络，如有侵权，请联系删除

许可证
---

MIT License © 2024-PRESENT Govin
