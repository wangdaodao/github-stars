---
project: YApi-X
stars: 301
description: YApi 改。
url: https://github.com/fjc0k/YApi-X
---

YApi-X
======

`YApi-X` 基于 `YApi v1.8.8` 开发，相较原版，有以下改动：

-   接口路径支持更多字符，可以将 `@`、`#`、`;` 等字符用于接口路径定义；
-   支持复制分类；
-   新增 `adminPassword` 配置项以设置管理员密码；
-   项目图标支持自传图片；
-   接口运行支持上传文件（需安装插件 →）；
-   请求参数设置下的 Headers 支持批量添加；
-   支持 webdav 扩展的 HTTP 请求方法 PROPFIND, PROPPATCH, MKCOL, COPY, MOVE, LOCK, UNLOCK（了解更多 →）；
-   支持为路径参数、查询参数设置类型。

* * *

-   如何安装
    -   YApi-X 镜像
    -   通过 Docker Compose 安装
        -   运行
        -   重启
        -   升级
        -   迁移
        -   日志
-   如何配置
    -   基础配置
    -   数据库配置
    -   邮件配置
    -   LDAP 登录配置
    -   插件配置

如何安装
----

为了节省各自的时间，推荐你使用 **Docker** 安装，同时本文档也不会介绍其他安装方式。

### YApi-X 镜像

-   Docker Hub: https://hub.docker.com/r/jayfong/yapi-x/tags

### 通过 Docker Compose 安装

以下是一个示例：

version: '3'

services:
  yapi-web:
    image: jayfong/yapi-x:latest
    container\_name: yapi-web
    ports:
      - 40001:3000
    environment:
      - YAPI\_ADMIN\_ACCOUNT=admin@docker.yapi
      - YAPI\_ADMIN\_PASSWORD=adm1n
      - YAPI\_CLOSE\_REGISTER=true
      - YAPI\_DB\_SERVERNAME=yapi-mongo
      - YAPI\_DB\_PORT=27017
      - YAPI\_DB\_DATABASE=yapi
      - YAPI\_MAIL\_ENABLE=false
      - YAPI\_LDAP\_LOGIN\_ENABLE=false
      - YAPI\_PLUGINS=\[\]
    depends\_on:
      - yapi-mongo
    links:
      - yapi-mongo
    restart: unless-stopped
  yapi-mongo:
    image: mongo:latest
    container\_name: yapi-mongo
    volumes:
      - ./data/db:/data/db
    expose:
      - 27017
    restart: unless-stopped

#### 运行

将上面的示例复制粘贴下来命名为 `docker-compose.yml`，使用以下命令运行：

docker-compose up -d

然后，通过 `http://localhost:40001` 即可访问 `YApi-X`。

#### 重启

若你修改了配置，务必重启应用才能生效：

docker-compose restart yapi-web

#### 升级

`YApi-X` 一旦有更新，你可通过以下命令升级：

docker-compose pull yapi-web \\
  && docker-compose down \\
  && docker-compose up -d

> 升级不会对原有数据造成任何影响！

#### 迁移

直接打包整个目录去新的服务器即可。

#### 日志

如果出现意外情况，你可通过以下命令查看运行日志：

docker-compose logs yapi-web

如何配置
----

你可通过环境变量进行配置。

### 基础配置

环境变量名称

类型

说明

示例

YAPI\_ADMIN\_ACCOUNT

string

管理员账号（邮箱）

admin@foo.bar

YAPI\_ADMIN\_PASSWORD

string

管理员密码

adm1n

YAPI\_CLOSE\_REGISTER

boolean

是否关闭注册

true

### 数据库配置

环境变量名称

类型

说明

示例

YAPI\_DB\_SERVERNAME

string

MongoDB 服务地址

yapi-mongo

YAPI\_DB\_PORT

number

MongoDB 服务端口

27017

YAPI\_DB\_DATABASE

string

使用的 MongoDB 数据库

yapi

YAPI\_DB\_USER

string

登录 MongoDB 服务的用户名

root

YAPI\_DB\_PASS

string

登录 MongoDB 服务的用户密码

r00t

YAPI\_DB\_AUTH\_SOURCE

string

MongoDB 身份认证所用库

admin

YAPI\_DB\_CONNECT\_STRING

string

使用 MongoDB 集群时配置

mongodb://127.0.0.100:8418,127.0.0.101:8418/yapidb?slaveOk=true

YAPI\_DB\_OPTIONS

json

Mongoose 连接 MongoDB 服务时的额外选项，一般不用设置。请参考: Mongoose.prototype.connect()

{}

### 邮件配置

环境变量名称

类型

说明

示例

YAPI\_MAIL\_ENABLE

boolean

是否启用

true

YAPI\_MAIL\_HOST

string

邮件服务地址

smtp.163.com

YAPI\_MAIL\_PORT

number

邮件服务端口

465

YAPI\_MAIL\_FROM

string

发送人邮箱

foo@163.com

YAPI\_MAIL\_AUTH\_USER

string

登录邮件服务的用户名

bar@163.com

YAPI\_MAIL\_AUTH\_PASS

string

登录邮件服务的用户密码

f00bar

YAPI\_MAIL\_OPTIONS

json

传递给 Nodemailer 的额外选项，一般不用设置。请参考：Nodemailer > SMTP transport

{"tls":{"rejectUnauthorized":false}}

### LDAP 登录配置

环境变量名称

类型

说明

示例

YAPI\_LDAP\_LOGIN\_ENABLE

boolean

是否启用

true

YAPI\_LDAP\_LOGIN\_SERVER

string

LDAP 服务地址

ldap://ldap.foo.bar

YAPI\_LDAP\_LOGIN\_BASE\_DN

string

登录 LDAP 服务的用户名

cn=admin,dc=foo,dc=bar

YAPI\_LDAP\_LOGIN\_BIND\_PASSWORD

string

登录 LDAP 服务的用户密码

f00bar

YAPI\_LDAP\_LOGIN\_SEARCH\_DN

string

查询用户数据的路径

ou=users,dc=foo,dc=bar

YAPI\_LDAP\_LOGIN\_SEARCH\_STANDARD

string

支持两种值：  
1、前端登录账号对应的查询字段，如：`mail`、`uid` 等；  
2、自定义查询条件，其中 `%s` 会被前端登录账号替换，如：`&(objectClass=user)(cn=%s)`

\-

YAPI\_LDAP\_LOGIN\_EMAIL\_POSTFIX

string

登录邮箱后缀

@163.com

YAPI\_LDAP\_LOGIN\_EMAIL\_KEY

string

LDAP 数据库存储用户邮箱的字段

mail

YAPI\_LDAP\_LOGIN\_USERNAME\_KEY

string

LDAP 数据库存储用户名的字段

name

### 插件配置

环境变量名称

类型

说明

示例

YAPI\_PLUGINS

json

要使用的插件列表。点击查看开源 YApi 插件列表 →  
**配置项数据格式：**  
{  
    "name": "插件名称",  
    "options": "插件配置"  
}  
**注意：**  
安装插件会运行 YApi 自带的打包命令，其内存消耗较大，因此，在安装插件时，物理机可用内存最好大于 `1GB`，否则，易出现内存溢出错误，导致插件安装失败。

\[{"name":"add-user"},{"name":"gitlab","options":{}}\]
