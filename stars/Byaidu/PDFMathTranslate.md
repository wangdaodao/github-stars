---
project: PDFMathTranslate
stars: 29255
description: [EMNLP 2025 Demo] PDF scientific paper translation with preserved formats - 基于 AI 完整保留排版的 PDF 文档全文双语翻译，支持 Google/DeepL/Ollama/OpenAI 等服务，提供 CLI/GUI/MCP/Docker/Zotero
url: https://github.com/Byaidu/PDFMathTranslate
---

English | 简体中文 | 繁體中文 | 日本語 | 한국어

PDFMathTranslate
----------------

1\. What does this do?
----------------------

Scientific PDF document translation preserving layouts.

-   📊 Preserve formulas, charts, table of contents, and annotations.
-   🌐 Support multiple languages, and diverse translation services.
-   🤖 Provides commandline tool, interactive user interface, and Docker

2\. Recent Updates
------------------

-   \[May 9, 2025\] pdf2zh 2.0 Preview Version #586: The Windows ZIP file and Docker image are now available.
    
    > \[!NOTE\]
    > 
    > 2.0 Moved to a new repository under the organization: PDFMathTranslate/PDFMathTranslate-next
    > 
    > Version 2.0 official release has been published.
    
-   \[Mar. 3, 2025\] Experimental support for the new backend BabelDOC WebUI added as an experimental option (by @awwaawwa)
    
-   \[Feb. 22 2025\] Better release CI and well-packaged windows-amd64 exe (by @awwaawwa)
    

3\. Use 🌟
----------

### 3.1 Online Service 🌟

You can try our application out using either of the following demos:

-   Public free service online without installation _(recommended)_.
-   Immersive Translate - BabelDOC 1000 free pages per month. _(recommended)_
-   Demo hosted on HuggingFace
-   Demo hosted on ModelScope without installation.

Note that the computing resources of the demo are limited, so please avoid abusing them.

### 3.2 Local Installation

For different use cases, we provide distinct methods to use our program:

3.2.1 Python: Install using uv

1.  Python installed (3.10 <= version <= 3.12)
    
2.  Install our package:
    
    pip install uv
    uv tool install --python 3.12 pdf2zh
    
3.  Execute translation, files generated in current working directory:
    
    pdf2zh document.pdf
    

3.2.2 Python: Install using pip

1.  Python installed (3.10 <= version <= 3.12)
    
2.  Install our package:
    
    pip install pdf2zh
    
3.  Execute translation, files generated in current working directory:
    
    pdf2zh document.pdf
    

3.3.3 Python: Graphic user interface

1.  Python installed (3.10 <= version <= 3.12)
    
2.  Install our package:
    

pip install pdf2zh

1.  Start using in browser:
    
    pdf2zh -i
    
2.  If your browser has not been started automatically, goto
    
    http://localhost:7860/
    

See documentation for GUI for more details.

3.2.4 Application: On Windows

1.  Download pdf2zh-version-win64.zip from release page
    
2.  Unzip and double-click `pdf2zh.exe` to run.
    

> \[!TIP\]
> 
> -   If you're using Windows and cannot open the file after downloading, please install vc\_redist.x64.exe and try again.

3.2.5 Reference manager: Zotero Plugin

See Zotero PDF2zh for more details.

3.2.6 Docker: Containerized Deployment

1.  Pull and run:
    
    docker pull byaidu/pdf2zh
    docker run -d -p 7860:7860 byaidu/pdf2zh
    
2.  Open in browser:
    
    ```
    http://localhost:7860/
    ```
    

For docker deployment on cloud service:

> \[!TIP\]
> 
> -   If you cannot access Docker Hub, please try the image on GitHub Container Registry.
> 
> docker pull ghcr.io/byaidu/pdfmathtranslate
> docker run -d -p 7860:7860 ghcr.io/byaidu/pdfmathtranslate

3.2.\* Solutions for network issues in installation

Users in specific regions may encounter network difficulties when loading the AI model. The current program relies on the AI model (`wybxc/DocLayout-YOLO-DocStructBench-onnx`), and some users are unable to download it due to these network issues.

To address issues with downloading this model, use the following environment variable as a workaround:

set HF\_ENDPOINT=https://hf-mirror.com

For PowerShell user:

