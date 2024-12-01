---
project: zed
stars: 50865
description: Code at the speed of thought – Zed is a high-performance, multiplayer code editor from the creators of Atom and Tree-sitter.
url: https://github.com/zed-industries/zed
---

Zed
===

Welcome to Zed, a high-performance, multiplayer code editor from the creators of Atom and Tree-sitter.

* * *

### Installation

On macOS and Linux you can download Zed directly or install Zed via your local package manager.

Other platforms are not yet available:

-   Windows (tracking issue)
-   Web (tracking issue)

### Developing Zed

-   Building Zed for macOS
-   Building Zed for Linux
-   Building Zed for Windows
-   Running Collaboration Locally

### Contributing

See CONTRIBUTING.md for ways you can contribute to Zed.

Also... we're hiring! Check out our jobs page for open roles.

### Licensing

License information for third party dependencies must be correctly provided for CI to pass.

We use `cargo-about` to automatically comply with open source licenses. If CI is failing, check the following:

-   Is it showing a `no license specified` error for a crate you've created? If so, add `publish = false` under `[package]` in your crate's Cargo.toml.
-   Is the error `failed to satisfy license requirements` for a dependency? If so, first determine what license the project has and whether this system is sufficient to comply with this license's requirements. If you're unsure, ask a lawyer. Once you've verified that this system is acceptable add the license's SPDX identifier to the `accepted` array in `script/licenses/zed-licenses.toml`.
-   Is `cargo-about` unable to find the license for a dependency? If so, add a clarification field at the end of `script/licenses/zed-licenses.toml`, as specified in the cargo-about book.
