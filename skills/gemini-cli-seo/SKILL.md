---
name: gemini-cli-seo
description: Use when the user wants to automate SEO tasks using Gemini CLI — meta titles, meta descriptions, alt text, schema markup, keyword research, or bulk page optimization. Trigger phrases: "Gemini CLI SEO," "bulk meta tags via CLI," "automate SEO with Gemini," "generate schema with Gemini CLI." For AI-powered SEO strategy, see ai-seo.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, seo, meta-tags, schema, keyword-research, automation]
---

## Overview

You are a Gemini CLI SEO automation expert. Help the user bulk-generate and optimize SEO elements — meta tags, alt texts, schema JSON-LD, and keyword-rich content — using Gemini CLI from the terminal.

## Meta Title & Description

### Single Page

```bash
gemini --model gemini-1.5-flash --temperature 0.3 prompt \
"Write an SEO meta title (under 60 chars) and meta description (under 155 chars) for a page about: [topic]. Target keyword: [keyword]. Brand: [brand name]."
```

### Bulk Meta Tags from CSV

Create `pages.txt`:
```
AI CRM for small businesses in India
MSME loan scheme guide 2026
Numerology personal report service
```

Run bulk generation:
```bash
while IFS= read -r page; do
  echo "=== $page ==" >> meta_output.txt
  gemini --model gemini-1.5-flash --temperature 0.2 prompt \
  "Write SEO meta title (max 60 chars) and meta description (max 155 chars) for: $page" >> meta_output.txt
  echo "" >> meta_output.txt
done < pages.txt
```

## Alt Text for Images

```bash
gemini --model gemini-1.5-flash prompt \
"Write SEO-friendly alt text (under 125 chars) for an image showing: [describe image]. Page context: [page topic]. Target keyword: [keyword]."
```

### Bulk Alt Text

```bash
gemini prompt "Write 10 alt text variations for product images of [product name] targeting the keyword '[keyword]'" > alt_texts.txt
```

## Schema Markup (JSON-LD)

### Local Business Schema

```bash
gemini --model gemini-1.5-pro --temperature 0.1 prompt \
"Generate a complete JSON-LD LocalBusiness schema for:
Business name: [name]
Type: [type e.g. TechCompany]
Address: [full address]
City: Lucknow, Uttar Pradesh, India
Phone: [phone]
Website: [url]
Description: [description]"
```

### Product Schema

```bash
gemini --temperature 0.1 prompt \
"Generate JSON-LD Product schema for: [product name]. Price: [price]. Currency: INR. Description: [desc]. Brand: [brand]."
```

### FAQ Schema

```bash
gemini --temperature 0.2 prompt \
"Generate JSON-LD FAQPage schema with 5 Q&As about [topic]. Optimised for Google rich results."
```

## Keyword Research

```bash
gemini --model gemini-1.5-pro prompt \
"List 20 long-tail SEO keywords for a [type of business] targeting [audience] in India. Include search intent (informational/commercial/transactional) for each."
```

### LSI Keywords

```bash
gemini prompt \
"Generate 15 LSI (Latent Semantic Indexing) keywords related to the primary keyword: '[keyword]'. Format as a comma-separated list."
```

## Content Optimization

### SEO Blog Outline

```bash
gemini --model gemini-1.5-pro prompt \
"Create an SEO-optimized blog outline for the keyword: '[target keyword]'. Include: title tag, meta description, H2s, H3s, and suggested word count per section."
```

### Title Tag Variations

```bash
gemini prompt \
"Write 10 SEO title tag variations for the keyword '[keyword]'. Mix question-based, how-to, list, and direct formats. Max 60 chars each."
```

## Temperature Guide for SEO Tasks

| Task | Temperature |
|---|---|
| Schema markup | 0.1 — must be precise |
| Meta descriptions | 0.2–0.3 |
| Keyword research | 0.3 |
| Blog outlines | 0.4 |
| Title variations | 0.5 |

## Save & Export

```bash
# Export all SEO output to one file
gemini prompt "[SEO task]" >> seo-output.txt

# Export schema as JSON
gemini prompt "Generate LocalBusiness schema for..." | grep -A 100 '{' > schema.json
```

## Related Skills

- `gemini-cli-copywriting` — keyword-rich copy
- `gemini-cli-content-strategy` — full SEO content plan
- `gemini-cli-ad-creative` — PPC ad copy
