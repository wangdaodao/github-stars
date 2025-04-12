---
project: shadPS4
stars: 21604
description: PlayStation 4 emulator for Windows, Linux and macOS written in C++
url: https://github.com/shadps4-emu/shadPS4
---

  
  
**shadPS4**  

====================

General information
===================

**shadPS4** is an early **PlayStation 4** emulator for **Windows**, **Linux** and **macOS** written in C++.

If you encounter problems or have doubts, do not hesitate to look at the **Quickstart**.  
To verify that a game works, you can look at **shadPS4 Game Compatibility**.  
To discuss shadPS4 development, suggest ideas or to ask for help, join our **Discord server**.  
To get the latest news, go to our **X (Twitter)** or our **website**.  
For those who'd like to donate to the project, we now have a **Kofi page**!

Status
======

Important

shadPS4 is early in development, don't expect a flawless experience.

Currently, the emulator can successfully run games like **Bloodborne**, **Dark Souls Remastered**, **Red Dead Redemption** and many other games.

Why
===

This project began as a fun project. Given our limited free time, it may take some time before shadPS4 can run more complex games, but we're committed to making small, regular updates.

Building
========

Important

If you want to use shadPS4 to play your games, you don't have to follow the build instructions, you can simply download the emulator from either the **release tab** or the **action tab**.

Windows
-------

Check the build instructions for **Windows**.

Linux
-----

Check the build instructions for **Linux**.

macOS
-----

Check the build instructions for **macOS**.

Important

macOS users need at least macOS 15.4 to run shadPS4. Due to GPU issues there are currently heavy bugs on Intel Macs.

Debugging and reporting issues
==============================

For more information on how to test, debug and report issues with the emulator or games, read the **Debugging documentation**.

Keyboard and Mouse Mappings
===========================

Note

Some keyboards may also require you to hold the Fn key to use the F\* keys. Mac users should use the Command key instead of Control, and need to use Command+F11 for full screen to avoid conflicting with system key bindings.

Button

Function

F10

FPS Counter

Ctrl+F10

Video Debug Info

F11

Fullscreen

F12

Trigger RenderDoc Capture

Note

Xbox and DualShock controllers work out of the box.

Controller button

Keyboard equivalent

LEFT AXIS UP

W

LEFT AXIS DOWN

S

LEFT AXIS LEFT

A

LEFT AXIS RIGHT

D

RIGHT AXIS UP

I

RIGHT AXIS DOWN

K

RIGHT AXIS LEFT

J

RIGHT AXIS RIGHT

L

TRIANGLE

Numpad 8 or C

CIRCLE

Numpad 6 or B

CROSS

Numpad 2 or N

SQUARE

Numpad 4 or V

PAD UP

UP

PAD DOWN

DOWN

PAD LEFT

LEFT

PAD RIGHT

RIGHT

OPTIONS

RETURN

BACK BUTTON / TOUCH PAD

SPACE

L1

Q

R1

U

L2

E

R2

O

L3

X

R3

M

Keyboard and mouse inputs can be customized in the settings menu by clicking the Controller button, and further details and help on controls are also found there. Custom bindings are saved per-game. Inputs support up to three keys per binding, mouse buttons, mouse movement mapped to joystick input, and more.

Firmware files
==============

shadPS4 can load some PlayStation 4 firmware files, these must be dumped from your legally owned PlayStation 4 console.  
The following firmware modules are supported and must be placed in shadPS4's `user/sys_modules` folder.

Modules

Modules

Modules

Modules

libSceCesCs.sprx

libSceFont.sprx

libSceFontFt.sprx

libSceFreeTypeOt.sprx

libSceJson.sprx

libSceJson2.sprx

libSceLibcInternal.sprx

libSceNgs2.sprx

libSceRtc.sprx

libSceUlt.sprx

Caution

The above modules are required to run the games properly and must be extracted from your PlayStation 4.  
**We do not provide any information or support on how to do this**.

Main team
=========

-   **georgemoralis**
-   **raphaelthegreat**
-   **psucien**
-   **skmp**
-   **wheremyfoodat**
-   **raziel1000**
-   **viniciuslrangel**
-   **roamic**
-   **poly**
-   **squidbus**
-   **frodo**

Logo is done by **Xphalnos**

Contributing
============

If you want to contribute, please look the **CONTRIBUTING.md** file.  
Open a PR and we'll check it :)

Translations
============

If you want to translate shadPS4 to your language we use **crowdin**.

Contributors
============

Special Thanks
==============

A few noteworthy teams/projects who've helped us along the way are:

-   **Panda3DS**: A multiplatform 3DS emulator from our co-author wheremyfoodat. They have been incredibly helpful in understanding and solving problems that came up from natively executing the x64 code of PS4 binaries
    
-   **fpPS4**: The fpPS4 team has assisted massively with understanding some of the more complex parts of the PS4 operating system and libraries, by helping with reverse engineering work and research.
    
-   **yuzu**: Our shader compiler has been designed with yuzu's Hades compiler as a blueprint. This allowed us to focus on the challenges of emulating a modern AMD GPU while having a high-quality optimizing shader compiler implementation as a base.
    
-   **felix86**: A new x86-64 → RISC-V Linux userspace emulator
    

License
=======

-   **GPL-2.0 license**
