---
project: NotepadNext
stars: 11822
description: A cross-platform, reimplementation of Notepad++
url: https://github.com/dail8859/NotepadNext
---

Notepad Next
============

A cross-platform, reimplementation of Notepad++.

Though the application overall is stable and usable, it should not be considered safe for critically important work.

There are numerous bugs and half working implementations. Pull requests are greatly appreciated.

Installation
============

Packages are available for Windows, Linux, and MacOS.

Below are the supported distribution mechanisms. There may be other ways to download/install the application, but this project will likely not be able to offer any support for those since they are made available by other individuals.

Windows
-------

Windows packages are available as an installer or a stand-alone zip file on the release page. The installer provides additional components such as an auto-updater and Windows context menu integration. You can easily install it with Winget:

winget install dail8859.NotepadNext

Linux
-----

Linux packages can be obtained by downloading the stand-alone AppImage on the release page or by installing the flatpak by executing:

flatpak install flathub com.github.dail8859.NotepadNext

MacOS
-----

MacOS disk images can be downloaded from the release page.

It can also be installed using brew:

brew tap dail8859/notepadnext
brew install --no-quarantine notepadnext

#### MacOS Tweaks

By default, MacOS enables font smoothing which causes text to appear quite differently from the Windows version. This can be disabled system-wide using the following command:

defaults -currentHost write -g AppleFontSmoothing -int 0

A restart is required for this to take effect.

Development
===========

Current development is done using QtCreator with the Microsoft Visual C++ (msvc) compiler. Qt 6.5 is the currently supported Qt version. Older versions of Qt are likely to work but are not tested. Any fixes for older versions will be accepted as long as they do not introduce complex fixes. This application is also known to build successfully on various Linux distributions and macOS. Other platforms/compilers should be usable with minor modifications.

If you are familiar with building C++ Qt desktop applications with Qt Creator, then this should be as simple as opening `src/NotepadNext.pro` and build/run the project.

If you are new to building C++ Qt desktop applications, there is a more detailed guide here.

License
=======

This code is released under the GNU General Public License version 3.