$env:HF\_ENDPOINT = https://hf-mirror.com

If the solution does not work to you / you encountered other issues, please refer to Frequently Asked Questions.

4\. Technical Details
---------------------

### 4.1 Advanced options

Execute the translation command in the command line to generate the translated document `example-mono.pdf` and the bilingual document `example-dual.pdf` in the current working directory. Use Google as the default translation service. More support translation services can find HERE.

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

`--skip-subset-fonts`

Skip font subset

`pdf2zh example.pdf --skip-subset-fonts`

`--ignore-cache`

Ignore translate cache

`pdf2zh example.pdf --ignore-cache`

`--share`

Public link

`pdf2zh -i --share`

`--authorized`

Authorization

`pdf2zh -i --authorized users.txt [auth.html]`

`--prompt`

Custom Prompt

`pdf2zh --prompt [prompt.txt]`

`--onnx`

\[Use Custom DocLayout-YOLO ONNX model\]

`pdf2zh --onnx [onnx/model/path]`

`--serverport`

\[Use Custom WebUI port\]

`pdf2zh --serverport 7860`

`--dir`

\[batch translate\]

`pdf2zh --dir /path/to/translate/`

`--config`

configuration file

`pdf2zh --config /path/to/config/config.json`

`--serverport`

\[custom gradio server port\]

`pdf2zh --serverport 7860`

`--babeldoc`

Use Experimental backend BabelDOC to translate

`pdf2zh --babeldoc` -s openai example.pdf

`--mcp`

Enable MCP STDIO mode

`pdf2zh --mcp`

`--sse`

Enable MCP SSE mode

`pdf2zh --mcp --sse`

For detailed explanations, please refer to our document about Advanced Usage for a full list of each option.

### 4.2 Downstream Development

For downstream applications, please refer to our document about \[API Details\](./docs/APIS.md) for further information about:

-   Python API, how to use the program in other Python programs
-   HTTP API, how to communicate with a server with the program installed

### 4.3 Differences between two major forks

-   Byaidu/PDFMathTranslate: The present and the original project for stable release.
    
-   PDFMathTranslate/PDFMathTranslate-next: A fork with web-ui and additional features. This fork handles a large number of marginal cases, improves PDF compatibility, and optimizes cross-column and cross-page semantic consistency, dynamic scaling, and dynamic scaling consistency, among many other translation quality improvements. However, this fork is intended solely for development and does not address compatibility issues and is not designed for community-contributions.
    

5\. Project Information
-----------------------

### 5.1 Citation

This work has been accepted by the _Proceedings of the 2025 Conference on Empirical Methods in Natural Language Processing: System Demonstrations_ (EMNLP 2025).

-   Pre-print version: PDFMathTranslate: Scientific Document Translation Preserving Layouts
    
    ```
    @online{ouyang2025pdfmathtranslate,
      title = {{{PDFMathTranslate}}: {{Scientific Document Translation Preserving Layouts}}},
      shorttitle = {{{PDFMathTranslate}}},
      author = {Ouyang, Rongxin and Chu, Chang and Xin, Zhikuang and Ma, Xiangyao},
      date = {2025-07-08},
      eprint = {2507.03009},
      eprinttype = {arXiv},
      eprintclass = {cs},
      doi = {10.48550/arXiv.2507.03009},
      url = {http://arxiv.org/abs/2507.03009},
      urldate = {2025-08-27},
      pubstate = {prepublished}
    }
    ```
    
-   The citation for the EMNLP proceedings will be provided upon release.
    

### 5.2 Acknowledgement

-   Immersive Translation sponsors monthly Pro membership redemption codes for active contributors to this project, see details at: CONTRIBUTOR\_REWARD.md
    
-   New backend: BabelDOC
    
-   Document merging: PyMuPDF
    
-   Document parsing: Pdfminer.six
    
-   Document extraction: MinerU
    
-   Document Preview: Gradio PDF
    
-   Multi-threaded translation: MathTranslate
    
-   Layout parsing: DocLayout-YOLO
    
-   Document standard: PDF Explained, PDF Cheat Sheets
    
-   Multilingual Font: Go Noto Universal
    

### 5.3 Contributors

For details on how to contribute, please consult the Contribution Guide.

### 5.4 Star History
