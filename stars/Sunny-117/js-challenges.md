---
project: js-challenges
stars: 2170
description: ✨✨✨ Challenge your JavaScript programming limits step by step 前端手写题，一步步提升 JavaScript 编程水平
url: https://github.com/Sunny-117/js-challenges
---

Welcome to js-challenges 👋
===========================

> 集锦大厂面试常考的 前端手写题和 leetcode 算法题

### 🏠 DOCS

Author
------

👤 **sunny-117**

-   Website: https://sunny-117.github.io/blog/
-   Twitter: @zhiqiangfu6sun
-   Github: @sunny-117
-   personal share: 个人分享

Project Status
--------------

Star History
------------

CONTENT
=======

前端手写题集锦 记录大厂**笔试，面试常考**手写题，2024 年前端面试中常见的 leetcode 算法题, 致力打造最全的前端 JavaScript 手写题题库和答案的最优解

> 题目来源：总结了牛客截止到 2024 年 7 月的所有大厂手写题\[100%\]，掘金部分出名的手写题文章，备战前端春招，秋招好友的总结好的题目(github), 就不一一列举链接啦，总之此项目题目来源于社区，答案也由社区讨论后 merge，也完全服务于社区。

谢谢您的 star，您的 star 是我更新的动力 🥳

**里面有答案，为了让你们有一个参考，不过非常希望你们能提供自己的思路，指出答案中存在的问题，复杂度优化等等， 期待你们的 contribute, 想来一起维护这个项目，可以联系我，成为 contributor**

最后我把社区的好的答案汇总到一个目录下，答案专栏，方便刷题

主要是让大家讨论出最优解，然后 merge，一起贡献这个项目，有些答案有点问题，所以我给出的答案仅作参考，也欢迎发现的小伙伴提 PR

🤝 Contributing
---------------

Contributions, issues and feature requests are welcome!  
Feel free to check issues page. You can also take a look at the contributing guide.

Thank you to all the people who already contributed to js-challenges!

前端 JavaScript 手写题
=================

JavaScript HOT 100 题
--------------------

> 中大厂面试，最常考的 100 个题，每一题都非常具有代表性，想要准备面试突击的同学，优先看这些题，祝在座的每一位都能拿到满意的 offer

-   实现 Promise.all
-   JSON2DOM = react 的 render 函数
-   树形结构转成列表
-   列表转成树形结构
-   Array.prototype.flat
-   instanceof
-   call apply bind
-   Array.prototype.map
-   正则表达式模版字符串
-   lodash.get
-   深拷贝
-   寄生组合式继承
-   发布订阅者模式
-   岛屿数量
-   实现有并行限制的 Promise 调度器
-   实现一个 LazyMan

实现 Promise （hot）
----------------

-   完整实现 Promise A+
-   实现 Promise.all
-   实现 Promise.prototype.finally
-   实现 Promise.allSettled
-   实现 Promise.race
-   实现 Promise.prototype.catch
-   Promise.resolve
-   Promise.reject

Promise 周边场景题（hot）
------------------

-   交通灯
-   封装异步的 fetch，使用 async await 方式来使用
-   repeat(console.log, 5, 1000)
-   封装一个工具函数输入一个 promiseA 返回一个 promiseB 如果超过 1s 没返回则抛出异常如果正常则输出正确的值
-   请求 5s 未完成就终止
-   实现一个 sleep 函数
-   js 每隔一秒打印 1,2,3,4,5
-   使用 setTimeout 实现 setInterval
-   promise 实现图片异步加载
-   使用 Promise 封装 AJAX 请求
-   我们能反过来使用 setinterval 模拟实现 settimeout 吗？
-   异步任务：依次发送 3 次网络请求，拿到服务器数据
-   实现网络请求超时判断，超过三秒视为超时
-   promise 中断请求
-   给定一系列的 api，测量上传速度（实现的时候用的 GET 请求）并选择一个加载时间最短的 api
-   settimeout 系统补偿时间
-   setTimeout 准时
-   请求五秒未完成则终止
-   并发多个请求，返回先得到 response 的。函数输入为 url 数组，输出为第一个返回的 response 的结果
-   JS 异步数据流，实现并发异步请求，结果顺序输出
-   Promise 串行
-   处理高并发, 100 条数据，带宽为 10， 跑满带宽
-   设计一个简单的任务队列, 要求分别在 1,3,4 秒后打印出 "1", "2", "3"；
-   实现有并行限制的 Promise 调度器
-   实现 Scheduler
-   有并发限制的 Promise.all(ts 类型)
-   实现 如果上一次的没请求完，之后的就无响应
-   使用 Promise 实现每隔三秒输出时间
-   使用 Promise 改写回调地狱
-   设计一个函数，该函数的参数为可同时发送请求的大小，返回一个函数，该函数的参数为要请求的 url。 实现的效果为，同时发送 n 个请求，当有请求返回后往请求队列里 push 新的请求，并输出刚刚结束的请求的返回值
-   Promise.retry 超时重新请求，并在重试一定次数依然失败时输出缓存内容
-   写一个 mySetInterVal(fn, a, b)，每次间隔 a,a+b,a+2b 的时间，然后写一个 myClear，停止上面的 mySetInterVal

