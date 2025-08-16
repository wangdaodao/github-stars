---
project: openwrt
stars: 23353
description: This repository is a mirror of https://git.openwrt.org/openwrt/openwrt.git It is for reference only and is not active for check-ins.  We will continue to accept Pull Requests here. They will be merged via staging trees then into openwrt.git.
url: https://github.com/openwrt/openwrt
---

OpenWrt Project is a Linux operating system targeting embedded devices. Instead of trying to create a single, static firmware, OpenWrt provides a fully writable filesystem with package management. This frees you from the application selection and configuration provided by the vendor and allows you to customize the device through the use of packages to suit any application. For developers, OpenWrt is the framework to build an application without having to build a complete firmware around it; for users this means the ability for full customization, to use the device in ways never envisioned.

Sunshine!

Download
--------

Built firmware images are available for many architectures and come with a package selection to be used as WiFi home router. To quickly find a factory image usable to migrate from a vendor stock firmware to OpenWrt, try the _Firmware Selector_.

-   OpenWrt Firmware Selector

If your device is supported, please follow the **Info** link to see install instructions or consult the support resources listed below.

An advanced user may require additional or specific package. (Toolchain, SDK, ...) For everything else than simple firmware download, try the wiki download page:

-   OpenWrt Wiki Download

Development
-----------

To build your own firmware you need a GNU/Linux, BSD or macOS system (case sensitive filesystem required). Cygwin is unsupported because of the lack of a case sensitive file system.

### Requirements

You need the following tools to compile OpenWrt, the package names vary between distributions. A complete list with distribution specific packages is found in the Build System Setup documentation.

```
binutils bzip2 diff find flex gawk gcc-6+ getopt grep install libc-dev libz-dev
make4.1+ perl python3.7+ rsync subversion unzip which
```

### Quickstart

1.  Run `./scripts/feeds update -a` to obtain all the latest package definitions defined in feeds.conf / feeds.conf.default
    
2.  Run `./scripts/feeds install -a` to install symlinks for all obtained packages into package/feeds/
    
3.  Run `make menuconfig` to select your preferred configuration for the toolchain, target system & firmware packages.
    
4.  Run `make` to build your firmware. This will download all sources, build the cross-compile toolchain and then cross-compile the GNU/Linux kernel & all chosen applications for your target system.
    

### Related Repositories

The main repository uses multiple sub-repositories to manage packages of different categories. All packages are installed via the OpenWrt package manager called `opkg`. If you're looking to develop the web interface or port packages to OpenWrt, please find the fitting repository below.

-   LuCI Web Interface: Modern and modular interface to control the device via a web browser.
    
-   OpenWrt Packages: Community repository of ported packages.
    
-   OpenWrt Routing: Packages specifically focused on (mesh) routing.
    
-   OpenWrt Video: Packages specifically focused on display servers and clients (Xorg and Wayland).
    

Support Information
-------------------

For a list of supported devices see the OpenWrt Hardware Database

### Documentation

-   Quick Start Guide
-   User Guide
-   Developer Documentation
-   Technical Reference

### Support Community

-   Forum: For usage, projects, discussions and hardware advise.
-   Support Chat: Channel `#openwrt` on **oftc.net**.

### Developer Community

-   Bug Reports: Report bugs in OpenWrt
-   Dev Mailing List: Send patches
-   Dev Chat: Channel `#openwrt-devel` on **oftc.net**.

License
-------

OpenWrt is licensed under GPL-2.0
