---
project: js-screen-shot
stars: 860
description: web端自定义截图插件(原生JS版)
url: https://github.com/likaia/js-screen-shot
---

js-web-screen-shot ·
====================

web端自定义截屏插件(原生JS版)，运行视频：实现web端自定义截屏功能 ,效果图如下：

写在前面
----

关于此插件的更多介绍以及实现原理请移步：

-   实现Web端自定义截屏
-   实现Web端自定义截屏(JS版)

> 注意⚠️：本文档并非最新的，最新文档请移步官网

插件安装
----

yarn add js-web-screen-shot

# or

npm install js-web-screen-shot --save

插件使用
----

由于插件采用原生js编写且不依赖任何第三方库，因此它可以在任意一台支持js的设备上运行。

> 注意⚠️： 如果需要使用插件的webrtc模式或者截图写入剪切板功能，需要你的网站运行在`https`环境或者`localhost`环境。当然，也可以通过修改浏览器设置的方式实现在所有环境下都能运行。步骤如下： 1.打开谷歌浏览器，在地址栏输入`chrome://flags/#unsafely-treat-insecure-origin-as-secure` 2.在打开的界面中：下拉框选择enabled，地址填写你的项目访问路径。

### import形式使用插件

-   在需要使用截屏插件的业务代码中导入插件

import ScreenShot from "js-web-screen-shot";

-   在业务代码中使用时实例化插件即可

new ScreenShot();

> ⚠️注意：实例化插件时一定要等dom加载完成，否则插件无法正常工作。

### cdn形式使用插件

-   将插件的`dist`文件夹复制到你的项目中
-   使用`script`标签引入dist目录下的`screenShotPlugin.umd.js`文件

<script src\="./screenShotPlugin.umd.js"\></script\>

-   在业务代码中使用时实例化插件即可

    // 截图确认按钮回调函数
    const callback \= ({base64, cutInfo})\=>{
      console.log(base64, cutInfo);
    }
    // 截图取消时的回调函数
    const closeFn \= ()\=>{
      console.log("截图窗口关闭");
    }
    new screenShotPlugin({enableWebRtc: true, completeCallback: callback,closeCallback: closeFn});

> ⚠️注意：实例化插件时一定要等dom加载完成，否则插件无法正常工作。

### electron环境下使用插件

由于electron环境下无法直接调用webrtc来获取屏幕流，因此需要调用者自己稍作处理，具体做法如下所示：

-   直接获取设备的窗口，主线程发送一个IPC消息handle

// electron主线程
import { desktopCapturer, webContents } from "electron";

// 修复electron18.0.0-beta.5 之后版本的BUG: 无法获取当前程序页面视频流
const selfWindws \= async () \=>
        await Promise.all(
                webContents
                        .getAllWebContents()
                        .filter(item \=> {
                          const win \= BrowserWindow.fromWebContents(item);
                          return win && win.isVisible();
                        })
                        .map(async item \=> {
                          const win \= BrowserWindow.fromWebContents(item);
                          const thumbnail \= await win?.capturePage();
                          // 当程序窗口打开DevTool的时候  也会计入
                          return {
                            name:
                                    win?.getTitle() + (item.devToolsWebContents \=== null ? "" : "-dev"), // 给dev窗口加上后缀
                            id: win?.getMediaSourceId(),
                            thumbnail,
                            display\_id: "",
                            appIcon: null
                          };
                        })
        );

// 获取设备窗口信息
ipcMain.handle("IPC消息名称", async (\_event, \_args) \=> {
  return \[
    ...(await desktopCapturer.getSources({ types: \["window", "screen"\] })),
    ...(await selfWindws())
  \];
});

-   渲染线程(前端)发送消息封装处理(相应写法自己调整)

// xxx.ts
export const getDesktopCapturerSource \= async () \=> {
  return await window.electron.ipcRenderer.invoke<Electron.DesktopCapturerSource\[\]\>("IPC消息名称", \[\]);
}

-   获取指定窗口的媒体流

