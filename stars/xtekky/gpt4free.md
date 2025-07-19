---
project: gpt4free
stars: 64676
description: The official gpt4free repository | various collection of powerful language models | o4, o3 and deepseek r1, gpt-4.1, gemini 2.5
url: https://github.com/xtekky/gpt4free
---

* * *

**Created by @xtekky, maintained by @hlohaus**

Support the project on GitHub Sponsors ❤️

Important

**GPT4Free Manifesto**

We live in a time where access to information and technology is increasingly restricted. Large corporations seek to monopolize control over their models, subjecting essential resources to strict terms of service and opaque practices. But we are here to stand against this tide.

We declare:

1.  **Open Access:** Developing software and utilizing AI models is not illegal. It is a basic right that belongs to everyone. The notion that developing or using AI for purposes outside of what large companies dictate constitutes a legal violation is not only incorrect, but it is also an attack on creativity and innovation.
    
2.  **Collaboration Over Isolation:** Instead of monopolizing a platform through enclosure, we should connect various models together. Only through collaboration can we make the benefits of AI accessible to all and foster diversity and progress.
    
3.  **Against Privatization:** The privatization and isolation of models by large companies is not only dishonest but also unethical. It hinders progress and innovation while restricting developers' and users' opportunities. We rise against this form of market dominance.
    
4.  **For the Community:** Let’s build a community that promotes the free exchange of ideas and technologies. An effective and just system must reflect the diversity of voices and perspectives.
    
5.  **Unleashing Creativity:** We firmly believe that the true value of AI lies in its ability to solve problems, support, and inspire. Let us not be held back by restrictive practices.
    

In this spirit, we proclaim: The future of AI does not belong to a few giant corporations; it belongs to each and every one of us. Let’s work together to create a space where innovation can flourish, and where everyone has access to the tools they need to express themselves and grow.

Note

Together, we will shape an open, inclusive, and more just digital world. 🤗

> **Latest version:**  
>   
> **Stats:**  

pip install -U g4f\[all\]

docker pull hlohaus789/g4f

🆕 What's New
-------------

-   **Explore the latest features and updates**  
    Find comprehensive details on our Releases Page.
    
-   **Stay updated with our Telegram Channel** 📨  
    Join us at telegram.me/g4f\_channel.
    
-   **Subscribe to our Discord News Channel** 💬🆕️  
    Stay informed about updates via our News Channel: discord.gg/5E39JUWUFa.
    
-   **Get support in our Discord Community** 🤝💻  
    Reach out for help in our Support Group: discord.gg/qXA4Wf4Fsm.
    
-   **Read our Documentation** 📖  
    Find detailed guidance and resources at g4f.dev/docs.
    

🔻 Site Takedown
----------------

Is your site on this repository and you want to take it down? Send an email to takedown@g4f.ai with proof it is yours and it will be removed as fast as possible. To prevent reproduction please secure your API. 😉

🚀 **Experience Live G4F**
--------------------------

Want to see G4F in action? Explore a live demo now!

tablet2.webm

Curious to see what G4F can do? Dive into a live demonstration and visit the official g4f.dev homepage for more.

* * *

📚 Table of Contents
--------------------

-   🆕 What's New
-   📚 Table of Contents
-   ⚡ Getting Started
    -   🛠 Installation
        -   🐳 Using Docker
        -   🪟 Windows Guide (.exe)
        -   🐍 Python Installation
-   💡 Usage
    -   📝 Text Generation
    -   🎨 Image Generation
    -   🌐 Web Interface
    -   🖥️ Local Inference
    -   🤖 Interference API
    -   🛠️ Configuration
    -   📱 Run on Smartphone
    -   📘 Full Documentation for Python API
-   🚀 Providers and Models
-   🔗 Powered by gpt4free
-   🤝 Contribute
    -   How do i create a new Provider?
    -   How can AI help me with writing code?
-   🙌 Contributors
-   ©️ Copyright
-   ⭐ Star History
-   📄 License

* * *

⚡️ Getting Started
------------------

🛠 Installation
---------------

### 🐳 Using Docker

1.  **Install Docker:** Download and install Docker.
2.  **Set Up Directories:** Before running the container, make sure the necessary data directories exist or can be created. For example, you can create and set ownership on these directories by running:

mkdir -p ${PWD}/har\_and\_cookies ${PWD}/generated\_media
sudo chown -R 1200:1201 ${PWD}/har\_and\_cookies ${PWD}/generated\_media

1.  **Run the Docker Container:** Use the following commands to pull the latest image and start the container (Only x64):

docker pull hlohaus789/g4f
docker run -p 8080:8080 -p 7900:7900 \\
  --shm-size="2g" \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_media:/app/generated\_media \\
  hlohaus789/g4f:latest

1.  **Running the Slim Docker Image:** And use the following commands to run the Slim Docker image. This command also updates the `g4f` package at startup and installs any additional dependencies: (x64 and arm64)

mkdir -p ${PWD}/har\_and\_cookies ${PWD}/generated\_media
chown -R 1000:1000 ${PWD}/har\_and\_cookies ${PWD}/generated\_media
docker run \\
  -p 1337:8080 -p 8080:8080 \\
  -v ${PWD}/har\_and\_cookies:/app/har\_and\_cookies \\
  -v ${PWD}/generated\_media:/app/generated\_media \\
  hlohaus789/g4f:latest-slim

1.  **Access the Client Interface:**
    
    -   **To use the included client, navigate to:** http://localhost:8080/chat/
    -   **Or set the API base for your client to:** http://localhost:8080/v1
2.  **(Optional) Provider Login:** If required, you can access the container's desktop here: http://localhost:7900/?autoconnect=1&resize=scale&password=secret for provider login purposes.
    