JavaScript 常考手写题
----------------

-   产生一个不重复的随机数组
-   await async 如何实现
-   使用递归完成 1 到 100 的累加
-   打印出 1~10000 以内的对称数
-   实现一个字符串匹配算法 indexOf
-   请实现一个模块 math，支持链式调用 math.add(2,4).minus(3).times(2);
-   手写用 ES6proxy 如何实现 arr\[-1\] 的访问（滴滴 2020）
-   有一堆整数，请把他们分成三份，确保每一份和尽量相等（11，42，23，4，5，6 4 5 6 11 23 42 56 78 90）
-   之字形打印矩阵
-   数组中的最大值
-   尾递归（斐波那契数列
-   实现简单路由
-   封装一个 localstorage 的 setItem 和 getItem 方法
-   1-1000 回文数
-   随机生成字符串
-   判断一个字符串是否为驼峰字符串， judge('ByteDance','BD') -> true judge('Bytedance','BD') -> false
-   压缩字符串
-   Map 场景题
-   输入 50a6we8y20x 输出 50 个 a，6 个 we，8 个 y，20 个 x
-   手写 defineProperty
-   String string 值一样返回 true Object Object 返回 true function function 都是声明的一个新的变量 返回 false
-   对输入的字符串：去除其中的字符'b'；去除相邻的'a'和'c'
-   用一行代码，将数组中的字符串和字符串对象(new String(123))直接判定出来
-   before
-   实现一下 console.log
-   实现(5).add(3).minus(2)功能
-   将十进制数字转为二进制数字字符串
-   封装 remove child.remove()销毁自身
-   字符串中字母的出现次数
-   输出一个等腰三角形
-   实现一个函数 a，使其奇数次调用时返回 1，偶数次调用时返回 2（不能使用全局变量）
-   求 最接近的值
-   不用循环求和
-   连续赋值操作
-   输入一串字符串，根据字符串求出每个字母的数量并返回结果对象。（数字为 1 时可省略
-   创建包含 10 个 1 的数组 多种方法
-   \['zm', 'za', 'b', 'lm', 'ln', 'k'\]
-   \["0->2", "4->5", "7", "13", "15->16"\]
-   \['ab', 'c', 'ab', 'd', 'c'\] => \['ab1', 'c1' ,'ab2', 'd', 'c2'\]
-   移除空属性
-   判断两个对象是否相等
-   一个数组，找出每个数组元素右侧第一个比当前数大的数的下标，时间复杂度 O(N)
-   寻找出现次数最多的三个标签
-   素数
-   实现日期格式化函数
-   实现 jsonp
-   URL 反转
-   解析 URL Params 为对象
-   调用计数器（支持重置）
-   颜色生成
-   JavaScript 怎么清空数组
-   判断 A、B 数组的包含关系（值和数量），A 属于 B 返回 1，B 属于 A 返回 2，两者相等返回 0，其他返回-1
-   对象的合并
-   实现一个 无限延伸数组)
-   多行字符串转二维数组
-   请实现一个通用的 Array 解构赋值
-   数组合并
-   数组交集，并集，差集
-   多维数组全排列
-   判断对象是否存在循环引用
-   实现函数 solution(arr, k)
-   逆对象扁平
-   对象扁平化
-   实现 执行一次的函数
-   链式调用
-   偏函数
-   实现管道函数
-   手写事件代理（委托）
-   数据类型判断
-   类数组转数组
-   预加载
-   图片懒加载
-   数组去重
-   防抖 节流
-   函数组合 compose redux-saga koa 洋葱模型
-   sum(x,y)和 sum(x)(y)
-   curry 柯里化
-   实现 xxx 时间之前的函数
-   n 个 2 的 n 次方之和
-   无限动画
-   瀑布流
-   匹配 "a\*c", "abcaacc"
-   一个字符串中是否出现某串字符,出现的话返回索引
-   实现一个属性选择器
-   字符串转数字
-   实现一个跨浏览器事件工具
-   12 调用计数器（支持重置）
-   实现内存函数缓存函数调用结果
-   返回给定七个扑克牌是否有同花顺，数据结构 \[{num: 1, hua: 's'}, ...\]
-   JS 定义一个 log 方法
-   阿拉伯数字专汉字(偏难)
-   用代码实现把字符串转换成 base64 编码
-   设计 LRU 缓存结构
-   实现一个 LazyMan
-   标签整理分类题
-   求集合单词组合起来的不同结果，集合中的单词不重复，每个结果包含所有单词
-   实现简易版的useState
-   数组乱序-百度实习
-   排序找第几个最大-快手实习
-   怎么在制定数据源里面生成一个长度为 n 的不重复随机数组 能有几种方法 时间复杂度多少（字节）

