---
name: gemini-cli-cold-email
description: Use when the user wants to draft, personalize, or automate cold email sequences using Gemini CLI. Trigger phrases: "Gemini CLI cold email," "generate outreach email via terminal," "automate email sequences with Gemini," "bulk cold emails CLI." For general email marketing, see gemini-cli-copywriting.
version: 1.0.0
author: Sheevum Goel
tags: [gemini-cli, cold-email, outreach, email-automation, b2b-marketing]
---

## Overview

You are a Gemini CLI cold email expert. Help the user draft, personalize, and automate cold email sequences for B2B outreach, investor pitches, partnership proposals, and MSME client acquisition using Gemini CLI.

## Single Cold Email

### B2B Outreach

```bash
gemini --model gemini-1.5-pro --temperature 0.7 prompt \
"Write a cold outreach email from [sender name], Founder of [company]. Recipient: [name], [title] at [company]. Goal: [goal e.g. book a demo, explore partnership]. Tone: professional but conversational. Max 150 words."
```

### Investor Pitch Email

```bash
gemini --model gemini-1.5-pro prompt \
"Write a cold email to an angel investor in India introducing [startup name], an AI startup from Lucknow focused on [problem solved]. Traction: [traction]. Ask: [ask e.g. 30-min call]. Max 200 words."
```

### Government / MSME Partnership

```bash
gemini prompt \
"Write a formal introductory email to a SIDBI/MSME Development Institute official, introducing [company name] and proposing collaboration for MSME digital automation. Formal Hindi-friendly English tone."
```

## Email Sequences (Multi-Step)

### 3-Email Follow-up Sequence

```bash
gemini --model gemini-1.5-pro prompt \
"Write a 3-email cold outreach sequence for [product/service]. 
Email 1: First contact (introduce, value prop, soft CTA). 
Email 2: Follow-up (different angle, social proof). 
Email 3: Final breakup email (low-pressure, keep door open). 
Target: [audience]. Each email max 120 words."
```

### Bulk Personalized Emails from List

Create `leads.txt`:
```
Rahul Sharma, CEO, TechStartup Delhi
Priya Verma, Marketing Head, RetailCo Mumbai
Amit Gupta, Founder, AgriTech Lucknow
```

Run:
```bash
while IFS=, read -r name title company; do
  echo "=== Email for $name ==" >> emails_output.txt
  gemini --model gemini-1.5-flash --temperature 0.7 prompt \
  "Write a personalized cold email to $name, $title at $company from Sheevum Goel, Founder of NAVA-NETRA NEURAL AI Labs. Goal: explore AI automation partnership. Max 120 words." >> emails_output.txt
  echo "" >> emails_output.txt
done < leads.txt
```

## Subject Line Generator

```bash
gemini --temperature 0.8 prompt \
"Write 10 cold email subject lines for an outreach email to [target role] about [topic]. Mix curiosity, personalization, and value-based approaches. Max 50 chars each."
```

## Email Audit / Improvement

```bash
gemini prompt \
"Review this cold email and improve it for higher open and reply rates. Flag: weak subject line, unclear CTA, too long, or generic language.

[Paste your email here]"
```

## Tone & Temperature Guide

| Email Type | Temperature | Tone |
|---|---|---|
| Investor pitch | 0.6 | Confident, concise |
| B2B outreach | 0.7 | Professional, friendly |
| Partnership proposal | 0.5 | Formal |
| Follow-up sequence | 0.7 | Persistent but polite |
| Breakup email | 0.8 | Light, human |

## MSME India-Specific Emails

```bash
gemini prompt \
"Write a cold email to a local MSME business owner in UP/Bihar introducing a free AI audit service. Use simple English, avoid jargon. Include one line in Hindi at the end as a warm sign-off."
```

## Related Skills

- `gemini-cli-copywriting` — copy for emails
- `gemini-cli-lead-magnets` — attach lead magnets to emails
- `gemini-cli-msme-growth` — India-specific outreach
- `gemini-cli-social` — LinkedIn DM sequences
