---
project: WebViewTvLive
stars: 833
description: 使用 腾讯X5 WebView 开发的电视直播App
url: https://github.com/hxh19950701/WebViewTvLive
---

WebView 电视
==========

使用 腾讯X5 WebView 开发的电视直播App

原理：加载官方直播网页，查找网页中的视频元素，然后自动全屏。

  

功能
--

-   自动更新频道列表
-   多直播源
-   播放异常自动换源/刷新
-   应用自定义设置
-   适配手机、平板和电视
-   上下键换台反转

待开发的功能
------

-   数字键换台
-   自定义播放列表源
-   局域网远程设置
-   手势调节屏幕亮度和音量
-   适配回看功能
-   自主选择是否启用TBS内核

获取应用
----

-   GitHub  
    https://github.com/hxh19950701/WebViewTvLive/releases  
    
-   微信公众号  
    若您不方便访问 GitHub，也可关注微信公众号 “**网页电视**” 获取最新版下载链接。  
    
-   本项目的原始发布地址只有以上两个，其他渠道均为第三方转载发布，与作者无关！  
    

优势
--

-   直接使用官网直播链接，非常稳定可靠
-   兼容 m3u8 链接

缺点
--

-   比起直接加载直播源，载入频道稍长，需要等待一定时间
-   使用的是网页播放器播放，对设备性能有一定的要求
-   对低版本 Android 设备兼容性比较差，建议 Android 9 或以上的设备
-   无法选择视频清晰度，大部分为 720P，少部分为 1080P
-   官网直播，大部分为 24FPS，基本没有 50FPS

FAQ
---

**Q: 在我的电视机/盒子上无法自动全屏？**  
A: 一般是设备 WebView 的问题，待X5内核下载完成，重启 App 即可。若无法自动下载X5内核，请在设置-TBS调试界面内选择“安装线上内核”来手动安装。  
  
**Q: 访问央视网总提示“您当前的浏览器不支持视频播放，请升级浏览器或更换设备”？**  
A: 和上面是一样的问题，安装X5内核或者升级设备的WebView即可解决。  
  
**Q: 在TBS调试界面“安装线上内核”老是失败？**  
A: 可能刚好遇到了官方 X5 内核下载限流时间段，请换个时间段重试。参见《关于官网X5内核SDK加载不稳定问题说明》。  
  
**Q: 尝试了以上所有的办法，在我的设备上依然闪退/无法自动全屏？**  
A: 请去这里反馈。#34  
  
**Q: 有没有适配 Android 5.0 以下设备的打算？**  
A: 没有这个打算。这些设备的性能通常都不高，而且 WebView 版本也比较低，即便适配了，也无法使用。  
  
**Q: 我打开怎么只有 CCTV-1？**  
A: 频道列表托管在GitHub，出现此问题请检查您与Github之间的连接。  
最新的版本应该不会出现这样的问题了。如果是升级后出现的问题，试试清除应用数据。  

注意
--

-   请尊重作者，源码仅供您学习、交流使用。  
    
-   对于二次打包的应用，仅限自用，或者在注明原 App 名称的情况下适度分享。  
    
-   不要利用此项目牟利。  
    

其他说明
----

-   本项目中收录的官方直播地址均为网友自行收集，若不小心侵犯了版权方的权益，请联系作者删除。  
    

捐赠
--

如果项目对您有帮助，欢迎捐赠开发者。  
查看已捐赠名单
