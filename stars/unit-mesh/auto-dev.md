---
project: auto-dev
stars: 3987
description: 🧙‍AutoDev: The AI-powered coding wizard（AI  驱动编程助手）with multilingual support 🌐, auto code generation 🏗️, and a helpful bug-slaying assistant 🐞! Customizable prompts 🎨 and a magic Auto Dev/Testing/Document/Agent  feature 🧪 included! 🚀
url: https://github.com/unit-mesh/auto-dev
---

AutoDev for Intellij
====================

> 🧙‍AutoDev: The AI-powered coding wizard with multilingual support 🌐, auto code generation 🏗️, and a helpful bug-slaying assistant 🐞! Customizable prompts 🎨 and a magic Auto Dev/Testing/Document/Agent feature 🧪 included! 🚀

AutoDev 2.0 Sketch - the Cursor Composer in Intellij IDEA
---------------------------------------------------------

Video demo (YouTube) — English

**AutoDev Sketch** is an IDE canvas feature provided by Shire, designed to simplify interactions and enhance the developer experience within the IDE.

Sketch Name

Description

Screenshots

**Code Sketch**

Real-time code editor with syntax highlighting

**Diff Sketch**

Diff content comparison tool with patch handling

**Terminal Sketch**

Editable pop-up terminal interface and integration with other sketch, like frontend dev localhost in WebView

**WebView Sketch**

HTML/React/Ionic mockup generator with WebView display

**OpenAPI Sketch`*`**

OpenAPI editor with bidirectional code-OpenAPI synchronization

**Dependency Sketch`*`**

Security-builtin vulnerable dependency checker

**Go Playground Sketch`*`**

Go Playground with bidirectional code preview/edit

**Mermaid Sketch`*`**

Real-time flowchart preview/edit with bidirectional binding

**PlantUML Sketch`*`**

UML diagram editor with bidirectional code-diagram synchronization

**PlanSketch**

Display AutoDev Planner planning for resolving code issues

`*` means requires additional plugin installation.

### Unite Your Dev Ecosystem, Create Your AI Copilot

VSCode Version: https://github.com/unit-mesh/auto-dev-vscode

Quick Start →

🆕🆕🆕: New AI agent language: https://github.com/phodal/shire

### Demos

Video demo (Bilibili) - 中文/Chinese

AutoDev Architecture
--------------------

Here is the AutoDev architecture:

AutoDev 1.0~ Feature Overview
-----------------------------

Features:

-   Sketch coding Agent
    -   Agentic drive coding workflow with Sketch viewer.
-   Auto development mode
    -   AutoCRUD (Spring framework）. With DevTi Protocol (like `devti://story/github/1102`) will auto generate Model-Controller-Service-Repository code.
    -   AutoSQL (required Database plugin). Context-aware SQL generation.
    -   AutoPage (React). Context-aware Web Page generation.
    -   AutoArkUI (HarmonyOS). Auto generate HarmonyOS ArkUI code.
    -   Auto Testing. create unit test intention, auto run unit test and try to fix test.
    -   Auto Document. Auto generate document.
-   Copilot mode
    -   AutoDev will help you find bug, explain code, trace exception, generate commits, and more.
    -   Pattern specific. Based on your code context like (Controller, Service `import`), AutoDev will suggest the best code to you.
    -   Related code. Based on recent file changes, AutoDev will call calculate similar chunk to generate the best code.
-   Chat with AI. Chat with selection code and context-aware code.
-   Customize.
    -   Custom specification of prompt. For example, Controller, Service, Repository, Model, etc.
    -   Custom intention action. You can add your own intention action.
    -   Custom LLM Server. You can customize your LLM Server in `Settings` -> `Tools` -> `AutoDev`
    -   Custom Living documentation. Customize your own living documentation, like annotation.
    -   Team AI. Customize your team prompts in codebase, and distribute to your team.
    -   Prompt override. You can override AutoDev's prompt in your codebase.
-   SDLC
    -   VCS. Generate/improve commit message, release note, and more.
    -   Code Review. Generate code-review content.
    -   Smart Refactoring. AI based Rename, refactoring with code smell, refactoring suggetion and more.
    -   Dockerfile. Based on your project, generate Dockerfile.
    -   CI/CD config. Based on build tool, generate CI/CD config file, like `.github/workflows/build.yml`.
    -   Terminal. In Terminal ToolWindow, you can use custom input to generate shell/command
-   Custom AI Agent
    -   Executable AI Agent language: DevIns.
    -   Custom AI Agent. You can integrate your own AI Agent into AutoDev.
-   Model
    -   Built-in LLM Fine-tune
    -   UnitEval evaluate llm result
    -   UnitGen generate code-llm fine-tune data.

AutoDev fine-tune models:

download from HuggingFace

name

model download (HuggingFace)

model download (OpenBayes)

DeepSeek 6.7B

AutoDev Coder

AutoDev Coder

Language Features
-----------------

### Language Support

We follow Chapi AST analysis engine for language support tier.

Features

Java

Python

Go

Kotlin

JS/TS

C/C++

C#

Scala

Rust

Chat Language Context

✅

✅

✅

✅

✅

✅

✅

Structure AST

✅

✅

✅

✅

✅

Doc Generation

✅

✅

✅

✅

✅

✅

Precision Test Generation

✅

✅

✅

✅

✅

✅

Precision Code Generation

✅

✅

### Extensions

see in exts

Demo
----

DevIns Language demo (Bilibili) - 中文

Video demo (YouTube) — English

Video demo (Bilibili) - 中文

Useful Links
------------

-   Copilot-Explorer Hacky repo to see what the Copilot extension sends to the server.
-   GitHub Copilot a small part of Copilot Performance logs.
-   花了大半个月，我终于逆向分析了Github Copilot

Who is using AutoDev?
---------------------

Welcome to add your company here.

-   Thoughtworks, a leading technology consultancy.

License
-------

Inspired by:

-   Multiple target inspired by: https://github.com/intellij-rust/intellij-rust
-   SimilarFile inspired by: GitHub Copilot
-   DevIn Language refs on JetBrains' Markdown Util, which is licensed under the Apache 2.0 license.
-   Stream Diff based on Continue Dev under the Apache 2.0 license.
-   Ripgrep inspired by Cline under the Apache 2.0 license.
-   MCP based on JetBrains' MCP

This code is distributed under the MPL 2.0 license. See `LICENSE` in this directory.
