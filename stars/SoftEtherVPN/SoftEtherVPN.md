---
project: SoftEtherVPN
stars: 12414
description: Cross-platform multi-protocol VPN software. Pull requests are welcome. The stable version is available at https://github.com/SoftEtherVPN/SoftEtherVPN_Stable.
url: https://github.com/SoftEtherVPN/SoftEtherVPN
---

SoftEther VPN
=============

Badges

GitLab CI

Coverity Scan

Cirrus CI

-   SoftEther VPN
-   BOARD MEMBERS OF THIS REPOSITORY
-   SOFTETHER VPN ADVANTAGES
-   Installation
    -   For FreeBSD
    -   For Windows
    -   From binary installers (stable channel)
    -   Build from Source code
-   About HTML5-based Modern Admin Console and JSON-RPC API Suite
    -   Built-in SoftEther VPN Server HTML5 Ajax-based Web Administration Console
    -   Built-in SoftEther Server VPN JSON-RPC API Suite
-   TO CIRCUMVENT YOUR GOVERNMENT'S FIREWALL RESTRICTION
-   SOURCE CODE CONTRIBUTION
-   DEAR SECURITY EXPERTS

SoftEther VPN (Developer Edition Master Repository)

-   An Open-Source Cross-platform Multi-protocol VPN Program https://www.softether.org/

This repository has experimental codes. Pull requests are welcome.

Stable Edition is available on https://github.com/SoftEtherVPN/SoftEtherVPN\_Stable which the non-developer user can stable use.

Please note that some features are not available in Stable Edition.

Source code packages (.zip and .tar.gz) and binary files of Stable Edition are also available:  
https://www.softether-download.com/

Copyright (c) all contributors on SoftEther VPN project in GitHub. Copyright (c) Daiyuu Nobori, SoftEther Project at University of Tsukuba, and SoftEther Corporation.

* * *

The development of SoftEther VPN was supported by the MITOH Project, a research and development project by Japanese Government, subsidized by Ministry of Economy, Trade and Industry of Japan, administrated by Information Promotion Agency. https://www.ipa.go.jp/english/humandev/

* * *

Icons8 kindly supported the project by gifting a license which allows to edit and redistribute their icons.

Please note that you are not allowed to redistribute those icons outside of this repository.

The developers of SoftEther VPN love Icons8's work and kindly ask the users to support them as much as possible.

* * *

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

SoftEther VPN ("SoftEther" means "Software Ethernet") is one of the world's most powerful and easy-to-use multi-protocol VPN software.

SoftEther VPN runs on Windows, Linux, Mac, FreeBSD and Solaris.

SoftEther VPN supports most of widely-used VPN protocols including SSL-VPN, WireGuard, OpenVPN, IPsec, L2TP, MS-SSTP, L2TPv3 and EtherIP by the single SoftEther VPN Server program.

More details on https://www.softether.org/.

BOARD MEMBERS OF THIS REPOSITORY
================================

Daiyuu Nobori (Since Jan 2, 2014) https://github.com/dnobori

Moataz Elmasry (Since Nov 6, 2017) https://github.com/moatazelmasry2

Zulyandri Zardi (Since Nov 6, 2017) https://github.com/zulzardi

Alex Maslakov (Since Nov 6, 2017) https://github.com/GildedHonour

Davide Beatrici (Since Jul 21, 2018) https://github.com/davidebeatrici

Ilya Shipitsin (Since Jul 21, 2018) https://github.com/chipitsine

SOFTETHER VPN ADVANTAGES
========================

-   Supporting all popular VPN protocols by the single VPN server: SSL-VPN (HTTPS) WireGuard OpenVPN IPsec L2TP MS-SSTP L2TPv3 EtherIP
-   Free and open-source software.
-   Easy to establish both remote-access and site-to-site VPN.
-   SSL-VPN Tunneling on HTTPS to pass through NATs and firewalls.
-   Revolutionary VPN over ICMP and VPN over DNS features.
-   Resistance to highly-restricted firewall.
-   Ethernet-bridging (L2) and IP-routing (L3) over VPN.
-   Embedded dynamic-DNS and NAT-traversal so that no static nor fixed IP address is required.
-   AES 256-bit and RSA 4096-bit encryptions.
-   Sufficient security features such as logging and firewall inner VPN tunnel.
-   User authentication with RADIUS and NT domain controllers.
-   User authentication with X.509 client certificate.
-   Packet logging.
-   1Gbps-class high-speed throughput performance with low memory and CPU usage.
-   Windows, Linux, Mac, Android, iPhone, iPad and Windows Phone are supported.
-   The OpenVPN clone function supports legacy OpenVPN clients.
-   IPv4 / IPv6 dual-stack.
-   The VPN server runs on Windows, Linux, FreeBSD, Solaris and Mac OS X.
-   Configure All settings on GUI.
-   Multi-languages (English, Japanese and Simplified-Chinese).
-   No memory leaks. High quality stable codes, intended for long-term runs. We always verify that there are no memory or resource leaks before releasing the build.
-   More details at https://www.softether.org/.

Comparison with Stable Edition
==============================

Protocol

Stable Edition (SE)

Developer Edition (DE)

Comment

SSL-VPN

✅

✅

OpenVPN

✅

✅

AEAD mode is supported in DE only.

IPsec

✅

✅

L2TP

✅

✅

MS-SSTP

✅

✅

L2TPv3

✅

✅

EtherIP

✅

✅

WireGuard

❌

✅

IKEv2

❌

❌

Feature

Stable Edition (SE)

Developer Edition (DE)

Comment

Password Authentication

✅

✅

RADIUS / NT Authentication

✅

✅

Certificate Authentication

⚠️

✅

SE supports the feature in SSL-VPN only.

IPv6-capable VPN Tunnel

⚠️

✅

SE supports IPv6 in L2 VPN tunnels only.

IPv4 Route Management

✅

✅

Windows clients only

IPv6 Route Management

❌

✅

Windows clients only

TLS Server Verification

⚠️

✅

In SE you need to specify the exact certificate or CA to verify. DE can perform standard TLS verification and use the system CA store.

Dual-stack Name Resolution

⚠️

✅

SE attempts in IPv6 only after IPv4 has failed.

ECDSA Certificates Import

❌

✅

Runs on Windows XP and Earlier

✅

❌

Compatible with SoftEther VPN 1.0

✅

❌

AES-NI Hardware Acceleration

⚠️

✅

SE requires intel\_aes\_lib to enable AES-NI, so x86 only. In DE, enabled by default as long as processor supports it (at least x86 and ARM).

Installation
============

For FreeBSD
-----------

SoftEther VPN in FreeBSD Ports Collection is maintained by Koichiro Iwao (@metalefty).

Binary package can be installed by pkg:

```
pkg install softether5
```

Alternatively, it can be built & installed by ports:

```
make install -C /usr/ports/security/softether5
```

To run SoftEther VPN Server:

```
service softether_server start
```

To configure SoftEther VPN Server startup on boot:

```
sysrc softether_server_enable=yes
```

Also SoftEther VPN Stable Edition and RTM version are available on FreeBSD.

For Windows
-----------

Releases

Nightly builds (choose appropriate platform, then find binaries or installers as artifacts)

From binary installers (stable channel)
---------------------------------------

Those can be found under https://www.softether-download.com/ There you can also find SoftEtherVPN source code in zip and tar formats.

Docker Container Image
----------------------

Please look at the ContainerREADME.md

Build from Source code
----------------------

see BUILD\_UNIX or BUILD\_WINDOWS

There are two flavours of SoftEtherVPN source code:

1.  Unstable. Found under https://github.com/SoftEtherVPN/SoftEtherVPN
2.  Stable. Found under https://github.com/SoftEtherVPN/SoftEtherVPN\_Stable

About HTML5-based Modern Admin Console and JSON-RPC API Suite
=============================================================

Built-in SoftEther VPN Server HTML5 Ajax-based Web Administration Console
-------------------------------------------------------------------------

We are developing the HTML5 Ajax-based Web Administration Console (currently very limited, under construction) in the embedded HTTPS server on the SoftEther VPN Server.

Access to the following URL from your favorite web browser.

```
https://<vpn_server_hostname>:<port>/admin/
```

For example if your VPN Server is running as the port 5555 on the host at 192.168.0.1, you can access to the web console by:

```
https://192.168.0.1:5555/admin/
```

Note: Your HTML5 development contribution is very appreciated. The current HTML5 pages are written by Daiyuu Nobori (the core developer of SoftEther VPN). He is obviously lack of HTML5 development ability. Please kindly consider to contribute for SoftEther VPN's development on GitHub. Your code will help every people running SoftEther VPN Server.

Built-in SoftEther Server VPN JSON-RPC API Suite
------------------------------------------------

The API Suite allows you to easily develop your original SoftEther VPN Server management application to control the VPN Server (e.g. creating users, adding Virtual Hubs, disconnecting a specified VPN sessions).

You can access to the latest SoftEther VPN Server JSON-RPC Document on GitHub.

-   Almost all control APIs, which the VPN Server provides, are available as JSON-RPC API. You can write your own VPN Server management application in your favorite languages (JavaScript, TypeScript, Java, Python, Ruby, C#, ... etc.)
-   If you are planning to develop your own VPN cloud service, the JSON-RPC API is the best choice to realize the automated operations for the VPN Server.
-   No need to use any specific API client library since all APIs are provided on the JSON-RPC 2.0 Specification. You can use your favorite JSON and HTTPS client library to call any of all APIs in your pure runtime environment.
-   Also, the SoftEther VPN Project provides high-quality JSON-RPC client stub libraries which define all of the API client stub codes. These libraries are written in C#, JavaScript and TypeScript. The Node.js Client Library for VPN Server RPC (vpnrpc) package is also available.

TO CIRCUMVENT YOUR GOVERNMENT'S FIREWALL RESTRICTION
====================================================

Because SoftEther VPN is overly strong tool to build a VPN tunnel, some censorship governments want to block your access to the source code of SoftEther VPN, by abusing their censorship firewalls.

To circumvent your censor's unjust restriction, SoftEther VPN Project distributes the up-to-date source code on all the following open-source repositories:

-   GitHub https://github.com/SoftEtherVPN/SoftEtherVPN
    
    ```
    $ git clone https://github.com/SoftEtherVPN/SoftEtherVPN.git
    ```
    
-   GitLab (mirrored from GitHub) https://gitlab.com/SoftEther/VPN
    
    ```
    $ git clone https://gitlab.com/SoftEther/VPN.git
    ```
    
-   OneDev (mirrored from GitHub) https://code.onedev.io/SoftEther/VPN
    
    ```
    $ git clone https://code.onedev.io/SoftEther/VPN.git
    ```
    

We hope that you can reach one of the above URLs at least!

SOURCE CODE CONTRIBUTION
========================

Your contribution to SoftEther VPN Project is much appreciated. Please send patches to us through GitHub.

DEAR SECURITY EXPERTS
=====================

If you find a bug or a security vulnerability please kindly inform us about the problem immediately so that we can fix the security problem to protect a lot of users around the world as soon as possible.

Our e-mail address for security reports is: **softether-vpn-security at softether.org**

Please note that the above e-mail address is not a technical support inquiry address. If you need technical assistance, please visit https://www.softether.org/ and ask your question on the users forum.
