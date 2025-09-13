---
project: gpt4free
stars: 65096
description: The official gpt4free repository | various collection of powerful language models | o4, o3 and deepseek r1, gpt-4.1, gemini 2.5
url: https://github.com/xtekky/gpt4free
---

GPT4Free (g4f)
==============

**Created by @xtekky,  
maintained by @hlohaus**

Support the project on GitHub Sponsors ❤️

Live demo & docs: https://g4f.dev | Documentation: https://g4f.dev/docs

* * *

GPT4Free (g4f) is a community-driven project that aggregates multiple accessible providers and interfaces to make working with modern LLMs and media-generation models easier and more flexible. GPT4Free aims to offer multi-provider support, local GUI, OpenAI-compatible REST APIs, and convenient Python and JavaScript clients — all under a community-first license.

This README is a consolidated, improved, and complete guide to installing, running, and contributing to GPT4Free.

Table of contents

-   What’s included
-   Quick links
-   Requirements & compatibility
-   Installation
    -   Docker (recommended)
    -   Slim Docker image
    -   Windows (.exe)
    -   Python (pip / from source / partial installs)
-   Running the app
    -   GUI (web client)
    -   FastAPI / Interference API
    -   CLI
    -   Optional provider login (desktop in container)
-   Using the Python client
    -   Synchronous text example
    -   Image generation example
    -   Async client example
-   Using GPT4Free.js (browser JS client)
-   Providers & models (overview)
-   Local inference & media
-   Configuration & customization
-   Running on smartphone
-   Interference API (OpenAI‑compatible)
-   Examples & common patterns
-   Contributing
    -   How to create a new provider
    -   How AI can help you write code
-   Security, privacy & takedown policy
-   Credits, contributors & attribution
-   Powered-by highlights
-   Changelog & releases
-   Manifesto / Project principles
-   License
-   Contact & sponsorship
-   Appendix: Quick commands & examples

* * *

What’s included
---------------

-   Python client library and async client.
-   Optional local web GUI.
-   FastAPI-based OpenAI-compatible API (Interference API).
-   Official browser JS client (g4f.dev distribution).
-   Docker images (full and slim).
-   Multi-provider adapters (LLMs, media providers, local inference backends).
-   Tooling for image/audio/video generation and media persistence.

* * *

Quick links
-----------

