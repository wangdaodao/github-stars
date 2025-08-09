---
project: iptv-api
stars: 17075
description: 📺IPTV电视直播源更新项目『✨秒播级体验🚀』：支持自定义频道与EPG；支持多种源获取方式；支持RTMP推流；支持IPv4/IPv6；支持获取归属地与运营商；每天自动更新两次，结果可用于TVBox等播放软件；支持工作流、Docker(amd64/arm64/arm v7)、命令行、GUI运行方式 | IPTV live TV source update project
url: https://github.com/Guovin/iptv-api
---

IPTV-API
========

一个可高度自定义的IPTV接口更新项目📺，自定义频道菜单，自动获取直播源，测速验效后生成可用的结果，可实现『✨秒播级体验🚀』

  

English | 中文

🎉💻 IPTV-Web：IPTV电视直播源管理平台，支持在线播放等功能，开发中...

💖 频道别名收集计划

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
-   👀 关注公众号
-   ⭐️ Star统计
-   📣 免责声明
-   ⚖️ 许可证

Important

1.  默认数据源，如订阅源，来源于Github开源项目，仅供示例作用，可能出现稳定性问题
2.  本项目不提供对接口结果稳定性的保证与解释
3.  若要实现最佳的稳定性，建议自行维护数据源

默认数据源

📍订阅源来自：

-   Guovin/iptv-database
-   iptv-org/iptv
-   suxuang/myIPTV
-   kimwang1978/collect-tv-txt
-   asdjkl6/tv
-   fanmingming/live
-   vbskycn/iptv

📍频道图标来自：

-   fanmingming/live

特点
--

-   ✅ 自定义模板，支持别名，生成您想要的频道
-   ✅ 支持RTMP推流(live/hls)，提升播放体验
-   ✅ 支持多种获取源方式：本地源、组播源、酒店源、订阅源、关键字搜索
-   ✅ 支持回放类接口获取与生成
-   ✅ 支持EPG功能，显示频道预告内容
-   ✅ 接口测速验效，获取延迟、速率、分辨率，过滤无效接口
-   ✅ 偏好设置：IPv4、IPv6、接口来源排序优先级与数量配置、白名单、黑名单、归属地与运营商过滤
-   ✅ 定时执行，北京时间每日 6:00 与 18:00 执行更新
-   ✅ 支持多种运行方式：工作流、命令行、GUI 软件、Docker(amd64/arm64/arm v7)
-   ✨ 更多功能请见配置参数

最新结果
----

Important

以下地址国内可能无法稳定访问，推荐在前拼接代理地址使用，公众号可回复`cdn`获取

### 直播源

-   默认

https://raw.githubusercontent.com/Guovin/iptv-api/gd/output/result.m3u

-   IPv6

https://raw.githubusercontent.com/Guovin/iptv-api/gd/output/ipv6/result.m3u

-   IPv4

https://raw.githubusercontent.com/Guovin/iptv-api/gd/output/ipv4/result.m3u

### 点播源

https://raw.githubusercontent.com/Guovin/iptv-api/gd/source.json

配置
--

配置项

描述

默认值

open\_driver

开启浏览器运行，若更新无数据可开启此模式，较消耗性能

False

open\_epg

开启EPG功能，支持频道显示预告内容

True

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

False

open\_hotel\_foodie

开启 Foodie 酒店源工作模式

True

open\_hotel\_fofa

开启 FOFA、ZoomEye 酒店源工作模式

False

open\_local

开启本地源功能，将使用模板文件与本地源文件中的数据

True

open\_m3u\_result

开启转换生成 m3u 文件类型结果链接，支持显示频道图标

True

open\_multicast

开启组播源功能，关闭后所有组播源工作模式都将关闭

False

open\_multicast\_foodie

开启 Foodie 组播源工作模式

True

open\_multicast\_fofa

开启 FOFA 组播源工作模式

False

open\_online\_search

开启关键字搜索源功能

False

open\_request

开启查询请求，数据来源于网络（仅针对酒店源与组播源）

False

open\_rtmp

开启RTMP推流功能，需要安装FFmpeg，利用本地带宽提升接口播放体验

False

open\_service

开启页面服务，用于控制是否启动结果页面服务；如果使用青龙等平台部署，有专门设定的定时任务，需要更新完成后停止运行，可以关闭该功能

True

open\_speed\_test

开启测速功能，获取响应时间、速率、分辨率

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

open\_headers

开启使用M3U内含的请求头验证信息，用于测速等操作，注意：只有个别播放器支持播放这类含验证信息的接口，默认为关闭

