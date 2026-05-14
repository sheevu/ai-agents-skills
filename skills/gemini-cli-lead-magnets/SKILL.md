---
name: gemini-cli-lead-magnets
description: Use when the user wants to create lead magnets — ebooks, checklists, guides, templates, or free tools — using Gemini CLI. Trigger phrases: "create lead magnet with Gemini CLI," "generate ebook outline via CLI," "checklist generator Gemini," "free resource creation CLI." For email delivery, see gemini-cli-cold-email.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, lead-magnets, ebooks, checklists, content-upgrades, list-building]
---

## Overview

You are a Gemini CLI lead magnet creation expert. Help the user generate high-value lead magnets — ebooks, checklists, swipe files, email courses, and templates — using Gemini CLI to grow their email list and generate qualified leads.

## Checklist Generator

```bash
gemini --model gemini-1.5-pro --temperature 0.5 prompt \
"Create a detailed checklist titled: '[Checklist Title]'. Target audience: [audience]. Include 20 actionable items grouped into 4 sections. Format with checkboxes (- [ ] item). Make it immediately actionable."
```

### Example for MSME

```bash
gemini prompt \
"Create a '25-Point MSME Digital Marketing Checklist for 2026' for small business owners in India. Group into: Website, Social Media, SEO, Paid Ads, and Automation. Format with checkboxes."
```

## Ebook Outline

```bash
gemini --model gemini-1.5-pro --temperature 0.6 prompt \
"Create a detailed ebook outline titled: '[Ebook Title]'. Target reader: [audience]. Include: intro chapter, 5 main chapters with 3 subheadings each, conclusion, and a bonus section. Each chapter description in 2 sentences."
```

### Generate Chapter Content

```bash
gemini --model gemini-1.5-pro prompt \
"Write Chapter [X] of an ebook about [topic]. Chapter title: [title]. Subheadings: [list subheadings]. Length: 600-800 words. Tone: [expert/friendly/simple]. Include 1 practical example and 1 key takeaway box."
```

### Full Ebook from Outline (Batch)

```bash
#!/bin/bash
EBOOK_TITLE="How to Grow Your MSME with AI in 2026"
CHAPTERS=("Why AI Matters for Small Business" "Free AI Tools for MSMEs" "AI for Marketing Automation" "AI for Customer Service" "Getting Government Funding for AI Adoption")

for i in "${!CHAPTERS[@]}"; do
  CHAP_NUM=$((i+1))
  echo "# Chapter $CHAP_NUM: ${CHAPTERS[$i]}" >> ebook_output.md
  gemini --model gemini-1.5-pro --temperature 0.6 prompt \
  "Write Chapter $CHAP_NUM: '${CHAPTERS[$i]}' for an ebook titled '$EBOOK_TITLE'. Target: Indian MSME owners. 700 words. Friendly expert tone." >> ebook_output.md
  echo "\n---\n" >> ebook_output.md
done
echo "Ebook draft saved to ebook_output.md"
```

## Email Course (5-Day)

```bash
gemini --model gemini-1.5-pro prompt \
"Create a 5-day email course titled: '[Course Title]'. Each day: subject line, lesson title, 200-word lesson content, and one action step. Target: [audience]. Deliver one key insight per day."
```

## Swipe File

```bash
gemini prompt \
"Create a swipe file of 10 proven [type: ad headlines / email subject lines / CTA buttons / Instagram hooks] for [industry/niche]. Label each with the psychological trigger it uses (curiosity/urgency/social proof/etc.)."
```

## Template Generator

```bash
gemini --temperature 0.4 prompt \
"Create a fill-in-the-blank template for [document type e.g. partnership proposal, investor pitch, sales script]. Target: [audience]. Mark all variable fields with [BRACKETS]. Include instructions at the top."
```

## India-Specific Lead Magnets

```bash
gemini prompt \
"Create a lead magnet concept + outline for Indian MSME owners on the topic: 'How to Apply for PMEGP Loan in 2026 — Step-by-Step Guide'. Include: eligibility checklist, documents needed, and common mistakes to avoid. Simple English."
```

```bash
gemini prompt \
"Write a free guide titled: 'Top 10 Free AI Tools for Small Businesses in India (2026)'. Include tool name, what it does, free tier details, and a use case for an MSME. Format as a numbered list."
```

## Lead Magnet Title Generator

```bash
gemini --temperature 0.85 prompt \
"Generate 15 lead magnet title ideas for a [type of business]. Mix formats: checklists, guides, templates, email courses, swipe files, calculators. Make each title result-oriented and specific."
```

## Temperature Guide

| Task | Temperature |
|---|---|
| Checklists | 0.4–0.5 — factual, actionable |
| Ebook outlines | 0.6 |
| Email course content | 0.6 |
| Title generation | 0.85 — creative |
| Templates | 0.3 — structured |

## Related Skills

- `gemini-cli-cold-email` — deliver lead magnets via email
- `gemini-cli-copywriting` — landing page copy for lead magnet
- `gemini-cli-content-strategy` — plan lead magnets in content calendar
- `gemini-cli-msme-growth` — India-specific lead generation
