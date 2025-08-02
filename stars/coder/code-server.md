---
project: code-server
stars: 73217
description: VS Code in the browser
url: https://github.com/coder/code-server
---

code-server
===========

Run VS Code on any machine anywhere and access it in the browser.

Highlights
----------

-   Code on any device with a consistent development environment
-   Use cloud servers to speed up tests, compilations, downloads, and more
-   Preserve battery life when you're on the go; all intensive tasks run on your server

Requirements
------------

See requirements for minimum specs, as well as instructions on how to set up a Google VM on which you can install code-server.

**TL;DR:** Linux machine with WebSockets enabled, 1 GB RAM, and 2 vCPUs

Getting started
---------------

There are five ways to get started:

1.  Using the install script, which automates most of the process. The script uses the system package manager if possible.
2.  Manually installing code-server
3.  Deploy code-server to your team with coder/coder
4.  Using our one-click buttons and guides to deploy code-server to a cloud provider ⚡
5.  Using the code-server feature for devcontainers, if you already use devcontainers in your project.

If you use the install script, you can preview what occurs during the install process:

curl -fsSL https://code-server.dev/install.sh | sh -s -- --dry-run

To install, run:

curl -fsSL https://code-server.dev/install.sh | sh

When done, the install script prints out instructions for running and starting code-server.

> **Note** To manage code-server for a team on your infrastructure, see: coder/coder

We also have an in-depth setup and configuration guide.

Questions?
----------

See answers to frequently asked questions.

Want to help?
-------------

See Contributing for details.

Hiring
------

Interested in working at Coder? Check out our open positions!

For Teams
---------

We develop coder/coder to help teams to adopt remote development.
