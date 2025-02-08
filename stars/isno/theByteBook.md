---
project: theByteBook
stars: 7878
description: ⭐ 【开源书籍】深入讲解内核网络、Kubernetes、ServiceMesh、容器等云原生相关技术。经历实践检验的 DevOps、SRE指南。如发现错误，谢谢提issue
url: https://github.com/isno/theByteBook
---

深入架构原理与实践
=========

这是什么？
-----

这是一本关于架构设计的开源书籍，已经完稿。如果阅读文章发现问题，欢迎在 github 给我提交 PR 或者 issue。

以下为我的公众号，欢迎与我讨论技术。

⭐️ 为什么要写这个？
-----------

这几年互联网基础设施技术出现了很大的更新迭代，比如容器技术（Container、Kubernetes）、服务网格（ServiceMesh）、无服务器（Serverless）、高性能网络（DPDK、XDP、RDMA）等等，我对这些技术有一些浅薄的见解和实践，但远没达到深刻理解的境界，我尝试使用 `费曼学习法` 把这些东西体系化地总结输出。一方面加深自我的学习认知，另一方面也希望这些输出对其他人有所帮助。

整个系列的内容主要集中在 `网络`、`集群以及服务治理`、`FinOps` 这三个主题，这也代表着基础架构的几个核心：稳定、效率、成本。

我会持续更新这个仓库的内容，如果想要关注可以点 `star` 。

:::center

https://github.com/isno/theByteBook

:::

如何阅读
----

-   **在线阅读**：本文档在线阅读地址为：https://www.thebyte.com.cn 【为防止缓存，阅读前请先强制刷新】
    
-   **离线阅读**：
    
    -   部署离线站点：文档基于 VuePress 2 构建，如你希望在本地搭建文档站点，请使用如下命令：
        
        # 克隆获取源码
        $ git clone https://github.com/isno/theByteBook.git && cd theByteBook
        
        # 安装工程依赖
        $ npm install
        
        # 运行网站，地址默认为 http://localhost:8080
        $ npm run dev
        

©️ 转载
-----

  
本作品由 isno 创作，采用知识共享署名 4.0 国际许可协议进行许可。
