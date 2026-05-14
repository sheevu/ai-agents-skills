---
name: gemini-cli-content-strategy
description: Use when the user wants to build a content strategy, content calendar, editorial plan, or pillar content architecture using Gemini CLI. Trigger phrases: "Gemini CLI content strategy," "build content calendar via CLI," "content plan with Gemini," "content pillars generator CLI." For individual posts, see gemini-cli-social.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, content-strategy, content-calendar, editorial-planning, content-marketing]
---

## Overview

You are a Gemini CLI content strategy expert. Help the user build comprehensive content strategies, editorial calendars, content pillar structures, and distribution plans using Gemini CLI.

## Brand Content Strategy

```bash
gemini --model gemini-1.5-pro --temperature 0.6 prompt \
"Create a content marketing strategy for [brand name], a [type of business] targeting [audience] in India. Include:
1. Brand voice and tone guidelines
2. 5 content pillars
3. Platform priority list (rank top 4 platforms)
4. Content types per platform
5. Posting frequency recommendation
6. KPIs to track"
```

## Content Pillars

```bash
gemini --model gemini-1.5-pro prompt \
"Define 5 content pillars for [brand/company] in the [industry] sector. For each pillar: name, description, 3 example topics, and best content format (video/blog/carousel/thread)."
```

## 30-Day Content Calendar

```bash
gemini --model gemini-1.5-pro --temperature 0.5 prompt \
"Create a 30-day content calendar for [brand] on [platforms]. Include: Date, Platform, Content Type, Topic, Caption Hook, CTA. Focus themes: [theme 1], [theme 2], [theme 3]. Format as markdown table."
```

## Weekly Content Plan

```bash
gemini prompt \
"Build a weekly content plan for a [business type] startup. Include: Mon-Sun with platform, topic, format, and time to post (IST). Optimize for Indian audience engagement times."
```

## Competitor Content Gap Analysis

```bash
gemini --model gemini-1.5-pro prompt \
"Analyze content gaps for a [type of business] in India compared to typical competitors. Suggest 10 underserved content topics that could drive organic traffic and social engagement in 2026."
```

## Blog Content Plan

```bash
gemini prompt \
"Create a 3-month blog content plan for [website/brand] targeting the keyword cluster: [main keyword]. Include: blog title, target keyword, search intent, word count, internal linking opportunity. Format as table."
```

## Repurposing Strategy

```bash
gemini prompt \
"Create a content repurposing plan for this [blog post/video/podcast episode]: [paste title or summary]. Show how to turn it into: Twitter thread, LinkedIn post, Instagram carousel, YouTube Short, email newsletter, and a lead magnet."
```

## Video Content Strategy

```bash
gemini --model gemini-1.5-pro prompt \
"Build a YouTube + Instagram Reels content strategy for [brand]. Include: 10 video ideas with hooks, ideal length per platform, thumbnail concept, and CTA for each video."
```

## India-Specific Content Strategy

```bash
gemini prompt \
"Create a content strategy for an MSME in [sector] in Uttar Pradesh, India. Focus on:
- Hindi + English bilingual content approach
- WhatsApp Business content plan
- Festival/seasonal content calendar (include key Indian festivals in 2026)
- Government scheme awareness content (PMEGP, Startup India, MSME registrations)
- Local SEO content for [city/region]"
```

## Content Performance Audit Prompt

```bash
gemini prompt \
"Review this content strategy and identify gaps, weak points, and optimization opportunities: [paste your current strategy or list of content pieces]."
```

## Automate Monthly Planning

Save as `monthly_plan.sh` and run at the start of each month:
```bash
#!/bin/bash
MONTH=$(date +"%B %Y")
gemini --model gemini-1.5-pro prompt \
"Create a content calendar for $MONTH for [brand name] in [industry]. Include national holidays, relevant Indian occasions, and 20 content ideas with platform assignments." > content_calendar_$MONTH.txt
echo "Calendar saved to content_calendar_$MONTH.txt"
```

Make executable:
```bash
chmod +x monthly_plan.sh
./monthly_plan.sh
```

## Related Skills

- `gemini-cli-social` — execute individual posts
- `gemini-cli-copywriting` — write the copy
- `gemini-cli-seo` — SEO-optimised blog content
- `gemini-cli-lead-magnets` — content upgrades
- `gemini-cli-analytics` — measure content performance
