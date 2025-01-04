---
project: gpt4free
stars: 62946
description: The official gpt4free repository | various collection of powerful language models
url: https://github.com/xtekky/gpt4free
---

* * *

**Written by @xtekky**

Important

By using this repository or any code related to it, you agree to the legal notice. The author is **not responsible for the usage of this repository nor endorses it**, nor is the author responsible for any copies, forks, re-uploads made by other users, or anything else related to GPT4Free. This is the author's only account and repository. To prevent impersonation or irresponsible actions, please comply with the GNU GPL license this Repository uses.

Warning

_"gpt4free"_ serves as a **PoC** (proof of concept), demonstrating the development of an API package with multi-provider requests, with features like timeouts, load balance and flow control.

Note

**Latest version:**  
**Stats:**

pip install -U g4f\[all\]

docker pull hlohaus789/g4f

🆕 What's New
-------------

-   **For comprehensive details on new features and updates, please refer to our** Releases **page**
-   **Installation Guide for Windows (.exe):** 💻 Installation Guide for Windows (.exe)
-   **Join our Telegram Channel:** 📨 telegram.me/g4f\_channel
-   **Join our Discord Group:** 💬🆕️ https://discord.gg/5E39JUWUFa

🔻 Site Takedown
----------------

Is your site on this repository and you want to take it down? Send an email to takedown@g4f.ai with proof it is yours and it will be removed as fast as possible. To prevent reproduction please secure your API. 😉

🚀 GPT4Free on HuggingFace
--------------------------

Explore our GPT4Free project on HuggingFace Spaces by clicking the link below:

-   Visit GPT4Free on HuggingFace

If you would like to create your own copy of this space, you can duplicate it using the following link:

-   Duplicate GPT4Free Space

📚 Table of Contents
--------------------

-   🆕 What's New
-   📚 Table of Contents
-   🛠️ Getting Started
    -   Docker Container Guide
    -   Installation Guide for Windows (.exe)
-   Use python
    -   Prerequisites
    -   Install using PyPI package
    -   Install from source
-   Install using Docker
-   💡 Usage
    -   Text Generation
    -   Image Generation
    -   Web UI
    -   Interference API
    -   Local Inference
    -   Configuration
    -   Full Documentation for Python API
        -   Requests API from G4F
        -   Client API from G4F
        -   AsyncClient API from G4F
-   🚀 Providers and Models
-   🔗 Powered by gpt4free
-   🤝 Contribute
    -   How do i create a new Provider?
    -   How can AI help me with writing code?
-   🙌 Contributors
-   ©️ Copyright
-   ⭐ Star History
-   📄 License

🛠️ Getting Started
-------------------

#### Docker Container Guide

##### Getting Started Quickly:

1.  **Install Docker:** Begin by downloading and installing Docker.
    
2.  **Check Directories:**
    

Before running the container, make sure the necessary data directories exist or can be created. For example, you can create and set ownership on these directories by running:

mkdir -p ${PWD}/har\_and\_cookies ${PWD}/generated\_images
chown -R 1000:1000 ${PWD}/har\_and\_cookies ${PWD}/generated\_images

1.  **Set Up the Container:** Use the following commands to pull the latest image and start the container:

docker pull hlohaus789/g4f
docker run \\
  -p 8080:8080 -p 1337:1337 -p 7900:7900 \\
  --shm-size="2g" \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_images:/app/generated\_images \\
  hlohaus789/g4f:latest

##### Running the Slim Docker Image

Use the following command to run the Slim Docker image. This command also updates the `g4f` package at startup and installs any additional dependencies:

docker run \\
  -p 1337:1337 \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_images:/app/generated\_images \\
  hlohaus789/g4f:latest-slim \\
  rm -r -f /app/g4f/ \\
  && pip install -U g4f\[slim\] \\
  && python -m g4f --debug

1.  **Access the Client:**
    
    -   To use the included client, navigate to: http://localhost:8080/chat/ or http://localhost:1337/chat/
    -   Or set the API base for your client to: http://localhost:1337/v1
2.  **(Optional) Provider Login:** If required, you can access the container's desktop here: http://localhost:7900/?autoconnect=1&resize=scale&password=secret for provider login purposes.
    

#### Installation Guide for Windows (.exe)

To ensure the seamless operation of our application, please follow the instructions below. These steps are designed to guide you through the installation process on Windows operating systems.