-   Website & docs: https://g4f.dev | https://g4f.dev/docs
-   PyPI: https://pypi.org/project/g4f
-   Docker image: https://hub.docker.com/r/hlohaus789/g4f
-   Releases: https://github.com/xtekky/gpt4free/releases
-   Issues: https://github.com/xtekky/gpt4free/issues
-   Community: Telegram (https://telegram.me/g4f\_channel) · Discord News (https://discord.gg/5E39JUWUFa) · Discord Support (https://discord.gg/qXA4Wf4Fsm)

* * *

Requirements & compatibility
----------------------------

-   Python 3.10+ recommended.
-   Google Chrome/Chromium for providers using browser automation.
-   Docker for containerized deployment.
-   Works on x86\_64 and arm64 (slim image supports both).
-   Some provider adapters may require platform-specific tooling (Chrome/Chromium, etc.). Check provider docs for details.

* * *

Installation
------------

### Docker (recommended)

1.  Install Docker: https://docs.docker.com/get-docker/
2.  Create persistent directories:
    -   Example (Linux/macOS):
        
        mkdir -p ${PWD}/har\_and\_cookies ${PWD}/generated\_media
        sudo chown -R 1200:1201 ${PWD}/har\_and\_cookies ${PWD}/generated\_media
        
3.  Pull image:
    
    docker pull hlohaus789/g4f
    
4.  Run container:
    
    docker run -p 8080:8080 -p 7900:7900 \\
      --shm-size="2g" \\
      -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
      -v ${PWD}/generated\_media:/app/generated\_media \\
      hlohaus789/g4f:latest
    

Notes:

-   Port 8080 serves GUI/API; 7900 can expose a VNC-like desktop for provider logins (optional).
-   Increase --shm-size for heavier browser automation tasks.

### Slim Docker image (x64 & arm64)

mkdir -p ${PWD}/har\_and\_cookies ${PWD}/generated\_media
chown -R 1000:1000 ${PWD}/har\_and\_cookies ${PWD}/generated\_media

docker run \\
  -p 1337:8080 -p 8080:8080 \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_media:/app/generated\_media \\
  hlohaus789/g4f:latest-slim

Notes:

-   The slim image can update the g4f package on startup and installs additional dependencies as needed.
-   In this example, the Interference API is mapped to 1337.

### Windows Guide (.exe)

1.  Download the release artifact `g4f.exe.zip` from: https://github.com/xtekky/gpt4free/releases/latest
2.  Unzip and run `g4f.exe`.
3.  Open GUI at: http://localhost:8080/chat/
4.  If Windows Firewall blocks access, allow the application.

### Python Installation (pip / from source / partial installs)

Prerequisites:

-   Python 3.10+ (https://www.python.org/downloads/)
-   Chrome/Chromium for some providers.

Install from PyPI (recommended):

pip install -U g4f\[all\]

Partial installs

-   To install only specific functionality, use optional extras groups. See docs/requirements.md in the project docs.

Install from source:

git clone https://github.com/xtekky/gpt4free.git
cd gpt4free
pip install -r requirements.txt
pip install -e .

Notes:

-   Some features require Chrome/Chromium or other tools; follow provider-specific docs.

* * *

Running the app
---------------

### GUI (web client)

-   Run via Python:

from g4f.gui import run\_gui
run\_gui()

-   Or via CLI:

python -m g4f.cli gui --port 8080 --debug

-   Open: http://localhost:8080/chat/

### FastAPI / Interference API

-   Start FastAPI server:

python -m g4f --port 8080 --debug

-   If using slim docker mapping, Interference API may be available at `http://localhost:1337/v1`
-   Swagger UI: `http://localhost:1337/docs`

### CLI

-   Start GUI server:

python -m g4f.cli gui --port 8080 --debug

### Optional provider login (desktop within container)

-   Accessible at:
    
    ```
    http://localhost:7900/?autoconnect=1&resize=scale&password=secret
    ```
    
-   Useful for logging into web-based providers to obtain cookies/HAR files.

* * *

Using the Python client
-----------------------

Install:

pip install -U g4f\[all\]

Synchronous text example:

from g4f.client import Client

client \= Client()
response \= client.chat.completions.create(
    model\="gpt-4o-mini",
    messages\=\[{"role": "user", "content": "Hello, how are you?"}\],
    web\_search\=False
)
print(response.choices\[0\].message.content)

Expected:

```
Hello! How can I assist you today?
```

Image generation example:

from g4f.client import Client

client \= Client()
response \= client.images.generate(
    model\="flux",
    prompt\="a white siamese cat",
    response\_format\="url"
)
print(f"Generated image URL: {response.data\[0\].url}")

Async client example:

from g4f.async\_client import AsyncClient
import asyncio

async def main():
    client \= AsyncClient()
    response \= await client.chat.completions.create(
        model\="gpt-4o-mini",
        messages\=\[{"role": "user", "content": "Explain quantum computing briefly"}\],
    )
    print(response.choices\[0\].message.content)

asyncio.run(main())

Notes:

-   See the full API reference for streaming, tool-calling patterns, and advanced options: https://g4f.dev/docs/client

* * *

Using GPT4Free.js (browser JS client)
-------------------------------------

Use the official JS client in the browser—no backend required.

Example:

<script type\="module"\>
  import Client from 'https://g4f.dev/dist/js/client.js';

  const client \= new Client();
  const result \= await client.chat.completions.create({
      model: 'gpt-4.1',  // Or "gpt-4o", "deepseek-v3", etc.
      messages: \[{ role: 'user', content: 'Explain quantum computing' }\]
  });
  console.log(result.choices\[0\].message.content);
</script\>

Notes:

-   The JS client is distributed via the g4f.dev CDN for easy usage. Review CORS considerations and usage limits.

* * *

Providers & models (overview)
-----------------------------

-   GPT4Free integrates many providers including (but not limited to) OpenAI-compatible endpoints, PerplexityLabs, Gemini, MetaAI, Pollinations (media), and local inference backends.
-   Model availability and behavior depend on provider capabilities. See the providers doc for current, supported provider/model lists: https://g4f.dev/docs/providers-and-models

Provider requirements may include:

-   API keys or tokens (for authenticated providers)
-   Browser cookies / HAR files for providers scraped via browser automation
-   Chrome/Chromium or headless browser tooling
-   Local model binaries and runtime (for local inference)

* * *

Local inference & media
-----------------------

-   GPT4Free supports local inference backends. See docs/local.md for supported runtimes and hardware guidance.
-   Media generation (image, audio, video) is supported through providers (e.g., Pollinations). See docs/media.md for formats, options, and sample usage.

* * *

Configuration & customization
-----------------------------

-   Configure via environment variables, CLI flags, or config files. See docs/config.md.
-   To reduce install size, use partial requirement groups. See docs/requirements.md.
-   Provider selection: learn how to set defaults and override per-request at docs/selecting\_a\_provider.md.
-   Persistence: HAR files, cookies, and generated media persist in mapped directories (e.g., har\_and\_cookies, generated\_media).

* * *

Running on smartphone
---------------------

-   The web GUI is responsive and can be accessed from a phone by visiting your host IP:8080 or via a tunnel. See docs/guides/phone.md.

* * *

Interference API (OpenAI‑compatible)
------------------------------------

-   The Interference API enables OpenAI-like workflows routed through GPT4Free provider selection.
-   Docs: docs/interference-api.md
-   Default endpoint (example slim docker): `http://localhost:1337/v1`
-   Swagger UI: `http://localhost:1337/docs`

* * *

Examples & common patterns
--------------------------

-   Streaming completions, stopping criteria, system messages, and tool-calling patterns are documented in:
    -   docs/client.md
    -   docs/async\_client.md
    -   docs/requests.md
-   Integrations (LangChain, PydanticAI): docs/pydantic\_ai.md
-   Legacy examples: docs/legacy.md

* * *

Contributing
------------

Contributions are welcome — new providers, features, docs, and fixes are appreciated.

How to contribute:

1.  Fork the repository.
2.  Create a branch for your change.
3.  Run tests and linters.
4.  Open a Pull Request with a clear description and tests/examples if applicable.

Repository: https://github.com/xtekky/gpt4free

### How to create a new provider

-   Read the guide: docs/guides/create\_provider.md
-   Typical steps:
    -   Implement a provider adapter in `g4f/Provider/`
    -   Add configuration and dependency notes
    -   Include tests and usage examples
    -   Respect third‑party code licenses and attribute appropriately

### How AI can help you write code

-   See: docs/guides/help\_me.md for prompt templates and workflows to accelerate development.

* * *

Security, privacy & takedown policy
-----------------------------------

-   Do not store or share sensitive credentials. Use per-provider recommended security practices.
-   If your site appears in the project’s links and you want it removed, send proof of ownership to takedown@g4f.ai and it will be removed promptly.
-   For production, secure the server with HTTPS, authentication, and firewall rules. Limit access to provider credentials and cookie/HAR storage.

* * *

Credits, contributors & attribution
-----------------------------------

-   Core creators: @xtekky (original), maintained by @hlohaus.
-   Full contributor graph: https://github.com/xtekky/gpt4free/graphs/contributors
-   Notable code inputs and attributions:
    -   `har_file.py` — input from xqdoo00o/ChatGPT-to-API
    -   `PerplexityLabs.py` — input from nathanrchn/perplexityai
    -   `Gemini.py` — input from dsdanielpark/Gemini-API and HanaokaYuzu/Gemini-API
    -   `MetaAI.py` — inspired by meta-ai-api by Strvm
    -   `proofofwork.py` — input from missuo/FreeGPT35

Many more contributors are acknowledged in the repository.

* * *

Powered-by highlights
---------------------

-   Pollinations AI — generative media: https://github.com/pollinations/pollinations
-   MoneyPrinter V2 — example project using GPT4Free: https://github.com/FujiwaraChoki/MoneyPrinterV2
-   For a full list of projects and sites using GPT4Free, see: docs/powered-by.md

* * *

Changelog & releases
--------------------

-   Releases and full changelog: https://github.com/xtekky/gpt4free/releases
-   Subscribe to Discord/Telegram for announcements.

* * *

Manifesto / Project principles
------------------------------

GPT4Free is guided by community principles:

1.  Open access to AI tooling and models.
2.  Collaboration across providers and projects.
3.  Opposition to monopolistic, closed systems that restrict creativity.
4.  Community-centered development and broad access to AI technologies.
5.  Promote innovation, creativity, and accessibility.

https://g4f.dev/manifest

* * *

License
-------

This program is licensed under the GNU General Public License v3.0 (GPLv3). See the full license: https://www.gnu.org/licenses/gpl-3.0.txt

Summary:

-   You may redistribute and/or modify under the terms of GPLv3.
-   The program is provided WITHOUT ANY WARRANTY.

Copyright notice

```
xtekky/gpt4free: Copyright (C) 2025 xtekky

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
```

* * *

Contact & sponsorship
---------------------

-   Maintainers: https://github.com/hlohaus
-   Sponsorship: https://github.com/sponsors/hlohaus
-   Issues & feature requests: https://github.com/xtekky/gpt4free/issues
-   Takedown requests: takedown@g4f.ai

* * *

Appendix: Quick commands & examples
-----------------------------------

Install (pip):

pip install -U g4f\[all\]

Run GUI (Python):

python -m g4f.cli gui --port 8080 --debug
# or
python -c "from g4f.gui import run\_gui; run\_gui()"

Docker (full):

docker pull hlohaus789/g4f
docker run -p 8080:8080 -p 7900:7900 \\
  --shm-size="2g" \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_media:/app/generated\_media \\
  hlohaus789/g4f:latest

Docker (slim):

docker run -p 1337:8080 -p 8080:8080 \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_media:/app/generated\_media \\
  hlohaus789/g4f:latest-slim

Python usage patterns:

-   `client.chat.completions.create(...)`
-   `client.images.generate(...)`
-   Async variants via `AsyncClient`

Docs & deeper reading

-   Full docs: https://g4f.dev/docs
-   Client API docs: https://g4f.dev/docs/client
-   Async client docs: https://g4f.dev/docs/async\_client
-   Provider guides: https://g4f.dev/docs/guides
-   Local inference: https://g4f.dev/docs/local

* * *

Thank you for using and contributing to GPT4Free — together we make powerful AI tooling accessible, flexible, and community-driven.