// yyy.ts
export function getInitStream(source: any): Promise<MediaStream | null\> {
    return new Promise((resolve, \_reject) \=> {
        // 获取指定窗口的媒体流
        // 此处遵循的是webRTC的接口类型  暂时TS类型没有支持  只能断言成any
        (navigator.mediaDevices as any).getUserMedia({
            audio: false,
            video: {
                mandatory: {
                    chromeMediaSource: 'desktop',
                    chromeMediaSourceId: source.id
                },
            }
        }).then((stream: MediaStream) \=> {
            resolve(stream);
        }).catch((error: any) \=> {
            console.log(error);
            resolve(null);
        })
    });
}

-   前端调用设备窗口信息

import { getDesktopCapturerSource } from "xxx.ts";
import { getInitStream } from "yyy.ts";
import ScreenShot from "js-web-screen-shot";

export const doScreenShot \= async ()\=>{
  // 下面这两块自己考虑  
  const sources \= await getDesktopCapturerSource(); // 这里返回的是设备上的所有窗口信息
  // 这里可以对\`sources\`数组下面id进行判断  找到当前的electron窗口  这里为了简单直接拿了第一个
  const stream \= await getInitStream(sources\[0\]);

  new ScreenShot({
    enableWebRtc: true, // 启用webrtc
    screenFlow: stream!, // 传入屏幕流数据
    level: 999,
  });
}

> 感谢 @Vanisper 提供的在electron环境下使用本插件的兼容思路。

### electron示例代码

如果你看完上个章节的使用方法，依然不是很理解的话，这里准备了一份在electron环境下使用本插件的demo，请移步electron-js-web-screen-shot-demo。

### 兼容移动端

插件对触屏设备做了兼容处理，如果你是pc端的触屏设备可以支持webrtc模式，如果是移动端那么就只能使用html2canvas模式。

import ScreenShot from "js-web-screen-shot";

const config \= {
    enableWebRtc: false
};
const screenShotHandler \= new ScreenShot(config);

<!DOCTYPE html\>
<html lang\="zh-CN"\>
<head\>
<!--禁止移动端浏览器的缩放-->
<meta name\="viewport" content\="user-scalable=no"\>
</head\>
<body\>
/body\>
</html\>

> 注意：在移动端使用时，需要在head标签里禁止浏览器的缩放行为，否则就会出现在使用撤销功能时，多次双击造成界面放大问题。

### Vue项目下使用乱码问题

当你vue项目中使用h2c模式进行截图时，画布左上角可能会出现一些奇怪的字符，这是由于`noscript`标签导致的，将其删除即可。

### 参数说明

截图插件有一个可选参数，它接受一个对象，对象每个key的作用如下:

-   `enableWebRtc` 是否启用webrtc，值为`boolean`类型，值为`false`则使用`html2canvas`来截图
-   `screenFlow` 设备提供的屏幕流数据(用于electron环境下自己传入的视频流数据)，需要将**enableWebRtc**属性设为`true`
-   `completeCallback` 截图完成回调函数，值为`Function`类型，最右侧的对号图标点击后会将图片的base64地址与裁剪信息回传给你定义的函数，如果不传的话则会将这些数据放到`sessionStorage`中，你可以通过下述方式拿到他：

sessionStorage.getItem("screenShotImg");

-   `closeCallback` 截图关闭回调函数，值为`Function`类型。
-   `triggerCallback` 截图响应回调函数，值为`Function`类型，使用html2canvas截屏时，页面图片过多时响应会较慢；使用webrtc截屏时用户点了分享，该函数为响应完成后触发的事件。回调函数返回一个对象，类型为: `{code: number,msg: string, displaySurface: string | null,displayLabel: string | null}`，code为0时代表截图加载完成，displaySurface返回的的是当前选择的窗口类型，displayLabel返回的是当前选择的标签页标识，浏览器不支持时此值为null。
-   `cancelCallback` 取消分享回到函数，值为`Function`类型，使用webrtc模式截屏时，用户点了取消或者浏览器不支持时所触发的事件。回调函数返回一个对象，类型为：`{code: number,msg: string, errorInfo: string}`，code为-1时代表用户未授权或者浏览器不支持webrtc。
-   `saveCallback` 保存截图回调函数，值为`Function`类型。回调函数中返回两个参数：
    -   `code` 状态码，number类型，为0时代表保存成功
    -   `msg` 消息码，string类型。