### Installation Steps

1.  **Download the Application**: Visit our releases page and download the most recent version of the application, named `g4f.exe.zip`.
2.  **File Placement**: After downloading, locate the `.zip` file in your Downloads folder. Unpack it to a directory of your choice on your system, then execute the `g4f.exe` file to run the app.
3.  **Open GUI**: The app starts a web server with the GUI. Open your favorite browser and navigate to `http://localhost:8080/chat/` to access the application interface.
4.  **Firewall Configuration (Hotfix)**: Upon installation, it may be necessary to adjust your Windows Firewall settings to allow the application to operate correctly. To do this, access your Windows Firewall settings and allow the application.

By following these steps, you should be able to successfully install and run the application on your Windows system. If you encounter any issues during the installation process, please refer to our Issue Tracker or try to get contact over Discord for assistance.

* * *

### Learn More About the GUI

For detailed instructions on how to set up, configure, and use the GPT4Free GUI, refer to the **GUI Documentation**:

-   GUI Documentation

This guide includes step-by-step details on provider selection, managing conversations, using advanced features like speech recognition, and more.

* * *

### Use Your Smartphone

Run the Web UI on your smartphone for easy access on the go. Check out the dedicated guide to learn how to set up and use the GUI on your mobile device:

-   Run on Smartphone Guide

* * *

### Use python

##### Prerequisites:

1.  Download and install Python (Version 3.10+ is recommended).
2.  Install Google Chrome for providers with webdriver

##### Install using PyPI package:

```
pip install -U g4f[all]
```

How do I install only parts or do disable parts? Use partial requirements: /docs/requirements

##### Install from source:

How do I load the project using git and installing the project requirements? Read this tutorial and follow it step by step: /docs/git

##### Install using Docker:

How do I build and run composer image from source? Use docker-compose: /docs/docker

💡 Usage
--------

#### Text Generation

from g4f.client import Client

client \= Client()
response \= client.chat.completions.create(
    model\="gpt-4o-mini",
    messages\=\[{"role": "user", "content": "Hello"}\],
    web\_search \= False
)
print(response.choices\[0\].message.content)

```
Hello! How can I assist you today?
```

#### Image Generation

from g4f.client import Client

client \= Client()
response \= client.images.generate(
    model\="flux",
    prompt\="a white siamese cat",
    response\_format\="url"
)

image\_url \= response.data\[0\].url
print(f"Generated image URL: {image\_url}")

#### **Full Documentation for Python API**

-   **New:**
    
    -   **Requests API from G4F:** /docs/requests
    -   **Client API from G4F:** /docs/client
    -   **AsyncClient API from G4F:** /docs/async\_client
    -   **File API from G4F:** /docs/file
-   **Legacy:**
    
    -   **Legacy API with python modules:** /docs/legacy

#### Web UI

**To start the web interface, type the following codes in python:**

from g4f.gui import run\_gui

run\_gui()

or execute the following command:

python -m g4f.cli gui -port 8080 -debug

### Interference API

The **Interference API** enables seamless integration with OpenAI's services through G4F, allowing you to deploy efficient AI solutions.

-   **Documentation**: Interference API Docs
-   **Endpoint**: `http://localhost:1337/v1`
-   **Swagger UI**: Explore the OpenAPI documentation via Swagger UI at `http://localhost:1337/docs`

This API is designed for straightforward implementation and enhanced compatibility with other OpenAI integrations.

### Configuration

#### Authentication

Refer to the G4F Authentication Setup Guide for detailed instructions on setting up authentication.

#### Cookies

Cookies are essential for using Meta AI and Microsoft Designer to create images. Additionally, cookies are required for the Google Gemini and WhiteRabbitNeo Provider. From Bing, ensure you have the "\_U" cookie, and from Google, all cookies starting with "\_\_Secure-1PSID" are needed.

You can pass these cookies directly to the create function or set them using the `set_cookies` method before running G4F:

from g4f.cookies import set\_cookies

set\_cookies(".bing.com", {
  "\_U": "cookie value"
})

set\_cookies(".google.com", {
  "\_\_Secure-1PSID": "cookie value"
})

#### Using .har and Cookie Files

You can place `.har` and cookie files `.json` in the default `./har_and_cookies` directory. To export a cookie file, use the EditThisCookie Extension available on the Chrome Web Store.