* * *

### 🪟 Windows Guide (.exe)

To ensure the seamless operation of our application, please follow the instructions below. These steps are designed to guide you through the installation process on Windows operating systems.

**Installation Steps:**

1.  **Download the Application**: Visit our releases page and download the most recent version of the application, named `g4f.exe.zip`.
2.  **File Placement**: After downloading, locate the `.zip` file in your Downloads folder. Unpack it to a directory of your choice on your system, then execute the `g4f.exe` file to run the app.
3.  **Open GUI**: The app starts a web server with the GUI. Open your favorite browser and navigate to http://localhost:8080/chat/ to access the application interface.
4.  **Firewall Configuration (Hotfix)**: Upon installation, it may be necessary to adjust your Windows Firewall settings to allow the application to operate correctly. To do this, access your Windows Firewall settings and allow the application.

By following these steps, you should be able to successfully install and run the application on your Windows system. If you encounter any issues during the installation process, please refer to our Issue Tracker or try to get contact over Discord for assistance.

* * *

### 🐍 Python Installation

#### Prerequisites:

1.  Install Python 3.10+ from python.org.
2.  Install Google Chrome for certain providers.

#### Install with PyPI:

pip install -U g4f\[all\]

> How do I install only parts or do disable parts? **Use partial requirements:** /docs/requirements

#### Install from Source:

git clone https://github.com/xtekky/gpt4free.git
cd gpt4free
pip install -r requirements.txt

> How do I load the project using git and installing the project requirements? **Read this tutorial and follow it step by step:** /docs/git

* * *

💡 Usage
--------

### 📝 Text Generation

from g4f.client import Client

client \= Client()
response \= client.chat.completions.create(
    model\="gpt-4o-mini",
    messages\=\[{"role": "user", "content": "Hello"}\],
    web\_search\=False
)
print(response.choices\[0\].message.content)

```
Hello! How can I assist you today?
```

### 🎨 Image Generation

from g4f.client import Client

client \= Client()
response \= client.images.generate(
    model\="flux",
    prompt\="a white siamese cat",
    response\_format\="url"
)

print(f"Generated image URL: {response.data\[0\].url}")

### 🌐 Web Interface

**Run the GUI using Python:**

from g4f.gui import run\_gui

run\_gui()

**Run via CLI (To start the Flask Server):**

python -m g4f.cli gui --port 8080 --debug

**Or, start the FastAPI Server:**

python -m g4f --port 8080 --debug

> **Learn More About the GUI:** For detailed instructions on how to set up, configure, and use the GPT4Free GUI, refer to the GUI Documentation . This guide includes step-by-step details on provider selection, managing conversations, using advanced features like speech recognition, and more.

* * *

### 🤖 Inference API

The **Inference API** enables seamless integration with OpenAI's services through G4F, allowing you to deploy efficient AI solutions.

-   **Documentation**: Inference API Docs
-   **Endpoint**: `http://localhost:1337/v1`
-   **Swagger UI**: Explore the OpenAPI documentation via Swagger UI at `http://localhost:1337/docs`
-   **Provider Selection**: How to Specify a Provider?

This API is designed for straightforward implementation and enhanced compatibility with other OpenAI integrations.

* * *

### 📱 Run on Smartphone

Run the Web UI on your smartphone for easy access on the go. Check out the dedicated guide to learn how to set up and use the GUI on your mobile device: Run on Smartphone Guide

* * *

#### **📘 Full Documentation for Python API**

-   **Client API from G4F:** /docs/client
-   **AsyncClient API from G4F:** /docs/async\_client
-   **Requests API from G4F:** /docs/requests
-   **File API from G4F:** /docs/file
-   **PydanticAI and LangChain Integration for G4F:** /docs/pydantic\_ai
-   **Legacy API with python modules:** /docs/legacy
-   **G4F - Media Documentation (Image, Audio and Video)** /docs/media _(New)_

* * *

### Powered by Pollinations AI

**🌟 Pollinations AI**

A creative AI content platform that generates images, audios, and other media using advanced generative models. Pollinations AI empowers users and developers to turn text into visuals and multimedia experiences.

> pollinations/pollinations on GitHub

* * *

### Powered by GPT4Free

**💸 MoneyPrinter**

MoneyPrinter V2 cranks up the automation for making money online. It’s a complete overhaul of the original MoneyPrinter, rebuilt from the ground up for more features and a plug-and-play, modular design. MPV2 takes the grind and guesswork out of online income: just set it up, let it run, and watch your earnings stack.

> FujiwaraChoki/MoneyPrinterV2 on GitHub

> Full list of GPT4Free powered sites and tools

🤝 Contribute
-------------

We welcome contributions from the community. Whether you're adding new providers or features, or simply fixing typos and making small improvements, your input is valued. Creating a pull request is all it takes – our co-pilot will handle the code review process. Once all changes have been addressed, we'll merge the pull request into the main branch and release the updates at a later time.

###### Guide: How do i create a new Provider?

-   **Read:** Create Provider Guide

###### Guide: How can AI help me with writing code?

-   **Read:** AI Assistance Guide

Contributors
------------

A list of all contributors is available here

-   The `Vercel.py` file contains code from vercel-llm-api by @ading2210
-   The `har_file.py` has input from xqdoo00o/ChatGPT-to-API
-   The `PerplexityLabs.py` has input from nathanrchn/perplexityai
-   The `Gemini.py` has input from dsdanielpark/Gemini-API
-   The `MetaAI.py` file contains code from meta-ai-api by @Strvm
-   The `proofofwork.py` has input from missuo/FreeGPT35
-   The `Gemini.py` has input from HanaokaYuzu/Gemini-API

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