ts 类型体操
-------

-   myPick
-   myReadonly
-   deepReadonly
-   tuple to object
-   first of Array
-   tuple of Length
-   myExclude
-   awaited
-   if
-   concat
-   includes
-   Trim
-   push
-   unshift
-   parameters
-   returnType
-   myReadonly2
-   Omit

设计模式相关
------

-   单例模式
-   命令模式
-   策略模式
-   观察者模式
-   发布订阅者模式
-   工厂模式
-   代理模式
-   装饰器模式

树-场景题（hot）
----------

-   DOM2JSON
-   JSON2DOM = react 的 render 函数
-   计算目录树的深度
-   树形结构获取路径名
-   树形结构转成列表
-   列表转成树形结构
-   对象树遍历
-   获取树对象属性
-   查找 json 中的 children 路径
-   对象字符串转化成树形结构
-   判断有无符合路径和 -> 打印所有路径
-   获取树结构中的 name：getName

实现 JS 原生方法
----------

-   Array.prototype.flat
-   Array.prototype.forEach
-   Array.prototype.map
-   Array.prototype.filter
-   Array.prototype.reduce
-   Array.prototype.fill
-   Array.prototype.includes
-   Array.prototype.push
-   Array.prototype.unshift
-   Array.prototype.copy
-   Array.prototype.getLevel
-   Array.prototype.interator
-   Array.prototype.sort
-   实现 es6 的 set 集合
-   实现 es6 的 map 集合
-   String.prototype.zpadStart
-   Object.assign
-   Object.is
-   JSON.stringify
-   JSON.parse
-   call apply bind
-   typeof
-   instanceof
-   trim
-   实现 new
-   String.prototype.repeat
-   String.prototype.includes

JS 库函数实现
--------

-   lodash.get
-   lodash.chunk
-   lodash.once
-   classnames

js utils
--------

-   判断一个对象是否是 isPlainObject

手写 nodejs 模块
------------

-   promisify

正则相关
----

-   正则表达式模版字符串
-   正则判断手机号，qq，颜色，邮箱
-   字符串的大小写取反
-   检验字符串首尾是否含有数字
-   去除字符串空格
-   去除字符串中的字母
-   正则：短横线 => 驼峰
-   正则：驼峰 => 短横线
-   对象 key 的驼峰转下划线
-   判断字符串中是否存在连续的三个数
-   ((2+3)+(3\*4))+2---->\['(2 + 3)+(3 \* 4)', '2 + 3', '3 \* 4'\]

排序算法
----

-   冒泡排序
-   选择排序
-   快速排序
-   插入排序
-   归并排序
-   基数排序
-   计数排序
-   希尔排序
-   桶排序
-   堆排序

实现自定义 HOOK
----------

-   Hooks 怎么封装手势逻辑
-   Hooks 实现移动端的滑动轮播插件
-   如何用 Hooks 模拟 componentDidMount 与 componentWillUnmount
-   实现一个 useBodyScrollLock ，当出现弹窗时 阻止背景滚动
-   ts 实现 hooks: useInterval
-   实现 useQuery
-   实现 useRequest
-   实现 usePosition
-   实现 useStorage
-   实现 防抖收藏 useFavorite

组件设计题（Vue/React/JS 均可）
----------------------

-   全选
-   轮播图
-   根据 response 渲染 table
-   歌词滚动功能(hot)
-   实现一个 百度搜索框 （搜索提示）
-   实现 todos
-   计时器或倒计时组件
-   设计一个公会入驻信息提交页
-   编码实现宽高不相同图片的自适配排列
-   列表子元素顺序反转
-   遍历树组件
-   选项卡
-   拖拽
-   原创组件设计题：互斥级联表单组件

Vue 原理题
-------

-   手写 v-model 简易版
-   手写 vue2 响应式
-   手写 vue3 proxy 实现数据响应式
-   手写 v-bind 简易版
-   手写 v-html 和 v-text

HTML CSS 手写题
------------

