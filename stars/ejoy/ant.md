---
project: ant
stars: 3905
description: Ant game engine
url: https://github.com/ejoy/ant
---

Ant 游戏引擎
========

English Version | 中文版本

Ant 是由灵犀互娱开发的开源游戏引擎。现阶段仅将代码仓库公开，尚未正式发布。文档、示例等均待在 Wiki 上逐步完善。如有任何问题，可在 Discussions 发帖讨论。Issues 仅用于 Bug 跟踪，请不要在里面提问题。

### 更新并初始化第三方库：

> git submodule update --init

### 搭建编译环境

#### 1.1 Windows

##### 1.1.1 MSVC

-   安装 Visual Studio version 22 17.5 或以上版本，因为依赖对 C11 Atomics 的支持，不然编译时会出现 `stdatomic.h no such file or directory` 错误。

##### 1.1.2 MINGW

-   下载并安装 msys2
-   找到 msys2 安装目录，用 mingw64.exe 打开 msys2 的终端
-   在 msys2 的终端中修改镜像服务器

echo "Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/i686/" \> /etc/pacman.d/mirrorlist.mingw32
echo "Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/mingw/x86\_64/" \> /etc/pacman.d/mirrorlist.mingw64
echo "Server = https://mirrors.tuna.tsinghua.edu.cn/msys2/msys/\\$arch/" \> /etc/pacman.d/mirrorlist.msys

-   把 ming64 的路径加到环境变量

echo "export MINGW=/mingw64" \>> ~/.bash\_profile
echo "export PATH=\\$MINGW/bin:\\$PATH" \>> ~/.bash\_profile

-   安装 gcc/ninja

pacman -Syu mingw-w64-x86\_64-gcc mingw-w64-x86\_64-ninja

#### 1.2 MACOS

-   安装xcode, ninja

#### 2.1 Common

##### 2.1.1 编译构建工具 luamake

git clone https://github.com/actboy168/luamake
cd luamake
git submodule update --init
.\\compile\\install.bat (msvc)
./compile/install.sh (mingw/linux/macos)

### 编译

#### 编译runtime

luamake

#### 编译tools

tools包含：shaderc, texturec, gltf2ozz，release模式会快一个数量级（debug模式下的tools可以不编译）

luamake -mode release tools

#### 编译选项

luamake \[target\] -mode \[debug/release\] #\-mode默认是debug

### 运行

运行一个最简单的示例

bin/msvc/debug/ant.exe test/simple/main.lua

### 启动编辑器

bin/msvc/debug/ant.exe tools/editor/main.lua \[projectdir\] #for example: test/simple

### 调试

-   安装VSCode；
-   安装**Lua Debug**插件；
-   添加调试配置到`.vscode/launch.json`

{
    "version": "0.2.0",
    "configurations": \[
        {
            "type": "lua",
            "request": "launch",
            "name": "Debug",
            "luaexe": "${workspaceFolder}/bin/msvc/debug/ant.exe",
            "luaVersion": "lua-latest",
            "path": null,
            "cpath": null,
            "console": "integratedTerminal",
            "stopOnEntry": true,
            "outputCapture": \[\],
            "program": "test/simple/main.lua",
            "arg": \[\]
        }
    \]
}

### 关于ant目录结构

-   **bin**：编译结果，exe/dll/lib等
-   **build**：编译的中间结果
-   **clibs**：c/c++代码
-   **engine**：引擎基础支持代码，包括包管理器、启动代码等
-   **pkg**：引擎的各个功能包（包与包之间有依赖）
-   **runtime**：引擎运行时的不同平台支持
-   **test**：测试工程
-   **tools**：引擎相关的工具
