---
name: gemini-cli-msme-growth
description: Use when the user wants India-specific MSME marketing automation using Gemini CLI — government scheme content, local business growth, Hindi/Hinglish copy, startup funding content, or B2B2G marketing for Indian markets. Trigger phrases: "MSME marketing Gemini CLI," "India startup content CLI," "PMEGP MUDRA content Gemini," "Hinglish marketing automation," "UP Bihar MSME digital marketing." For general content, see gemini-cli-copywriting.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, msme, india, startup-india, pmegp, mudra, hinglish, lucknow, uttar-pradesh, b2b2g]
---

## Overview

You are an India-focused MSME growth and marketing automation expert using Gemini CLI. Help Indian startup founders, MSME owners, and digital marketers create localized content, government scheme awareness material, investor pitches, and growth-focused copy in English, Hindi, and Hinglish.

## Government Scheme Content

### PMEGP Awareness Post

```bash
gemini --model gemini-1.5-pro --temperature 0.5 prompt \
"Write a simple, easy-to-understand explainer on PMEGP (Prime Minister's Employment Generation Programme) 2026 for small business owners in UP. Include: eligibility, loan amount, subsidy percentage, and how to apply. Language: simple English with Hindi keywords."
```

### MUDRA Loan Guide

```bash
gemini prompt \
"Create a WhatsApp message template explaining MUDRA loan categories (Shishu/Kishor/Tarun) to a local shopkeeper or small business owner in Lucknow. Use Hinglish. Max 200 words. Add emoji."
```

### Startup India Pitch Summary

```bash
gemini --model gemini-1.5-pro prompt \
"Write a 200-word summary of the Startup India Recognition benefits for a tech startup in Lucknow, UP applying for DPIIT recognition in 2026. Include: tax benefits, self-certification compliance, and fast-track patent application."
```

### GEM Portal Awareness Content

```bash
gemini prompt \
"Write a LinkedIn post explaining how MSMEs can sell to the Indian government via the GeM (Government e-Marketplace) portal. Include: registration steps, benefits, and 3 success tips. Professional tone."
```

## Local Business Marketing

### Lucknow / UP Business Promotion

```bash
gemini --temperature 0.8 prompt \
"Write social media content (Instagram caption + Facebook post) for a [type of business] in Lucknow, UP. Highlight: local trust, established presence, and [key service]. Use Hinglish for Instagram, formal English for Facebook."
```

### Local SEO Content

```bash
gemini --temperature 0.3 prompt \
"Write a locally optimized 'About Us' page for [business name] in [city], [state], India. Include: city name 3+ times, local landmarks, service area description, and 2 India-specific trust signals (years in business, certifications)."
```

### WhatsApp Business Templates

```bash
gemini prompt \
"Create 5 WhatsApp Business message templates for a [type of MSME] in India:
1. Welcome message for new customers
2. Order confirmation
3. Payment received
4. Follow-up after 7 days
5. Festival offer (Diwali/Holi)
Use simple Hindi-friendly English. Max 160 chars each."
```

## Investor & Funding Content

### Pitch Deck Slide Copy

```bash
gemini --model gemini-1.5-pro --temperature 0.6 prompt \
"Write compelling copy for the following pitch deck slides for [startup name], an AI startup from Lucknow:
1. Problem slide (2-3 sentences)
2. Solution slide (3 bullet points)
3. Market size slide (TAM/SAM/SOM framing for India)
4. Traction slide (format: key metrics + growth)
5. Ask slide (raise amount + use of funds)"
```

### SIDBI / TiE / iCreate Grant Application Summary

```bash
gemini --temperature 0.4 prompt \
"Write a 300-word project summary for a grant application from [startup name] to [funding body]. Problem: [problem]. Solution: [solution]. Social impact: [impact]. Target: Indian MSMEs in [sector]."
```

## Bulk Hindi / Hinglish Content

```bash
#!/bin/bash
TOPICS=("AI ke fayde chhote business ke liye" "PMEGP loan kaise milta hai" "Digital marketing se kamai kaise badhaye")

for topic in "${TOPICS[@]}"; do
  echo "=== $topic ===" >> hindi_content.txt
  gemini --model gemini-1.5-flash --temperature 0.8 prompt \
  "Write a short 100-word Facebook post in Hinglish about: '$topic'. Target: small business owners in UP/Bihar. Friendly tone, add 3 Hindi hashtags." >> hindi_content.txt
  echo "" >> hindi_content.txt
done
```

## MSME Festival Marketing Calendar

```bash
gemini --model gemini-1.5-pro prompt \
"Create a 2026 festival marketing calendar for an MSME in India. For each major festival (Holi, Navratri, Dussehra, Diwali, Christmas, New Year, Republic Day, Independence Day): suggest offer type, ad copy hook, and best platform. Format as markdown table."
```

## Automation Scripts for MSME Teams

### Daily Content Generator (Run via Cron)

```bash
#!/bin/bash
# Save as daily_content.sh, add to crontab: 0 8 * * * /path/to/daily_content.sh
DATE=$(date +"%d %B %Y")
gemini --model gemini-1.5-flash prompt \
"Generate today's ($DATE) social media post for [brand name], an AI company in Lucknow. Topic: rotate between AI tips, MSME growth, startup inspiration. Keep under 100 words. Platform: LinkedIn." > daily_post_$DATE.txt
echo "Today's post saved!"
```

## Related Skills

- `gemini-cli-cold-email` — outreach to MSME clients and government bodies
- `gemini-cli-lead-magnets` — free guides for MSME audiences
- `gemini-cli-social` — Hinglish social media content
- `gemini-cli-seo` — local SEO for MSME websites
- `gemini-cli-content-strategy` — MSME content calendar
