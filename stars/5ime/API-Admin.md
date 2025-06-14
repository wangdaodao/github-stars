---
project: API-Admin
stars: 436
description: API 网站内容管理系统 内置 20+ API 接口
url: https://github.com/5ime/API-Admin
---

食用方法
====

此程序基于ThinkPHP5.1 PHP版本需`7.0-7.4`之间。

`Nginx`请设置如下`伪静态` `Apache`无需配置 运行目录`默认`即可

```
location / {
	if (!-e $request_filename){
		rewrite  ^(.*)$  /index.php?s=$1  last;   break;
	}
}
```

将程序上传至网站根目录,访问`域名/install`进行安装操作

操作指南请前往：https://github.com/5ime/API-Admin/wiki

Bug反馈请提交`Issues`

更新日志
====

-   2020-4-1 提交API-Admin beta版 新增`随机动漫图API`
-   2020-4-7 新增`抖音无水印解析API`,`IP签名图API`,`免KEY加群API`
-   2020-4-15 新增安装页面/优化部分代码 新增`网站ICO获取API`,`网站icp备案查询API`,`历史上的今天API`,`QQ头像获取API`,`QQ在线状态查询API`,`服务器信息获取API`,`网站标题获取API`,`爱站权重获取API`,`城市天气获取API`,`随机一言API`
-   2020-4-20 修复移动端菜单栏不显示/优化部分代码
-   2020-4-22 更新首页样式
-   2020-4-23 修复已知bug 新增`皮皮虾无水印解析API`，`每日Bing获取API`,`QQ短网址获取API`,`垃圾分类查询API`,`手机号归属地查询API`,`申通快递查询API`
-   2020-8-4 修复部分bug,**建议重新安装**
-   2020-8-21 修复已知bug 新增`蓝奏云直链获取API`，`火山小视频去水印API`,`360/搜狗/百度收录量查询API`,`短网址还原API`
-   2020-9-27 修复部分已知失效API 如有其他失效API请提交Issues
-   2021-1-29 优化部分代码，后台新增API总调用数统计、API搜索功能、API分类功能、程序更新检测功能、API列表分页...
-   开源了聚合短视频去水印解析API https://github.com/5ime/video\_spider
-   2021-8-22 修复几处错误
-   2022-1-6 大更新

免责声明
====

本仓库只为学习研究，如涉及侵犯个人或者团体利益，请与我取得联系，我将主动删除一切相关资料，谢谢！
