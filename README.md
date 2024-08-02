<a href="">
  <img alt="Next.js 14 and App Router-ready AI chatbot." src="https://chat.vercel.ai/opengraph-image.png">
  <h1 align="center">Next.js AI Chatbot with Local Model</h1>
</a>

<p align="center">
  An open-source AI chatbot app template built with Next.js, the Vercel AI SDK, LMStudio, and Vercel KV.
</p>

<br/>

## Features

- [Next.js](https://nextjs.org) App Router
- React Server Components (RSCs), Suspense, and Server Actions
- [Vercel AI SDK](https://sdk.vercel.ai/docs) for streaming chat UI
- [LM Studio] (https://lmstudio.ai/) for interacting with LLM models and streaming API from our local machine
- [shadcn/ui](https://ui.shadcn.com)
  - Styling with [Tailwind CSS](https://tailwindcss.com)
  - [Radix UI](https://radix-ui.com) for headless component primitives
  - Icons from [Phosphor Icons](https://phosphoricons.com)
- Chat History, rate limiting, and session storage with [Vercel KV](https://vercel.com/storage/kv)
- [NextAuth.js](https://github.com/nextauthjs/next-auth) for authentication

## Requirements

- Node version 18 or higher [https://nodejs.org/en]
- Visual Studio Code [https://code.visualstudio.com/download]
- LM Studio [https://lmstudio.ai/]
- Vercel if you want to deploy the project online [https://vercel.com/]

## Start Guide

1. Go to LM Studio and download the latest release [https://lmstudio.ai/]
2. Load a model in LM Studio. Pick one of the featured ones or download a model from HuggingFace [https://huggingface.co/]
3. In LM Studio, turn on the API endpoint so that we can interact with it from our NextJS project
4. Fork this repo and open it in your IDE
5. Copy .env.example and rename it to .env
6. In .env file change MODEL_NAME="LM Studio Community/Meta-Llama-3-8B-Instruct-GGUF" to the name of the model you have loaded into LM Studio and save the file
7. Open Terminal and tun the following commands to install the dependencies and start the website locally
```bash
npm install pnpm -g
pnpm install
pnpm dev
```
8. Open your browser and navigate to [localhost:3000](http://localhost:3000/) where your app is running

## Deploying to Vercel

To deploy to Vercel, you will need a few things. First, you will need to tunnel your LM Studio local API endpoint online in order to access it anywhere. This is not secure as LM Studio does not provide you with an API key. Anybody will be able to access your API endpoint.

Upload this project to GitHub as a private repo. Go to Vercel and add a new project using their GitHub integration. Add all the value from your .env file into the environment variables in Vercel.

Follow the steps outlined in the [quick start guide](https://vercel.com/docs/storage/vercel-kv/quickstart#create-a-kv-database) provided by Vercel. This guide will assist you in creating and configuring your KV database instance on Vercel, enabling your application to interact with it.

Remember to update your environment variables (`KV_URL`, `KV_REST_API_URL`, `KV_REST_API_TOKEN`, `KV_REST_API_READ_ONLY_TOKEN`) in the `.env` file with the appropriate credentials provided during the KV database setup.
