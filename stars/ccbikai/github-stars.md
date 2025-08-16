---
project: github-stars
stars: 72
description: A Cloudflare-powered MCP (Model Context Protocol) Server that allows you to search and query your GitHub starred repositories using natural language.
url: https://github.com/ccbikai/github-stars
---

GitHub Stars MCP Server
=======================

A Cloudflare-powered MCP (Model Context Protocol) Server that allows you to search and query your GitHub starred repositories using natural language.

English | 简体中文

* * *

Overview
--------

This project creates a searchable database of your GitHub starred repositories by:

1.  Fetching all your starred repositories using the GitHub API
2.  Extracting and processing the README files from each repository
3.  Uploading the processed data to Cloudflare R2 storage
4.  Using Cloudflare AutoRAG to create embeddings for efficient searching
5.  Exposing a MCP Server that allows querying these repositories via natural language

Features
--------

-   Automatically fetches and processes GitHub starred repositories
-   Scheduled weekly updates via GitHub Actions
-   Stores repository metadata and README content
-   Provides semantic search capabilities through Cloudflare AutoRAG
-   Exposes a MCP-compatible API for integration with AI agents

Setup
-----

### Prerequisites

-   Node.js (v22 recommended)
-   PNPM package manager
-   GitHub Personal Access Token with `repo` scope
-   Cloudflare account

### Configuration

1.  Clone this repository
    
2.  Set up Cloudflare R2:
    
    -   Create a R2 bucket
    -   Configure R2 access credentials
3.  Configure GitHub Secrets for the CI/CD workflow:
    
    -   `GH_TOKEN`: GitHub token for fetching starred repositories
    -   `R2_ACCOUNT_ID`: Cloudflare account ID
    -   `R2_ACCESS_KEY_ID`: R2 access key
    -   `R2_SECRET_ACCESS_KEY`: R2 secret key
    -   `R2_BUCKET`: R2 bucket name
4.  Configure Cloudflare AutoRAG:
    
    -   Create an AutoRAG instance in Cloudflare
    -   Set the `AUTO_RAG_NAME` environment variable in your Cloudflare Worker

### Local Development

To develop locally:

# Install dependencies
pnpm install

# Fetch your GitHub stars locally
pnpm dev:stars

# Run MCP server locally
pnpm dev:mcp

### Deployment

Deploy to Cloudflare Workers:

pnpm deploy

The GitHub Action will automatically:

1.  Run weekly to update your starred repositories
2.  Upload the processed files to R2
3.  Rebuild the AutoRAG index

Usage
-----

Once deployed, you can interact with the MCP Server using any MCP-compatible client:

SSE: `https://your-worker-url.workers.dev`

API Reference
-------------

### MCP Tool: `search_github_stars`

Searches through your starred GitHub repositories.

Parameters:

-   `query` (string): Natural language query to search repositories

Response:

-   JSON result containing matching repositories and relevant README content
