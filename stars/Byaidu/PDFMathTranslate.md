---
project: PDFMathTranslate
stars: 10067
description: PDF scientific paper translation with preserved formats - 基于 AI 完整保留排版的 PDF 文档全文双语翻译，支持 Google/DeepL/Ollama/OpenAI 等服务，提供 CLI/GUI/Docker
url: https://github.com/Byaidu/PDFMathTranslate
---

English | 简体中文 | 日本語

PDFMathTranslate
----------------

PDF scientific paper translation and bilingual comparison.

-   📊 Preserve formulas, charts, table of contents, and annotations _(preview)_.
-   🌐 Support multiple languages, and diverse translation services.
-   🤖 Provides commandline tool, interactive user interface, and Docker

Feel free to provide feedback in GitHub Issues, Telegram Group or QQ Group.

Updates
-------

-   \[Dec. 19 2024\] Non-PDF/A documents are now supported using `-cp` _(by @reycn)_
-   \[Dec. 13 2024\] Additional support for backend by _(by @YadominJinta)_
-   \[Dec. 10 2024\] The translator now supports OpenAI models on Azure _(by @yidasanqian)_

Preview
-------

Online Service 🌟
-----------------

You can try our application out using either of the following demos:

-   Public free service online without installation _(recommended)_.
-   Demo hosted on HuggingFace
-   Demo hosted on ModelScope without installation.

Note that the computing resources of the demo are limited, so please avoid abusing them.

Installation and Usage
----------------------

### Methods

For different use cases, we provide four distinct methods to use our program:

1\. Commandline

1.  Python installed (3.8 <= version <= 3.12)
    
2.  Install our package:
    
    pip install pdf2zh
    
3.  Execute translation, files generated in current working directory:
    
    pdf2zh document.pdf
    

2\. Portable (w/o Python installed)

1.  Download setup.bat
    
2.  Double-click to run.
    

3\. Graphic user interface 1. Python installed (3.8 <= version <= 3.12) 2. Install our package:

pip install pdf2zh

1.  Start using in browser:
    
    pdf2zh -i
    
2.  If your browswer has not been started automatically, goto
    
    http://localhost:7860/
    

See documentation for GUI for more details.

4\. Docker

1.  Pull and run:
    
    docker pull byaidu/pdf2zh
    docker run -d -p 7860:7860 byaidu/pdf2zh
    
2.  Open in browser:
    
    ```
    http://localhost:7860/
    ```
    

For docker deployment on cloud service:

### Unable to install?

The present program needs an AI model(`wybxc/DocLayout-YOLO-DocStructBench-onnx`) before working and some users are not able to download due to network issues. If you have a problem with downloading this model, we provide a workaround using the following environment variable:

set HF\_ENDPOINT=https://hf-mirror.com

If the solution does not work to you / you encountered other issues, please refer to frequently asked questions.

Advanced Options
----------------

Execute the translation command in the command line to generate the translated document `example-mono.pdf` and the bilingual document `example-dual.pdf` in the current working directory. Use Google as the default translation service.

In the following table, we list all advanced options for reference:

Option

Function

Example

files

Local files

`pdf2zh ~/local.pdf`

links

Online files

`pdf2zh http://arxiv.org/paper.pdf`

`-i`

Enter GUI

`pdf2zh -i`

`-p`

Partial document translation

`pdf2zh example.pdf -p 1`

`-li`

Source language

`pdf2zh example.pdf -li en`

`-lo`

Target language

`pdf2zh example.pdf -lo zh`

`-s`

Translation service

`pdf2zh example.pdf -s deepl`

`-t`

Multi-threads

`pdf2zh example.pdf -t 1`

`-o`

Output dir

`pdf2zh example.pdf -o output`

`-f`, `-c`

Exceptions

`pdf2zh example.pdf -f "(MS.*)"`

`-cp`

Compatibility Mode

`pdf2zh example.pdf --compatible`

`--share`

Public link

`pdf2zh -i --share`

`--authorized`

Authorization

`pdf2zh -i --authorized users.txt [auth.html]`

`--prompt`

Custom Prompt

`pdf2zh --prompt [prompt.txt]`

For detailed explanations, please refer to our document about Advanced Usage for a full list of each option.

Secondary Development (APIs)
----------------------------

For downstream applications, please refer to our document about API Details for futher information about:

-   Python API, how to use the program in other Python programs
-   HTTP API, how to communicate with a server with the program installed

TODOs
-----

-   Parse layout with DocLayNet based models, PaddleX, PaperMage, SAM2
    
-   Fix page rotation, table of contents, format of lists
    
-   Fix pixel formula in old papers
    
-   Async retry except KeyboardInterrupt
    
-   Knuth–Plass algorithm for western languages
    
-   Support non-PDF/A files
    
-   Plugins of Zotero and Obsidian
    

Acknowledgements
----------------

-   Document merging: PyMuPDF
    
-   Document parsing: Pdfminer.six
    
-   Document extraction: MinerU
    
-   Document Preview: Gradio PDF
    
-   Multi-threaded translation: MathTranslate
    
-   Layout parsing: DocLayout-YOLO
    
-   Document standard: PDF Explained, PDF Cheat Sheets
    
-   Multilingual Font: Go Noto Universal
    

Contributors
------------

Star History
------------