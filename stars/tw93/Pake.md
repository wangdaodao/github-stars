---
project: Pake
stars: 36765
description: 🤱🏻 Turn any webpage into a desktop app with Rust.  🤱🏻 利用 Rust 轻松构建轻量级多端桌面应用
url: https://github.com/tw93/Pake
---

#### **English** | 简体中文 | 日本語

Pake
====

**Turn any webpage into a desktop app with Rust _with ease_.**

Pake supports Mac, Windows, and Linux. Check out README for Popular Packages, Command-Line Packaging, and Customized Development information. Feel free to share your suggestions in Discussions.

Features
--------

-   🎐 Nearly 20 times smaller than an Electron package (around 5M!)
-   🚀 With Rust Tauri, Pake is much more lightweight and faster than JS-based frameworks.
-   📦 Battery-included package — shortcut pass-through, immersive windows, and minimalist customization.
-   👻 Pake is just a simple tool — replace the old bundle approach with Tauri (though PWA is good enough).

Popular Packages
----------------

WeRead Mac Windows Linux

Twitter Mac Windows Linux

Grok Mac Windows Linux

DeepSeek Mac Windows Linux

ChatGPT Mac Windows Linux

Gemini Mac Windows Linux

YouTube Music Mac Windows Linux

YouTube Mac Windows Linux

LiZhi Mac Windows Linux

ProgramMusic Mac Windows Linux

Excalidraw Mac Windows Linux

XiaoHongShu Mac Windows Linux

🏂 You can download more applications from Releases. **Click here to expand the shortcuts reference!**  

Mac

Windows/Linux

Function

⌘ + \[

Ctrl + ←

Return to the previous page

⌘ + \]

Ctrl + →

Go to the next page

⌘ + ↑

Ctrl + ↑

Auto scroll to top of page

⌘ + ↓

Ctrl + ↓

Auto scroll to bottom of page

⌘ + r

Ctrl + r

Refresh Page

⌘ + w

Ctrl + w

Hide window, not quite

⌘ + \-

Ctrl + \-

Zoom out the page

⌘ + +

Ctrl + +

Zoom in the page

⌘ + \=

Ctrl + \=

Zoom in the Page

⌘ + 0

Ctrl + 0

Reset the page zoom

In addition, double-click the title bar to switch to full-screen mode. For Mac users, you can also use the gesture to go to the previous or next page and drag the title bar to move the window.

Before starting
---------------

1.  **For beginners**: Play with Popular Packages to find out Pake's capabilities, or try to pack your application with GitHub Actions. Don't hesitate to reach for assistance at Discussion!
2.  **For developers**: “Command-Line Packaging” supports macOS fully. For Windows/Linux users, it requires some tinkering. Configure your environment before getting started.
3.  **For hackers**: For people who are good at both front-end development and Rust, how about customizing your apps' function more with the following Customized Development?

Command-Line Packaging
----------------------

**Pake provides a command line tool, making the flow of package customization quicker and easier. See documentation for more information.**

# Install with npm
npm install -g pake-cli

# Command usage
pake url \[OPTIONS\]...

# Feel free to play with Pake! It might take a while to prepare the environment the first time you launch Pake.
pake https://weekly.tw93.fun --name Weekly --hide-title-bar

If you are new to the command line, you can compile packages online with _GitHub Actions_. See the Tutorial for more information.

Development
-----------

Prepare your environment before starting. Make sure you have Rust `>=1.63` and Node `>=16` (e.g., `16.18.1`) installed on your computer. For installation guidance, see Tauri documentation.

If you are unfamiliar with these, it is better to try out the above tool to pack with one click.

# Install Dependencies
npm i

# Local development \[Right-click to open debug mode.\]
npm run dev

# Pack application
npm run build

Advanced Usage
--------------

1.  You can refer to the codebase structure before working on Pake, which will help you much in development.
2.  Modify the `url` and `productName` fields in the `pake.json` file under the src-tauri directory, the "domain" field in the `tauri.config.json` file needs to be modified synchronously, as well as the `icon` and `identifier` fields in the `tauri.xxx.conf.json` file. You can select an `icon` from the `icons` directory or download one from macOSicons to match your product needs.
3.  For configurations on window properties, you can modify the `pake.json` file to change the value of `width`, `height`, `fullscreen` (or not), `resizable` (or not) of the `windows` property. To adapt to the immersive header on Mac, change `hideTitleBar` to `true`, look for the `Header` element, and add the `padding-top` property.
4.  For advanced usages such as style rewriting, advertisement removal, JS injection, container message communication, and user-defined shortcut keys, see Advanced Usage of Pake.

Developers
----------

Pake's development can not be without these Hackers. They contributed a lot of capabilities for Pake. Also, welcome to follow them! ❤️

  
**Tw93**

  
**Tlntin**

  
**Santree**

  
**Pan93412**

  
**Данил Бизимов**

  
**Volare**

  
**Bryan Lee**

  
**Essesoul**

  
**Jerry Zhou**

  
**Aiello**

  
**Horus**

  
**Pake Actions**

  
**GoodbyeNJN**

  
**Ikko Eltociear Ashimine**

  
**Matt Bajorek**

  
**Steam**

  
**Qitianjia**

  
**Yi Xin**

  
**孟世博**

  
**2nthony**

  
**Null**

  
**Abu Taher Siddik**

  
**An Li**

  
**Ayaka Neko**

  
**Dengju Deng**

  
**Fechin**

  
**Imgbot**

  
**Jiaqi Gu**

  
**Milo**

  
**Po Chen**

  
**Null**

  
**Hyzhao**

  
**Null**

  
**Liudonghua**

  
**Liusishan**

  
**Ranger**

  
**贺天卓**

Frequently Asked Questions
--------------------------

1.  Right-clicking on an image element in the page to open the menu and select download image or other events does not work (common in MacOS systems). This issue is due to the MacOS built-in webview not supporting this feature.

Support
-------

1.  I have two cats, TangYuan and Coke. If you think Pake delights your life, you can feed them some canned food 🥩.
2.  If you like Pake, you can star it on GitHub. Also, welcome to recommend Pake to your friends.
3.  You can follow my Twitter to get the latest news of Pake or join our Telegram chat group.
4.  I hope that you enjoy playing with it. Let us know if you find a website that would be great for a Mac App!