-   `level` 截图容器层级，值为number类型。
-   `cutBoxBdColor` 裁剪区域边框像素点颜色，值为string类型。
-   `maxUndoNum` 最大可撤销次数, 值为number类型
-   `canvasWidth` 画布宽度，值为number类型，必须与高度一起设置，单独设置无效。
-   `canvasHeight` 画布高度，值为number类型，必须与宽度一起设置，单独设置无效。
-   `position` 截图容器位置，值为`{left?: number, top?: number}`类型
-   `clickCutFullScreen` 单击截全屏启用状态,值为`boolean`类型， 默认为`false`
-   `hiddenToolIco` 需要隐藏的截图工具栏图标，值为`Object`类型，默认为`{}`。传你需要隐藏的图标名称，将值设为`true`即可，除关闭图标外，其他图标均可隐藏。可隐藏的key如下所示：
    -   `square` 矩形绘制
    -   `round` 圆形绘制
    -   `rightTop` 箭头绘制
    -   `brush` 涂鸦
    -   `mosaicPen`马赛克工具
    -   `text` 文本工具
    -   `separateLine` 分割线
    -   `save` 下载图片
    -   `undo` 撤销工具
    -   `confirm` 保存图片
-   `showScreenData` 截图组件加载完毕后，是否显示截图内容至canvas画布内，值为`boolean`类型，默认为`false`。
-   `customRightClickEvent` 自定义容器的右键点击事件，值为`Object`类型，接受2个参数：
    -   `state` 是否拦截右键点击，值为boolean类型，默认为`false`。
    -   `handleFn` 拦截后的事件处理函数，该属性为可选项，如果不传，默认行为是销毁组件。
-   `imgSrc` 截图内容，如果你已经通过其他方式获取到了屏幕内容（例如`electron`环境），那么可以将获取到的内容传入，此时插件将使用你传进来的图片，值为`string`类型（可以为图片`url`地址或者`base64`），默认为`null`。
-   `loadCrossImg` 是否加载跨域图片，值为`boolean`类型，默认为`false`。
-   `proxyUrl` 代理服务器地址，值为`string`类型，默认为""
-   `screenShotDom` 需要进行截图的容器，值为`HTMLElement`类型，默认使用的是`body`。
-   `useRatioArrow` 是否使用等比例箭头, 默认为false(递增变粗的箭头)。
-   `imgAutoFit` 是否开启图片自适应, 默认为false。如果自定义了截图内容，浏览器的缩放比例不为100%时，可以设置此参数来修复图片与蒙板大小不一致的问题。
-   `cropBoxInfo` 初始裁剪框，值为`{ x: number; y: number; w: number; h: number }`类型，默认不加载。
-   `wrcReplyTime` webrtc模式捕捉屏幕时的响应时间，值为`number`类型，默认为500ms。
-   `wrcImgPosition` webrtc模式下是否需要对图像进行裁剪，值为`{ x: number; y: number; w: number; h: number }`类型，默认为不裁剪。
-   `noScroll` 截图容器是否可滚动，值为`boolean`类型，默认为`true`。
-   `maskColor` 蒙层颜色，值为`{ r: number; g: number; b: number; a: number }`类型,默认为:`{ r: 0; g: 0; b: 0; a: 0.6 }`
-   `toolPosition` 工具栏展示位置，值为`string`类型，默认为居中展示，提供三个选项：
    -   `left` 左对齐于裁剪框
    -   `center` 居中对齐于裁剪框
    -   `right` 右对齐于裁剪框
-   `writeBase64` 是否将截图内容写入剪切板，值为`boolean`类型，默认为`true`
-   `wrcWindowMode` 是否启用窗口截图模式，值为`boolean`类型，默认为`false`，即当前标签页截图。如果标签页截图的内容有滚动条或者底部有空缺，可以考虑启用此模式。
-   `hiddenScrollBar` 是否隐藏滚动条，用webrtc模式截图时chrome 112版本的浏览器在部分系统下会挤压出现滚动条，如果出现你可以尝试通过此参数来进行修复。值为`Object`类型，有4个属性：
    -   `state: boolean`; 启用状态, 默认为`false`
    -   `fillState?: boolean`; 填充状态，默认为`false`
    -   `color?: string`; 填充层颜色，滚动条隐藏后可能会出现空缺，需要进行填充，默认填充色为黑色。
    -   `fillWidth?: number`; 填充层宽度，默认为截图容器的宽度
    -   `fillHeight?: number`; 填充层高度，默认为空缺区域的高度

