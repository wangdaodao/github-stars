---
project: screenshot-to-code
stars: 70045
description: Drop in a screenshot and convert it to clean code (HTML/Tailwind/React/Vue)
url: https://github.com/abi/screenshot-to-code
---

screenshot-to-code
==================

A simple tool to convert screenshots, mockups and Figma designs into clean, functional code using AI. Now supporting Claude Sonnet 3.7!

Youtube.Clone.mp4

Supported stacks:

-   HTML + Tailwind
-   HTML + CSS
-   React + Tailwind
-   Vue + Tailwind
-   Bootstrap
-   Ionic + Tailwind
-   SVG

Supported AI models:

-   Claude Sonnet 3.7 - Best model!
-   GPT-4o - also recommended!
-   DALL-E 3 or Flux Schnell (using Replicate) for image generation

See the Examples section below for more demos.

We also just added experimental support for taking a video/screen recording of a website in action and turning that into a functional prototype.

Learn more about video here.

Follow me on Twitter for updates.

🌍 Hosted Version
-----------------

Try it live on the hosted version (paid).

🛠 Getting Started
------------------

The app has a React/Vite frontend and a FastAPI backend.

Keys needed:

-   OpenAI API key with access to GPT-4 or Anthropic key (optional)
-   Both are recommended so you can compare results from both Claude and GPT4o

If you'd like to run the app with Ollama open source models (not recommended due to poor quality results), follow this comment.

Run the backend (I use Poetry for package management - `pip install poetry` if you don't have it):

cd backend
echo "OPENAI\_API\_KEY=sk-your-key" \> .env
echo "ANTHROPIC\_API\_KEY=your-key" \> .env
poetry install
poetry shell
poetry run uvicorn main:app --reload --port 7001

You can also set up the keys using the settings dialog on the front-end (click the gear icon after loading the frontend).

Run the frontend:

cd frontend
yarn
yarn dev

Open http://localhost:5173 to use the app.

If you prefer to run the backend on a different port, update VITE\_WS\_BACKEND\_URL in `frontend/.env.local`

For debugging purposes, if you don't want to waste GPT4-Vision credits, you can run the backend in mock mode (which streams a pre-recorded response):

MOCK=true poetry run uvicorn main:app --reload --port 7001

Docker
------

If you have Docker installed on your system, in the root directory, run:

echo "OPENAI\_API\_KEY=sk-your-key" \> .env
docker-compose up -d --build

The app will be up and running at http://localhost:5173. Note that you can't develop the application with this setup as the file changes won't trigger a rebuild.

🙋‍♂️ FAQs
----------

-   **I'm running into an error when setting up the backend. How can I fix it?** Try this. If that still doesn't work, open an issue.
-   **How do I get an OpenAI API key?** See https://github.com/abi/screenshot-to-code/blob/main/Troubleshooting.md
-   **How can I configure an OpenAI proxy?** - If you're not able to access the OpenAI API directly (due to e.g. country restrictions), you can try a VPN or you can configure the OpenAI base URL to use a proxy: Set OPENAI\_BASE\_URL in the `backend/.env` or directly in the UI in the settings dialog. Make sure the URL has "v1" in the path so it should look like this: `https://xxx.xxxxx.xxx/v1`
-   **How can I update the backend host that my front-end connects to?** - Configure VITE\_HTTP\_BACKEND\_URL and VITE\_WS\_BACKEND\_URL in front/.env.local For example, set VITE\_HTTP\_BACKEND\_URL=http://124.10.20.1:7001
-   **Seeing UTF-8 errors when running the backend?** - On windows, open the .env file with notepad++, then go to Encoding and select UTF-8.
-   **How can I provide feedback?** For feedback, feature requests and bug reports, open an issue or ping me on Twitter.

📚 Examples
-----------

**NYTimes**

Original

Replica

**Instagram page (with not Taylor Swift pics)**

instagram.taylor.swift.take.1.mp4

**Hacker News** but it gets the colors wrong at first so we nudge it

hacker.news.with.edits.mp4
