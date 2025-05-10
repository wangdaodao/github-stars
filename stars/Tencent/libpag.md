---
project: libpag
stars: 5269
description: The official rendering library for PAG (Portable Animated Graphics) files that renders After Effects animations natively across multiple platforms.
url: https://github.com/Tencent/libpag
---

English | 简体中文 | Homepage

Introduction
------------

libpag is a real-time rendering library for PAG (Portable Animated Graphics) files, capable of rendering both vector-based and raster-based animations across various platforms, including iOS, Android, OpenHarmony, macOS, Windows, Linux, and the Web.

PAG is an open-source file format designed for recording animations. You can create and export PAG files from Adobe After Effects using the PAGExporter plugin and preview them in the PAGViewer app, both available on macOS and Windows.

PAG is widely used in major Tencent apps like WeChat, Mobile QQ, Honor of Kings, Tencent Video, and QQ Music, as well as in thousands of third-party apps, reaching hundreds of millions of users.

Advantages
----------

-   **Highly efficient file format**

Benefiting from its highly efficient binary format, PAG files decode 10 times faster than JSON files and are about 50% smaller in file size for the same animations. Designers can also easily include beautiful animations with bitmaps or audiovisual media in a single file without needing additional attachments.

-   **All AE features supported**

While other solutions may only support exporting limited vector-based AE features, PAG combines vector-based and raster-based exporting techniques to support all AE animations in a single file. This means third-party plugin effects in AE can also be exported.

-   **Measurable performance**

PAG provides a monitoring panel in PAGViewer that displays normalized performance data for PAG files, making it easy for designers to review and optimize performance without needing developers. With numerous automatic optimization techniques from the PAGExporter plugin, you can create animations with impressive visual effects and excellent performance more efficiently.

PAGViewer includes a monitoring panel

-   **Runtime editable animations**

With the flexible editing APIs from the PAG SDK, developers can easily modify the layer structure of a single PAG file, combine multiple PAG files into one composition, or replace text and images with all pre-designed animation effects applied at runtime. This significantly reduces the coding work required for features like video templates.

System Requirements
-------------------

-   iOS 9.0 or later
-   Android 5.0 or later
-   HarmonyOS Next 5.0.0(12) or later
-   macOS 10.15 or later
-   Windows 7.0 or later
-   Chrome 69.0 or later (Web)
-   Safari 11.3 or later (Web)

Getting Started
---------------

We currently only publish precompiled libraries for iOS, Android, macOS, Web, and OpenHarmony. You can build libraries of other platforms from the source code. The latest releases can be downloaded from here.

### iOS Integration

You can download the framework from the release page or add `libpag` to your project using CocoaPods. To add the pod to your Podfile, include:

```
pod 'libpag'
```

And then run:

```
pod install
```

After installing the CocoaPod, import `libpag` into your project with:

```
#import <libpag/xxx.h>
```

### Android Integration

You can download the AAR from the release page or add `libpag` to your project using Maven:

Edit the `build.gradle` file in the root of your project and add `mavenCentral()` to the `repositories` section:

```
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.2.1'
    }
}
```

Add libpag to `app/build.gradle` (_`4.0.5.10` should be replaced with the latest release version_):

```
dependencies {
    implementation 'com.tencent.tav:libpag:4.0.5.10'
}
```

Add the following rule to your proguard rules to prevent incorrect obfuscation:

```
  -keep class org.libpag.** {*;}
  -keep class androidx.exifinterface.** {*;}
```

Finally, run gradle sync and build your project.

### OpenHarmony Integration

You can download the HAR file from the release page, or add `libpag` to your project using OHPM:

```
ohpm install @tencent/libpag
```

Alternatively, you can add it to your project manually. Add the following lines to `oh-package.json5` in your app module.

```
"dependencies": {
"@tencent/libpag": "^1.0.1",
}
```

Then run:

```
ohpm install
```

### Web Integration

Copy the following code into an HTML file and open it in your browser:

<canvas class\="canvas" id\="pag"\></canvas\>
<script src\="https://unpkg.com/libpag@latest/lib/libpag.min.js"\></script\>
<script\>
  window.libpag.PAGInit().then((PAG) \=> {
    const url \= 'https://pag.io/file/like.pag';
    fetch(url)
      .then((response) \=> response.blob())
      .then(async (blob) \=> {
        const file \= new window.File(\[blob\], url.replace(/(.\*\\/)\*(\[^.\]+)/i, '$2'));
        // Do Something.
      });
  });
</script\>

More information：Web SDK Guide

### Example

Explore these projects to learn how to use the libpag APIs:

-   https://github.com/libpag/pag-ios
-   https://github.com/libpag/pag-android
-   https://github.com/libpag/pag-web

### Documentation

-   iOS API Reference
-   Android API Reference
-   Web API Reference

You can find additional documentation on pag.io

Development
-----------

We recommend using the CLion IDE on macOS for development.

### Branch Management

-   The `main` branch is our active development branch, containing the latest features and bug fixes.
-   The `release/` branches are our stable milestone branches, fully tested. We periodically create a `release/{version}` branch from the `main` branch. After a `release/{version}` branch is created, only high-priority fixes are checked into it.

**Note: This repository only contains the latest code since PAG 4.0. For legacy PAG 3.0 versions, you can download the precompiled libraries from here.**

### Build Prerequisites

-   Xcode 11.0+
-   GCC 9.0+
-   Visual Studio 2019+
-   NodeJS 14.14.0+
-   Ninja 1.9.0+
-   CMake 3.13.0+
-   QT 6.2.0+
-   NDK 28+ (**28.0.13004108 recommended**)
-   Emscripten 3.1.58+

### Dependency Management

libpag uses the depsync tool to manage third-party dependencies.

**For macOS platform：**

Run the script located in the root directory of the project:

```
./sync_deps.sh
```

This script will automatically install the necessary tools and sync all third-party repositories.

**For other platforms：**

First, ensure you have the latest version of Node.js installed (you may need to restart your computer afterward). Then, run the following command to install the depsync tool:

```
npm install -g depsync
```

Then, run `depsync` in the root directory of the project.

```
depsync
```

You might need to enter your Git account and password during synchronization. Ensure you have enabled the `git-credential-store` so that `CMakeList.txt` can automatically trigger synchronization next time.

### Build

After synchronization, you can open the project with CLion and build the PAG library.

**For macOS:**

No additional CLion configuration is needed.

**For Windows:**

Follow these steps to configure CLion correctly:

-   Ensure you have installed the **\[Desktop development with C++\]** and **\[Universal Windows Platform development\]** components for VS2019.
-   Open the **File->Settings** panel, go to **Build, Execution, Deployment->Toolchains**, and set the toolchain to **Visual Studio** with **amd64 (Recommended)** or **x86** architecture.

**Note: If you encounter issues during the CMake build, update to the latest version of the CMake command-line tool and try again.**

Support Us
----------

If you find libpag helpful, please give us a **Star**. We truly appreciate your support :)

License
-------

libpag is licensed under the Apache Version 2.0 License

Privacy Policy
--------------

Please refer to the PAG SDK Personal Information Processing Rules when using the libpag SDK.

Contribution
------------

If you have any ideas or suggestions to improve libpag, feel free to submit an issue or a pull request. Before doing so, please read our Contributing Guide.
