# AGENTS.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains **Agent Skills** for Google Gemini CLI, following the [Agent Skills specification](https://agentskills.io/specification.md). Skills install to `.agents/skills/`.

- **Name**: AI Agents Skills — Gemini CLI Edition
- **GitHub**: [sheevu/ai-agents-skills](https://github.com/sheevu/ai-agents-skills)
- **Creator**: Sheevum Goel, NAVA-NETRA NEURAL Sudarshan AI Labs Pvt. Ltd.
- **License**: MIT

## Repository Structure

```
ai-agents-skills/
├── skills/
│   └── skill-name/
│       └── SKILL.md       # Required skill file
├── AGENTS.md
└── README.md
```

## Required Frontmatter

```yaml
---
name: skill-name
description: What this skill does and when to use it. Include trigger phrases.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, marketing, automation]
---
```

## Frontmatter Field Constraints

| Field | Required | Constraints |
|---|---|---|
| `name` | Yes | 1-64 chars, lowercase, hyphens only. Must match dir name. |
| `description` | Yes | 1-1024 chars. Include trigger phrases. |
| `version` | No | Semantic versioning (1.0.0) |
| `author` | No | Skill author name |
| `tags` | No | Array of relevant tags |

## Writing Style

- Direct and instructional ("You are a...")
- Under 500 lines per SKILL.md
- H2 for main sections, H3 for subsections
- Code blocks for all CLI examples
- Tables for reference data

## Git Workflow

- New skills: `feature/skill-name`
- Improvements: `fix/skill-name-description`
- Commit format: `feat: add gemini-cli-[name] skill`
