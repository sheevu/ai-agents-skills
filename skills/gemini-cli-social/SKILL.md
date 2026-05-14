---
name: gemini-cli-social
description: Use when the user wants to generate social media captions, posts, hashtags, or content for Instagram, LinkedIn, Twitter/X, Facebook, or YouTube using Gemini CLI. Trigger phrases: "Gemini CLI social media," "generate Instagram captions via terminal," "bulk social posts with Gemini," "LinkedIn content CLI." For ad copy, see gemini-cli-ad-creative.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, social-media, instagram, linkedin, twitter, content-creation]
---

## Overview

You are a Gemini CLI social media expert. Help the user generate platform-specific posts, captions, hashtags, and content calendars for all major social platforms using Gemini CLI commands.

## Platform-Specific Commands

### Instagram Caption

```bash
gemini --model gemini-1.5-pro --temperature 0.85 prompt \
"Write an Instagram caption for [topic/image description]. Brand: [brand name]. Tone: [inspirational/funny/educational]. Include 5 relevant hashtags. Max 150 words."
```

### LinkedIn Post

```bash
gemini --model gemini-1.5-pro --temperature 0.7 prompt \
"Write a LinkedIn post from the perspective of [name], Founder of [company]. Topic: [topic]. Tone: thought leadership. Include a hook first line, 3 key insights, and end with a question to drive comments. Max 250 words."
```

### Twitter/X Thread

```bash
gemini --model gemini-1.5-pro prompt \
"Write a 5-tweet Twitter thread about [topic]. Tweet 1: hook/bold claim. Tweets 2-4: insights with data. Tweet 5: CTA or takeaway. Each tweet under 280 chars."
```

### Facebook Post

```bash
gemini --temperature 0.75 prompt \
"Write a Facebook post for [business type] in [city/region], India. Topic: [topic]. Tone: friendly and community-focused. Include a question at the end to boost engagement."
```

### YouTube Description

```bash
gemini --temperature 0.4 prompt \
"Write a YouTube video description for a video titled: '[video title]'. Include: 2-line hook, 5 bullet points of what viewers learn, target keywords: [keywords], and 3 hashtags. Max 300 words."
```

## Hashtag Generator

```bash
gemini prompt \
"Generate 30 hashtags for a [niche] brand in India. Mix: 10 high-volume (1M+ posts), 10 mid-volume (100K–1M), 10 niche (under 100K). Format as a copy-paste ready list."
```

## Bulk Content for Multiple Platforms

Create `topics.txt`:
```
AI automation for MSMEs
Startup India scheme benefits 2026
How to grow business with WhatsApp
```

Run for all platforms:
```bash
while IFS= read -r topic; do
  echo "=== TOPIC: $topic ===" >> social_content.txt
  gemini --model gemini-1.5-flash prompt \
  "Write: 1) Instagram caption (100 words + hashtags), 2) LinkedIn post (150 words), 3) Twitter post (280 chars) for topic: $topic. Brand voice: professional but relatable." >> social_content.txt
  echo "" >> social_content.txt
done < topics.txt
```

## India / MSME-Specific Social Content

### Hindi + English (Hinglish) Instagram

```bash
gemini --temperature 0.9 prompt \
"Write an Instagram caption in Hinglish (mix of Hindi and English) for a post about [topic] targeting young Indian entrepreneurs. Add 5 trending Indian startup hashtags."
```

### Startup India / Government Scheme Post

```bash
gemini prompt \
"Write a LinkedIn post explaining the key benefits of the [scheme name e.g. PMEGP/MUDRA/Startup India] for small business owners. Professional yet simple. Include a CTA to DM for help."
```

## Content Calendar (30 Days)

```bash
gemini --model gemini-1.5-pro prompt \
"Create a 30-day social media content calendar for a [business type] brand. Include: day, platform, post topic, content type (reel/carousel/post/story). Format as a markdown table."
```

## Tone Guide

| Platform | Temperature | Tone |
|---|---|---|
| LinkedIn | 0.6–0.7 | Professional, insightful |
| Instagram | 0.85–0.9 | Creative, visual, punchy |
| Twitter/X | 0.8 | Sharp, opinionated |
| Facebook | 0.7 | Friendly, community |
| YouTube | 0.4 | Informative, keyword-rich |

## Related Skills

- `gemini-cli-copywriting` — brand copy
- `gemini-cli-content-strategy` — full content plan
- `gemini-cli-ad-creative` — paid social ads
- `gemini-cli-lead-magnets` — content upgrades to grow following