-   实现圆形环状进度条
-   等边三角形
-   实现 扇形
-   实现平行四边形
-   实现 九宫格
-   实现一个秒针绕一点转动的效果
-   实现一个 球 字节
-   圆弧旋转
-   使用 div 和 css 实现一个圆形，红色部分站 60%，绿色 40%
-   现在有一个进度条，进度条中间有一串文字，当我的进度条覆盖了文字之后，文字要去进度条反色，怎么实现？
-   shadowDOM 实现 css 隔离
-   两栏布局
-   宽高自适应正方形
-   1px 问题
-   实现 筛子
-   css3 实现多行文字截断处理
-   三栏布局移动优先设计
-   css 实现一个自适应搜索框
-   css 书卡布局
-   实现宽高比例固定的 div
-   实现一个五点骰子
-   实现圣杯布局
-   黑白主题切换

JS 实现基本数据结构
-----------

-   队列结构
-   哈希表
-   实现集合
-   用 Javascript 创建一个单链表
-   树结构
-   图结构
-   栈结构
-   js 实现 堆
-   实现 Trie (前缀树)
-   top K

系统设计（场景）题
---------

-   原创-实现缓存类 TipCache设计
-   百度社招：实现一个Observable

其他
--

-   tools-js

前端常考 leetcode 算法题
=================

前端 HOT 100 题
------------

> 所有题目的名称都对应 leetcode，可以自行搜索，完成题目后欢迎把答案贡献给 issue 评论区，大家讨论最优解后 merge 到答案文档区

矩阵相关
----

-   螺旋矩阵
-   旋转矩阵
-   旋转图像
-   岛屿数量
-   矩形重叠
-   矩阵乘法

数组
--

-   把数组排成最小的数
-   买卖股票的最佳时机
-   最长递增子序列

链表
--

-   删除排序链表中的重复元素
-   反转链表
-   反转链表 II
-   环形链表
-   环形链表 II
-   合并两个有序链表
-   链表中倒数第 k 个节点
-   两两交换链表中的节点
-   相交链表
-   K 个一组翻转链表
-   删除链表的倒数第 N 个结点
-   链表的中间结点

二叉树
---

-   路径总和
-   路径总和 II
-   二叉树的所有路径
-   二叉树的层序遍历
-   二叉树的锯齿形层序遍历
-   N 叉树的层序遍历
-   二叉树的最大深度
-   二叉树的前序遍历
-   二叉树的完全性检验
-   序列化二叉树
-   二叉树的最近公共祖先
-   翻转二叉树
-   从中序与后序遍历序列构造二叉树
-   相同的树
-   对称二叉树

子序列问题
-----

-   最长递增子序列
-   最长连续递增序列
-   最长重复子数组
-   最长公共子序列
-   判断子序列
-   不相交的线
-   编辑距离

回文专题
----

-   最长回文子串
-   最长回文子序列
-   回文数
-   验证回文串
-   验证回文字符串 Ⅱ
-   分割回文串（字节广告）

二分查找
----

-   搜索旋转排序数组
-   x 的平方根
-   第一个错误的版本
-   有序数组中的单一元素
-   旋转数组的最小数字
-   0 ～ n-1 中缺失的数字

滑动窗口
----

-   无重复字符的最长子串
-   字符串的排列
-   和为 s 的连续正数序列

双指针
---

-   盛最多水的容器
-   三数之和
-   最接近的三数之和
-   接雨水
-   字符串相乘
-   合并两个有序数组
-   移动零
-   字符串相加

单调队列
----

-   滑动窗口最大值
-   队列的最大值

单调栈
---

-   每日温度
-   下一个更大的元素 I
-   下一个更大的元素 II

位运算
---

-   只出现一次的数字
-   二进制中 1 的个数
-   数组中数字出现的次数
-   不用加减乘除做加法

动态规划
----

-   最大子数组和
-   最小路径和
-   不同路径
-   不同路径 II
-   爬楼梯
-   最长有效括号
-   零钱兑换

回溯
--

-   括号生成
-   电话号码的字母组合
-   全排列
-   全排列 II
-   N 皇后
-   N 皇后 II

字符串
---

-   最长公共前缀
-   罗马数字转整数
-   整数转罗马数字
-   找出字符串中第一个匹配项的下标
-   不同的子序列
-   最长重复子串

场景题
===

-   Markdown 文本解析

社区建议收集区：https://github.com/Sunny-117/js-challenges/discussions

关于捐赠
----

本项目会持续更新

整理不易，如果您觉得本项目对您有帮助，您可以通过支付宝或微信，扫描二维码，捐赠 X 元，^\_^，谢谢！

📝 License
----------

Copyright © 2022 sunny-117.  
This project is MIT licensed.

* * *

_This README was generated with ❤️ by readme-md-generator_
