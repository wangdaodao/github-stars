---
project: Pake
stars: 41837
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
-   🖱️ Smart right-click context menus with download support for images, videos, and files.
-   👻 Pake is just a simple tool — replaces the old bundle approach with Tauri (though PWA is also a good alternative).

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

Hide window, not quit

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

**Pake provides a command line tool, making the flow of package customization quicker and easier. See the CLI usage guide for more information.**

# Recommended (pnpm)
pnpm install -g pake-cli

# Alternative (npm)
npm install -g pake-cli

# Command usage
pake url \[OPTIONS\]...

# Feel free to play with Pake! It might take a while to prepare the environment the first time you launch Pake.
pake https://weekly.tw93.fun --name Weekly --hide-title-bar

If you are new to the command line, you can compile packages online with _GitHub Actions_. See our documentation for detailed guides.

Development
-----------

Prepare your environment before starting. Make sure you have Rust `>=1.89` and Node `>=18` (e.g., `22.11.0`) installed on your computer. _Note: Latest stable versions are recommended._ For installation guidance, see Tauri documentation.

If you are unfamiliar with these, it is better to try out the above tool to pack with one click.

# Install dependencies
pnpm i

# Local development (right-click to open debug mode)
pnpm run dev

# Build application
pnpm run build

Documentation
-------------

-   **CLI Usage** | 中文 - Command-line interface reference
-   **Advanced Usage** | 中文 - Customization and advanced features
-   **GitHub Actions** | 中文 - Build apps online
-   **Pake Action** - Use Pake as GitHub Action in your projects
-   **Contributing** - How to contribute to development

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

  
**Kittizz**

  
**Matt Bajorek**

  
**Srinivas Vaddi**

  
**Steam**

  
**Qitianjia**

  
**Yi Xin**

  
**Yue Yang**

  
**Kieran**

  
**孟世博**

  
**2nthony**

  
**Null**

  
**Abu Taher Siddik**

  
**An Li**

  
**Ayaka Neko**

  
**Dengju Deng**

  
**Fabien**

  
**Fechin**

  
**Imgbot**

  
**Jiaqi Gu**

  
**Luminall**

  
**Milo**

  
**Po Chen**

  
**Xie Ruiqi**

  
**Null**

  
**Null**

  
**Hyzhao**

  
**Null**

  
**Liudonghua**

  
**Liusishan**

  
**Ranger**

  
**贺天卓**

Support
-------

1.  I have two cats, TangYuan and Coke. If you think Pake delights your life, you can feed them some canned food 🥩.
2.  If you like Pake, you can star it on GitHub. Also, welcome to recommend Pake to your friends.
3.  You can follow my Twitter to get the latest news of Pake or join our Telegram chat group.
4.  I hope that you enjoy playing with it. Let us know if you find a website that would be great for a Mac App!
