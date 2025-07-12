---
project: jpegview
stars: 2596
description: Fork of JPEGView by David Kleiner - fast and highly configurable viewer/editor for JPEG, BMP, PNG, WEBP, TGA, GIF and TIFF images with a minimal GUI.  Basic on-the-fly image processing is provided - allowing adjusting typical parameters as sharpness, color balance, rotation, perspective, contrast and local under-/overexposure.
url: https://github.com/sylikc/jpegview
---

JPEGView - Image Viewer and Editor
==================================

This is the official re-release of JPEGView.

Description
-----------

JPEGView is a lean, fast and highly configurable image viewer/editor with a minimal GUI.

### Formats Supported

JPEGView has built-in support the following formats:

-   Popular: JPEG, GIF
-   Lossless: BMP, PNG, TIFF, PSD
-   Web: WEBP, JXL, HEIF/HEIC, AVIF
-   Legacy: TGA, WDP, HDP, JXR
-   Camera RAW formats:
    -   Adobe (DNG), Canon (CRW, CR2, CR3), Nikon (NEF, NRW), Sony (ARW, SR2)
    -   Olympus (ORF), Panasonic (RW2), Fujifilm (RAF)
    -   Sigma (X3F), Pentax (PEF), Minolta (MRW), Kodak (KDC, DCR)
    -   A full list is available here: LibRaw supported cameras

Many additional formats are supported by Windows Imaging Component (WIC)

### Basic Image Editor

Basic on-the-fly image processing is provided - allowing adjusting typical parameters:

-   sharpness
-   color balance
-   rotation
-   perspective
-   contrast
-   local under-exposure/over-exposure

### Other Features

-   Small and fast, uses AVX2/SSE2 and up to 4 CPU cores
-   High quality resampling filter, preserving sharpness of images
-   Basic image processing tools can be applied realtime during viewing
-   Movie/Slideshow mode - to play folder of JPEGs as movie

Installation
============

Official Releases
-----------------

Official releases will be made to sylikc's GitHub Releases page. Each release includes:

-   **Archive Zip/7z** - Portable
-   **Windows Installer MSI** - For Installs
-   **Source code** - Build it yourself

Portable
--------

JPEGView _does not require installation_ to run. Just **unzip, and run** either the 64-bit version, or the 32-bit version depending on which platform you're on. It can save the settings to the extracted folder and run entirely portable.

MSI Installer
-------------

For those who prefer to have JPEGView installed for All Users, a 32-bit/64-bit installer is available to download starting with v1.0.40.

(Unfortunately, I don't own a code signing certificate yet, so the MSI release is not signed. Please verify checksums!)

### WinGet

If you're on Windows 11, or Windows 10 (build 1709 or later), you can also download it directly from the official Microsoft WinGet tool repository. This downloads the latest MSI installer directly from GitHub for installation.

Example Usage:

C:> `winget search jpegview`

```
Name     Id              Version  Source
-----------------------------------------
JPEGView sylikc.JPEGView 1.1.43  winget
```

C:> `winget install jpegview`

```
Found JPEGView [sylikc.JPEGView] Version 1.1.43
This application is licensed to you by its owner.
Microsoft is not responsible for, nor does it grant any licenses to, third-party packages.
Downloading https://github.com/sylikc/jpegview/releases/download/v1.1.43/JPEGView64_en-us_1.1.43.msi
  ██████████████████████████████  4.23 MB / 4.23 MB
Successfully verified installer hash
Starting package install...
Successfully installed
```

PortableApps
------------

Another option is to use the official JPEGView on PortableApps package. The PortableApps launcher preserves user settings in a separate directory from the extracted application directory. This release is signed.

Scoop
-----

Scoop is a Windows command-line installer and manager for portable applications.

To install with Scoop, run the following commands:

scoop bucket add extras
scoop install extras/jpegview-fork

After installation, the configuration file is located at `%UserProfile%\scoop\persist\JPEGView-fork\JPEGView.ini`.

System Requirements
-------------------

-   64-bit version: Windows 7/8/10/11 64-bit or later
-   32-bit version: Windows 7 or later
    -   A special _32-bit Windows XP SP2_ build is available, which supports most formats (except for formats added after v1.0.37.1, ex. Animated PNG, JXL, HEIC). Other features and options are the same as the normal builds.

What's New
----------

-   See what has changed in the latest releases
-   Or Check the CHANGELOG.txt to review new features in detail.

Localization
============

By default, the language is auto-detected to match your Windows Locale. All the text in the menus and user interface should show in your language. To override the auto-detection, manually set `Language` option in `JPEGView.ini`

JPEGView is currently translated/localized to 28 languages:

INI Option

Language

be

Belarusian

bg

Bulgarian

cs

Czech

de

German

el

Greek, Modern

es-ar

Spanish (Argentina)

es

Spanish

eu

Basque

fi

Finnish

fr

French (Français)

hu

Hungarian

it

Italian

ja

Japanese (日本語)

ko

Korean (한국어)

pl

Polish

pt-br

Portuguese (Brazilian)

pt

Portuguese

ro

Romanian

ru

Russian (Русский)

sk

Slovak

sl

Slovenian (Slovenščina)

sr

Serbian (српски)

sv

Swedish

ta

Tamil

tr

Turkish (Türkçe)

uk

Ukrainian (Українська)

zh-tw

Chinese, Traditional (繁體中文)

zh

Chinese, Simplified (简体中文)

See the Localization wiki page for translation status for each language.

Help / Documentation
====================

The JPEGView documentation is a little out of the date at the moment, but should still give a good summary of the features.

This readme.html is part of the JPEGView package.

Brief History
=============

This GitHub repo continues the legacy (is a "fork") of the excellent project JPEGView by David Kleiner. Unfortunately, starting in 2020, the SourceForge project has essentially been abandoned, with the last update being 2018-02-24 (1.0.37). It's an excellent lightweight image viewer that I use almost daily!

The starting point for this repo was a direct clone from SourceForge SVN to GitHub Git. By continuing this way, it retains all previous commits and all original author comments.

I'm hoping with this project, some devs might help me keep the project alive! It's been awhile, and could use some new features or updates. Looking forward to the community making suggestions, and devs will help with some do pull requests as some of the image code is quite a learning curve for me to pick it up. -sylikc

Special Thanks
--------------

Special thanks to qbnu for adding additional codec support!

-   Animated WebP
-   Animated PNG
-   JPEG XL with animation support
-   HEIF/HEIC/AVIF support
-   QOI support
-   ICC Profile support for WebP, JPEG XL, HEIF/HEIC, AVIF
-   LibRaw support (all updated RAW formats, such as CR3)
-   Photoshop PSD support

Thanks to all the _translators_ which keep JPEGView strings up-to-date in different languages! See CHANGELOG.txt to find credits for translators at each release!