> 使用当前标签页进行截图相对而言用户体验是最好的，但是因为`chrome 112`版本的bug会造成页面内容挤压导致截取到的内容不完整，因此只能采用其他方案来解决此问题了。`wrcWindowMode`和`hiddenScrollBar`都可以解决这个问题。
> 
> -   `wrcWindowMode`方案会更完美些，但是用户授权时会出现其他的应用程序选项，用户体验会差一些
> -   `hiddenScrollBar`方案还是采用标签页截图，但是会造成内容挤压，底部出现空白。
> 
> 两种方案的优点与缺点讲完了，最好的办法还是希望`chrome`能在之后的版本更新中修复此问题。

> 上述类型中的`?:`为ts中的可选类型，意思为：这个key是可选的，如果需要就传，不需要就不传。

> imgSrc是url时，如果图片资源跨域了，必须让图片服务器允许跨域才能正常加载。同样的loadCrossImg设置为true时，图片资源跨域了也需要让图片服务器允许跨域。

### 快捷键监听

插件容器监听了三个快捷键，如下所示：

-   `Esc`，按下键盘上的esc键时，等同于点了工具栏的关闭图标。
-   `Enter`，按下键盘上的enter键时，等同于点了截图工具栏的确认图标。
-   `Ctrl/Command + z`，按下这两个组合键时，等同于点了截图工具栏的撤销图标。

### 额外提供的API

插件暴露了一些内部变量出来，便于调用者根据自己的需求进行修改。

#### getCanvasController

该函数用于获取截图容器的DOM，返回值为`HTMLCanvasElement`类型。

示例代码：

import ScreenShot from "js-web-screen-shot";

const screenShotHandler \= new ScreenShot();
const canvasDom \= screenShotHandler.getCanvasController();

> 注意：如果截图容器尚未加载完毕，获取到的内容可能为null。

#### destroyComponents

该函数用于销毁截图容器，无返回值。

示例代码：

import ScreenShot from "js-web-screen-shot";

const screenShotHandler \= new ScreenShot();
screenShotHandler.destroyComponents()

#### completeScreenshot

该函数用于将框选区域的截图内容写入剪切版，无返回值。

该方法可以跟`cropBoxInfo`参数结合起来实现指定位置的自动截图，截图内容默认写入剪切版内，如果你想拿到截取到的base64内容可以通过`completeCallback`参数拿到，或者直接从sessionStorage中获取。

该回调函数中返回的参数格式如下所示：

-   base64
-   cutInfo 裁剪框位置参数
    -   startX
    -   startY
    -   width
    -   height

示例代码：

      const plugin \= new screenShotPlugin(
        {
          clickCutFullScreen:true,
          wrcWindowMode: true,
          cropBoxInfo:{x:350, y:20, w:300, h:300},
          completeCallback: ({base64, cutInfo}) \=> {
            console.log(base64, cutInfo);
          },
          triggerCallback:() \=> {
            // 截图组件加载完毕调用此方法来完成框选区域的截图
            plugin.completeScreenshot()
          }
        });

> 注意：此方法在1.9.9版本之后不再返回字符串类型的数据，而是返回的对象格式。

### 工具栏图标定制

如果你需要修改截图工具栏的图标，可以通过覆盖元素css类名的方式实现，插件内所有图标的css类名如下所示：

-   square 矩形绘制图标
-   round 圆型绘制图标
-   right-top 箭头绘制图标
-   brush 画笔工具
-   mosaicPen 马赛克工具
-   text 文本工具
-   save 保存
-   close 关闭
-   undo 撤销
-   confirm 确认

以`square`为例，要修改它的图标，只需要将下述代码添加进你项目代码的样式中即可。

  .square {
    background-image: url("你的图标路径") !important;
    
    &:hover {
      background-image: url("你的图标路径") !important;
    }
    
    &:active {
      background-image: url("你的图标路径") !important;
    }
 }

写在最后
----

至此，插件的所有使用方法就介绍完了，该插件的Vue3版本，请移步：vue-web-screen-shot
