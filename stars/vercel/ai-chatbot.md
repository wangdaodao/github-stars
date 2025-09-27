---
project: ai-chatbot
stars: 18160
description: A full-featured, hackable Next.js AI chatbot built by Vercel
url: https://github.com/vercel/ai-chatbot
---

Chat SDK
========

Chat SDK is a free, open-source template built with Next.js and the AI SDK that helps you quickly build powerful chatbot applications.

**Read Docs** · **Features** · **Model Providers** · **Deploy Your Own** · **Running locally**

  

Features
--------

-   Next.js App Router
    -   Advanced routing for seamless navigation and performance
    -   React Server Components (RSCs) and Server Actions for server-side rendering and increased performance
-   AI SDK
    -   Unified API for generating text, structured objects, and tool calls with LLMs
    -   Hooks for building dynamic chat and generative user interfaces
    -   Supports xAI (default), OpenAI, Fireworks, and other model providers
-   shadcn/ui
    -   Styling with Tailwind CSS
    -   Component primitives from Radix UI for accessibility and flexibility
-   Data Persistence
    -   Neon Serverless Postgres for saving chat history and user data
    -   Vercel Blob for efficient file storage
-   Auth.js
    -   Simple and secure authentication

Model Providers
---------------

This template uses the Vercel AI Gateway to access multiple AI models through a unified interface. The default configuration includes xAI models (`grok-2-vision-1212`, `grok-3-mini`) routed through the gateway.

### AI Gateway Authentication

**For Vercel deployments**: Authentication is handled automatically via OIDC tokens.

**For non-Vercel deployments**: You need to provide an AI Gateway API key by setting the `AI_GATEWAY_API_KEY` environment variable in your `.env.local` file.

With the AI SDK, you can also switch to direct LLM providers like OpenAI, Anthropic, Cohere, and many more with just a few lines of code.

Deploy Your Own
---------------

You can deploy your own version of the Next.js AI Chatbot to Vercel with one click:

Running locally
---------------

You will need to use the environment variables defined in `.env.example` to run Next.js AI Chatbot. It's recommended you use Vercel Environment Variables for this, but a `.env` file is all that is necessary.

> Note: You should not commit your `.env` file or it will expose secrets that will allow others to control access to your various AI and authentication provider accounts.

1.  Install Vercel CLI: `npm i -g vercel`
2.  Link local instance with Vercel and GitHub accounts (creates `.vercel` directory): `vercel link`
3.  Download your environment variables: `vercel env pull`

pnpm install
pnpm dev

Your app template should now be running on localhost:3000.
