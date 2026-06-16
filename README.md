# Draftify AI 🚀 | Uncapped API & AI Code Generator

[![Website](https://img.shields.io/badge/Website-draftify.site-orange.svg)](https://draftify.site)
[![API Status](https://img.shields.io/badge/API-Online-brightgreen.svg)]()
[![Zero Retention](https://img.shields.io/badge/Privacy-Zero_Retention-blue.svg)]()

Ever been 300 lines deep into refactoring a spaghetti codebase, totally in the flow state, only to get slapped with a 'Generation Stopped' because you hit your 4-hour message cap? Yeah, us too. It feels exactly like spending hours on Stack Overflow for a missing semicolon, only to find a post from 2013 with no answers. 

We got sick of the corporate leash. Draftify is our middle finger to 4-hour cooldowns. We give you raw, Opus-level and Sonnet-level intelligence directly in your IDE or via our Developer API—without the arbitrary limits.

## ⚡ Why Draftify? (No Marketing BS)

We don't just resell a public API wrapper. We run highly optimized, coding-focused hybrid architectures on dedicated bare-metal hardware.

*   **Zero Corporate Cooldowns:** Keep your flow state intact. We don't do message caps.
*   **Zero-Retention Policy:** Your proprietary code is yours. Workspace context is processed purely in-memory and instantly flushed. We never train models on your hard work.
*   **Pay-as-you-go Developer API:** Build your own autonomous agents or tools using our API. You get the reasoning power of the big guys, just without the heart-stopping token bills.
*   **Claude AI Skills Ready:** Full support for function calling and complex, multi-step agent workflows.

## 📚 Documentation & Quick Links

- [Official Website & Dashboard](https://draftify.site)
- [Read the Full API Documentation](./api-reference.md)
- [Terms of Service](https://draftify.site/terms)
2. Fájl: api-reference.md (Az API Dokumentáció)
# Draftify API Quickstart 🔌

Let's be real: integrating APIs usually sucks, and reading sterile corporate documentation is the last thing you want to do on a Friday night. 

We built the Draftify API as a seamless drop-in replacement for standard conversational endpoints. You get the elite reasoning power to build your own tools, scripts, and autonomous agents, without paying $50 for a million output tokens.

## Prerequisites

Before you hit the endpoint, you need:
1. An active Draftify account.
2. A **Draftify API Key** (grab it from your Dashboard under *Settings > API Keys*).

*Tip: Don't commit your API key to a public repo. We all know someone who did that. Don't be that guy. Use environment variables.*

## Available Models

We offer multiple models tailored for different complexities. No subscription required for API access, just pure pay-as-you-go compute:

| Model Name | Description | Input Price | Output Price |
| :--- | :--- | :--- | :--- |
| `sonnet-4.6-level` | Lightning-fast, cost-effective coding | €0.20 / 1M tokens | €0.74 / 1M tokens |
| `opus-4.7-level` | Advanced logic and context handling | €1.00 / 1M tokens | €3.00 / 1M tokens |
| `opus-4.8-level` | Elite reasoning for complex architecture | €2.00 / 1M tokens | €5.00 / 1M tokens |
| `fable-5-level` | Autonomous agent mode *(Coming Soon)* | €2.00 / 1M tokens | €6.00 / 1M tokens |

---

## 1. Your First Request (cURL)

Want to test if we are actually uncapped? Fire up your terminal and send a request to the `sonnet-4.6-level` model:

```bash
curl -X POST https://api.draftify.site/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_DRAFTIFY_API_KEY" \
  -d '{
    "model": "sonnet-4.6-level",
    "messages": [
      {
        "role": "user",
        "content": "Hello! Write a fast sorting algorithm in Python, and do it without giving me a 4-hour cooldown."
      }
    ]
  }'
2. Using Python
If you're building backend agents, use the standard requests library. No bloated SDKs required.
import requests
import os

api_key = os.getenv("DRAFTIFY_API_KEY")
url = "https://api.draftify.site/v1/chat/completions"

headers = {
    "Authorization": f"Bearer {api_key}",
    "Content-Type": "application/json"
}

data = {
    "model": "opus-4.8-level",
    "messages": [{"role": "user", "content": "Write a scalable authentication middleware."}]
}

response = requests.post(url, headers=headers, json=data)
print(response.json()["choices"]["message"]["content"])
🔒 Security & Privacy (We actually respect it)
Your code is your most valuable asset. Every request sent to the Draftify API is processed entirely in-memory. Once the generation loop is finished, the data is instantly and permanently destroyed. We do not—and will never—train models on your API inputs.
