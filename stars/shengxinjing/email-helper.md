---
project: email-helper
stars: 724
description: Generate your business emails in seconds (by OpenAI)
url: https://github.com/shengxinjing/email-helper
---

EmailHelper
===========

This project generates emails for you using AI.

Support
-------

`English`, `Simplified Chinese`, `Traditional Chinese`, `Japanese`, `Italian`, `German`, `Spanish`,`French`,`Dutch` ,`Korean`,`Khmer`, `Hindi`

PR welcome

How it works
------------

Inspired by TwtterBio and Danny Richman

Powerd by OpenAI, Next.js, Vercel and Tailwind CSS.

This project uses the OpenAI GPT-3 API (specifically, text-davinci-003) and Vercel Edge functions with streaming. It constructs a prompt based on the form and user input, sends it to the GPT-3 API via a Vercel Edge function, then streams the response back to the application.

Video and blog post coming soon on how to build apps with OpenAI and Vercel Edge functions!

Running Locally
---------------

After cloning the repo, go to OpenAI to make an account and put your API key in a file called `.env`.

Then, run the application in the command line and it will be available at `http://localhost:3000`.

npm run dev

One-Click Deploy
----------------

Deploy the example using Vercel:
