---
project: 7days-golang
stars: 15886
description: 7 days golang programs from scratch (web framework Gee, distributed cache GeeCache, object relational mapping ORM framework GeeORM, rpc framework GeeRPC etc)  7天用Go动手写/从零实现系列
url: https://github.com/geektutu/7days-golang
---

7 days golang programs from scratch
===================================

**README 中文版本**

7天用Go从零实现系列
-----------

7天能写什么呢？类似 gin 的 web 框架？类似 groupcache 的分布式缓存？或者一个简单的 Python 解释器？希望这个仓库能给你答案。

推荐先阅读 **Go 语言简明教程**，一篇文章了解Go的基本语法、并发编程，依赖管理等内容。

推荐 **Go 语言笔试面试题**，加深对 Go 语言的理解。

推荐 **Go 语言高性能编程**(项目地址)，写出高性能的 Go 代码。

期待关注我的「知乎专栏」和「微博」，查看最近的文章和动态。

### 7天用Go从零实现Web框架 - Gee

Gee 是一个模仿 gin 实现的 Web 框架，Go Gin简明教程可以快速入门。

-   第一天：前置知识(http.Handler接口) | Code
-   第二天：上下文设计(Context) | Code
-   第三天：Trie树路由(Router) | Code
-   第四天：分组控制(Group) | Code
-   第五天：中间件(Middleware) | Code
-   第六天：HTML模板(Template) | Code
-   第七天：错误恢复(Panic Recover) | Code

### 7天用Go从零实现分布式缓存 GeeCache

GeeCache 是一个模仿 groupcache 实现的分布式缓存系统

-   第一天：LRU 缓存淘汰策略 | Code
-   第二天：单机并发缓存 | Code
-   第三天：HTTP 服务端 | Code
-   第四天：一致性哈希(Hash) | Code
-   第五天：分布式节点 | Code
-   第六天：防止缓存击穿 | Code
-   第七天：使用 Protobuf 通信 | Code

### 7天用Go从零实现ORM框架 GeeORM

GeeORM 是一个模仿 gorm 和 xorm 的 ORM 框架

gorm 准备推出完全重写的 v2 版本(目前还在开发中)，相对 gorm-v1 来说，xorm 的设计更容易理解，所以 geeorm 接口设计上主要参考了 xorm，一些细节实现上参考了 gorm。

-   第一天：database/sql 基础 | Code
-   第二天：对象表结构映射 | Code
-   第三天：记录新增和查询 | Code
-   第四天：链式操作与更新删除 | Code
-   第五天：实现钩子(Hooks) | Code
-   第六天：支持事务(Transaction) | Code
-   第七天：数据库迁移(Migrate) | Code

### 7天用Go从零实现RPC框架 GeeRPC

GeeRPC 是一个基于 net/rpc 开发的 RPC 框架 GeeRPC 是基于 Go 语言标准库 `net/rpc` 实现的，添加了协议交换、服务注册与发现、负载均衡等功能，代码约 1k。

-   第一天 - 服务端与消息编码 | Code
-   第二天 - 支持并发与异步的客户端 | Code
-   第三天 - 服务注册(service register) | Code
-   第四天 - 超时处理(timeout) | Code
-   第五天 - 支持HTTP协议 | Code
-   第六天 - 负载均衡(load balance) | Code
-   第七天 - 服务发现与注册中心(registry) | Code

### WebAssembly 使用示例

具体的实践过程记录在 Go WebAssembly 简明教程。

-   示例一：Hello World | Code
-   示例二：注册函数 | Code
-   示例三：操作 DOM | Code
-   示例四：回调函数 | Code

What can be accomplished in 7 days? A gin-like web framework? A distributed cache like groupcache? Or a simple Python interpreter? Hope this repo can give you the answer.

Web Framework - Gee
-------------------

Gee is a gin\-like framework

-   Day 1 - http.Handler Interface Basic Code
-   Day 2 - Design a Flexiable Context Code
-   Day 3 - Router with Trie-Tree Algorithm Code
-   Day 4 - Group Control Code
-   Day 5 - Middleware Mechanism Code
-   Day 6 - Embeded Template Support Code
-   Day 7 - Panic Recover & Make it Robust Code

Distributed Cache - GeeCache
----------------------------

GeeCache is a groupcache\-like distributed cache

-   Day 1 - LRU (Least Recently Used) Caching Strategy Code
-   Day 2 - Single Machine Concurrent Cache Code
-   Day 3 - Launch a HTTP Server Code
-   Day 4 - Consistent Hash Algorithm Code
-   Day 5 - Communication between Distributed Nodes Code
-   Day 6 - Cache Breakdown & Single Flight | Code
-   Day 7 - Use Protobuf as RPC Data Exchange Type | Code

Object Relational Mapping - GeeORM
----------------------------------

GeeORM is a gorm\-like and xorm\-like object relational mapping library

Xorm's desgin is easier to understand than gorm-v1, so the main designs references xorm and some detailed implementions references gorm-v1.

-   Day 1 - database/sql Basic | Code
-   Day 2 - Object Schame Mapping | Code
-   Day 3 - Insert and Query | Code
-   Day 4 - Chain, Delete and Update | Code
-   Day 5 - Support Hooks | Code
-   Day 6 - Support Transaction | Code
-   Day 7 - Migrate Database | Code

RPC Framework - GeeRPC
----------------------

GeeRPC is a net/rpc\-like RPC framework

Based on golang standard library `net/rpc`, GeeRPC implements more features. eg, protocol exchange, service registration and discovery, load balance, etc.

-   Day 1 - Server Message Codec | Code
-   Day 2 - Concurrent Client | Code
-   Day 3 - Service Register | Code
-   Day 4 - Timeout Processing | Code
-   Day 5 - Support HTTP Protocol | Code
-   Day 6 - Load Balance | Code
-   Day 7 - Discovery and Registry | Code

Golang WebAssembly Demo
-----------------------

-   Demo 1 - Hello World Code
-   Demo 2 - Register Functions Code
-   Demo 3 - Manipulate DOM Code
-   Demo 4 - Callback Code