False

app\_port

页面服务端口，用于控制页面服务的端口号

8000

cdn\_url

CDN代理加速地址，用于订阅源、频道图标等资源的加速访问

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

isp

接口运营商，用于控制结果中只包含填写的运营商类型，支持关键字过滤，英文逗号分隔，不填写表示不指定运营商

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

location

接口归属地，用于控制结果只包含填写的归属地类型，支持关键字过滤，英文逗号分隔，不填写表示不指定归属地，建议使用靠近使用者的归属地，能提升播放体验

local\_file

本地源文件路径

config/local.txt

local\_num

结果中偏好的本地源接口数量

10

min\_resolution

接口最小分辨率，需要开启 open\_filter\_resolution 才能生效

1920x1080

max\_resolution

接口最大分辨率，需要开启 open\_filter\_resolution 才能生效

1920x1080

min\_speed

接口最小速率（单位M/s），需要开启 open\_filter\_speed 才能生效

0.5

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

speed\_test\_limit

同时执行测速的接口数量，用于控制测速阶段的并发数量，数值越大测速所需时间越短，负载较高，结果可能不准确；数值越小测速所需时间越长，低负载，结果较准确；调整此值能优化更新时间

10

speed\_test\_timeout

单个接口测速超时时长，单位秒(s)；数值越大测速所需时间越长，能提高获取接口数量，但质量会有所下降；数值越小测速所需时间越短，能获取低延时的接口，质量较好；调整此值能优化更新时间

10

speed\_test\_filter\_host

测速阶段使用Host地址进行过滤，相同Host地址的频道将共用测速数据，开启后可大幅减少测速所需时间，但可能会导致测速结果不准确

False

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

update\_interval

定时执行更新时间间隔，单位小时，设置0或空则只运行一次，不作用于工作流

12

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

1.  下载IPTV-API 更新软件，打开软件，点击启动，即可进行更新
    
2.  或者在项目目录下运行以下命令，即可打开 GUI 软件：
    

pipenv run ui

### Docker

#### 1\. 拉取镜像

docker pull guovern/iptv-api:latest

🚀 代理加速（推荐国内用户使用）：

docker pull docker.1ms.run/guovern/iptv-api:latest

#### 2\. 运行容器

docker run -d -p 8000:8000 guovern/iptv-api

##### 挂载（推荐）：

实现宿主机文件与容器文件同步，修改模板、配置、获取更新结果文件可直接在宿主机文件夹下操作

以宿主机路径/etc/docker 为例：

\-v /etc/docker/config:/iptv-api/config
-v /etc/docker/output:/iptv-api/output

##### 环境变量：

变量

描述

默认值

APP\_HOST

服务host地址，可修改使用公网域名

"http://localhost"

APP\_PORT

服务端口

8000

#### 3\. 更新结果

接口

描述

/

默认接口

/m3u

m3u 格式接口

/txt

txt 格式接口

/ipv4

ipv4 默认接口

/ipv6

ipv6 默认接口

/ipv4/txt

ipv4 txt接口

/ipv6/txt

ipv6 txt接口

/ipv4/m3u

ipv4 m3u接口

/ipv6/m3u

ipv6 m3u接口

/content

接口文本内容

/log

测速日志

-   RTMP 推流：

Note

1.  如果需要对本地视频源进行推流，可在`config`目录下新建`live`或`hls`（推荐）文件夹
2.  live文件夹用于推流live接口，hls文件夹用于推流hls接口
3.  将以`频道名称命名`的视频文件放入其中，程序会自动推流到对应的频道中
4.  可访问 http://localhost:8080/stat 查看实时推流状态统计数据

推流接口

描述

/live

推流live接口

/hls

推流hls接口

/live/txt

推流live txt接口

/hls/txt

推流hls txt接口

/live/m3u

推流live m3u接口

/hls/m3u

推流hls m3u接口

/live/ipv4/txt

推流live ipv4 txt接口

/hls/ipv4/txt

推流hls ipv4 txt接口

/live/ipv4/m3u

推流live ipv4 m3u接口

/hls/ipv4/m3u

推流hls ipv4 m3u接口

/live/ipv6/txt

推流live ipv6 txt接口

/hls/ipv6/txt

推流hls ipv6 txt接口

/live/ipv6/m3u

推流live ipv6 m3u接口

/hls/ipv6/m3u

推流hls ipv6 m3u接口

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

Star统计
------

免责声明
----

本项目仅供学习交流用途，接口数据均来源于网络，如有侵权，请联系删除

许可证
---

MIT License © 2024-PRESENT Govin
