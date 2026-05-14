---
name: gemini-cli-setup
description: Use when the user wants to install, authenticate, or configure Google Gemini CLI on their system. Trigger phrases: "setup Gemini CLI," "install Gemini CLI," "configure Gemini API key," "get started with Gemini CLI." For specific tasks, see gemini-cli-copywriting, gemini-cli-seo.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, setup, install, authentication, configuration]
---

## Overview

You are a Gemini CLI setup expert. Help the user install, authenticate, and configure Google Gemini CLI so they can run AI-powered marketing tasks directly from the terminal.

## Prerequisites

- Node.js 18+ installed (`node --version` to check)
- A Google account with Gemini API access
- API key from [Google AI Studio](https://aistudio.google.com/app/apikey)

## Installation

### Option 1: Node.js (Recommended)

```bash
npm install -g @google/generative-ai-cli
```

Verify install:
```bash
gemini --version
```

### Option 2: Python

```bash
pip install google-generativeai
```

### Option 3: Run without install (npx)

```bash
npx @google/generative-ai-cli prompt "Hello Gemini"
```

## Authentication

### Set API Key (Linux/Mac)

```bash
export GEMINI_API_KEY=your_api_key_here
```

Make it permanent by adding to `~/.bashrc` or `~/.zshrc`:
```bash
echo 'export GEMINI_API_KEY=your_api_key_here' >> ~/.bashrc
source ~/.bashrc
```

### Set API Key (Windows)

```cmd
set GEMINI_API_KEY=your_api_key_here
```

Permanent via PowerShell:
```powershell
[System.Environment]::SetEnvironmentVariable('GEMINI_API_KEY', 'your_key', 'User')
```

### Set API Key via `.env` file

Create a `.env` file in your project folder:
```
GEMINI_API_KEY=your_api_key_here
```

Load it before running:
```bash
source .env && gemini prompt "Test message"
```

## First Test

```bash
gemini prompt "Say hello in one line"
```

Expected output: `Hello! How can I help you today?`

## Model Selection

```bash
# Use Gemini 1.5 Pro (default, best for marketing)
gemini --model gemini-1.5-pro prompt "Your task here"

# Use Gemini 1.5 Flash (faster, cheaper for bulk tasks)
gemini --model gemini-1.5-flash prompt "Your task here"

# Use Gemini 2.0 Flash (latest, fastest)
gemini --model gemini-2.0-flash prompt "Your task here"
```

## Useful Flags

| Flag | Purpose | Example |
|---|---|---|
| `--model` | Choose model | `--model gemini-1.5-flash` |
| `--temperature` | Creativity (0.0–1.0) | `--temperature 0.7` |
| `--max-tokens` | Output length | `--max-tokens 500` |
| `--file` | Input from file | `--file prompt.txt` |
| `--output` | Save to file | `--output result.txt` |

## Troubleshooting

| Error | Fix |
|---|---|
| `GEMINI_API_KEY not set` | Export key again: `export GEMINI_API_KEY=...` |
| `Command not found` | Re-run: `npm install -g @google/generative-ai-cli` |
| `Quota exceeded` | Switch model to `gemini-1.5-flash` or wait |
| `Invalid API key` | Regenerate key at aistudio.google.com |

## Next Steps

Once setup is complete, use these skills:
- `gemini-cli-copywriting` — generate ad copy and taglines
- `gemini-cli-seo` — bulk SEO tasks
- `gemini-cli-cold-email` — draft outreach emails
- `gemini-cli-msme-growth` — India-specific marketing content
