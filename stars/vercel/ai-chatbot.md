---
project: ai-chatbot
stars: 10719
description: A full-featured, hackable Next.js AI chatbot built by Vercel
url: https://github.com/vercel/ai-chatbot
---

Next.js AI Chatbot
==================

An Open-Source AI Chatbot Template Built With Next.js and the AI SDK by Vercel.

**Features** · **Model Providers** · **Deploy Your Own** · **Running locally**

  

Features
--------

-   Next.js App Router
    -   Advanced routing for seamless navigation and performance
    -   React Server Components (RSCs) and Server Actions for server-side rendering and increased performance
-   AI SDK
    -   Unified API for generating text, structured objects, and tool calls with LLMs
    -   Hooks for building dynamic chat and generative user interfaces
    -   Supports OpenAI (default), Anthropic, Cohere, and other model providers
-   shadcn/ui
    -   Styling with Tailwind CSS
    -   Component primitives from Radix UI for accessibility and flexibility
-   Data Persistence
    -   Vercel Postgres powered by Neon for saving chat history and user data
    -   Vercel Blob for efficient file storage
-   NextAuth.js
    -   Simple and secure authentication

Model Providers
---------------

This template ships with OpenAI `gpt-4o` as the default. However, with the AI SDK, you can switch LLM providers to OpenAI, Anthropic, Cohere, and many more with just a few lines of code.

Deploy Your Own
---------------

You can deploy your own version of the Next.js AI Chatbot to Vercel with one click:

Running locally
---------------

You will need to use the environment variables defined in `.env.example` to run Next.js AI Chatbot. It's recommended you use Vercel Environment Variables for this, but a `.env` file is all that is necessary.

> Note: You should not commit your `.env` file or it will expose secrets that will allow others to control access to your various OpenAI and authentication provider accounts.

1.  Install Vercel CLI: `npm i -g vercel`
2.  Link local instance with Vercel and GitHub accounts (creates `.vercel` directory): `vercel link`
3.  Download your environment variables: `vercel env pull`

pnpm install
pnpm dev

Your app template should now be running on localhost:3000.