#### Creating .har Files to Capture Cookies

To capture cookies, you can also create `.har` files. For more details, refer to the next section.

#### Changing the Cookies Directory and Loading Cookie Files in Python

You can change the cookies directory and load cookie files in your Python environment. To set the cookies directory relative to your Python file, use the following code:

import os.path
from g4f.cookies import set\_cookies\_dir, read\_cookie\_files

import g4f.debug
g4f.debug.logging \= True

cookies\_dir \= os.path.join(os.path.dirname(\_\_file\_\_), "har\_and\_cookies")
set\_cookies\_dir(cookies\_dir)
read\_cookie\_files(cookies\_dir)

### Debug Mode

If you enable debug mode, you will see logs similar to the following:

```
Read .har file: ./har_and_cookies/you.com.har
Cookies added: 10 from .you.com
Read cookie file: ./har_and_cookies/google.json
Cookies added: 16 from .google.com
```

#### .HAR File for OpenaiChat Provider

##### Generating a .HAR File

To utilize the OpenaiChat provider, a .har file is required from https://chatgpt.com/. Follow the steps below to create a valid .har file:

1.  Navigate to https://chatgpt.com/ using your preferred web browser and log in with your credentials.
2.  Access the Developer Tools in your browser. This can typically be done by right-clicking the page and selecting "Inspect," or by pressing F12 or Ctrl+Shift+I (Cmd+Option+I on a Mac).
3.  With the Developer Tools open, switch to the "Network" tab.
4.  Reload the website to capture the loading process within the Network tab.
5.  Initiate an action in the chat which can be captured in the .har file.
6.  Right-click any of the network activities listed and select "Save all as HAR with content" to export the .har file.

##### Storing the .HAR File

-   Place the exported .har file in the `./har_and_cookies` directory if you are using Docker. Alternatively, if you are using Python from a terminal, you can store it in a `./har_and_cookies` directory within your current working directory.

> **Note:** Ensure that your .har file is stored securely, as it may contain sensitive information.

#### Using Proxy

If you want to hide or change your IP address for the providers, you can set a proxy globally via an environment variable:

**\- On macOS and Linux:**

export G4F\_PROXY="http://host:port"

**\- On Windows:**

set G4F\_PROXY=http://host:port

🔗 Powered by gpt4free
----------------------

**🎁 Projects**

**⭐ Stars**

**📚 Forks**

**🛎 Issues**

**📬 Pull requests**

**gpt4free**

**gpt4free-ts**

**Free AI API's & Potential Providers List**

**ChatGPT-Clone**

**Ai agent**

**ChatGpt Discord Bot**

**chatGPT-discord-bot**

**Nyx-Bot (Discord)**

**LangChain gpt4free**

**ChatGpt Telegram Bot**

**ChatGpt Line Bot**

**Action Translate Readme**

**Langchain Document GPT**

**python-tgpt**

**GPT4js**

**VividNode (pyqt-openai)**

🤝 Contribute
-------------

We welcome contributions from the community. Whether you're adding new providers or features, or simply fixing typos and making small improvements, your input is valued. Creating a pull request is all it takes – our co-pilot will handle the code review process. Once all changes have been addressed, we'll merge the pull request into the main branch and release the updates at a later time.

###### Guide: How do i create a new Provider?

-   **Read:** Create Provider Guide

###### Guide: How can AI help me with writing code?

-   **Read:** AI Assistance Guide

🙌 Contributors
---------------

A list of all contributors is available here

-   The `Vercel.py` file contains code from vercel-llm-api by @ading2210
-   The `har_file.py` has input from xqdoo00o/ChatGPT-to-API
-   The `PerplexityLabs.py` has input from nathanrchn/perplexityai
-   The `Gemini.py` has input from dsdanielpark/Gemini-API
-   The `MetaAI.py` file contains code from meta-ai-api by @Strvm
-   The `proofofwork.py` has input from missuo/FreeGPT35

_Having input implies that the AI's code generation utilized it as one of many sources._

©️ Copyright
------------

This program is licensed under the GNU GPL v3

```
xtekky/gpt4free: Copyright (C) 2023 xtekky

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

⭐ Star History
--------------

📄 License
----------

  
This project is licensed under GNU\_GPL\_v3.0.

* * *

(🔼 Back to top)
