# ResolveAI: Autonomous Customer Support

**Ticket in, resolution out. A human only when needed.**

Prototype for the *Legacy to Modern Challenge*, PS 2 (Customer Support → Autonomous AI Support), TechTatva 2K26.

## How it works

```
Customer message (web chat)
   → n8n Webhook
   → 1. Understand   Gemini classifies intent, sentiment, urgency, confidence
   → 2. Investigate  Order lookup in the order system
   → 3. Decide       Business rules + AI confidence
   → 4. Act          Auto-reply / auto-approve refund (up to Rs.500) / escalate to a human with an AI summary
```

The AI never invents facts. Replies are built only from looked-up order data, and actions are limited by business rules. If Gemini is unavailable, a rule-based fallback classifies the ticket so customers still get an answer.

## Files

| File | What it is |
|---|---|
| `index.html` | Support console: customer chat, live AI pipeline, human agent desk, ticket log |
| `classic.html` | Earlier, simpler demo page |
| `config.example.js` | Copy to `config.js` and set your webhook URL |
| `ResolveAI_n8n_workflow.json` | n8n workflow to import |
| `docs/` | Pitch script |

## Setup

1. In n8n, go to **Workflows → Import from File** and choose `ResolveAI_n8n_workflow.json`.
2. In the **1. AI Understand (Gemini)** node, set the `x-goog-api-key` header to your Gemini API key and use the `gemini-3.5-flash-lite` model in the URL.
3. **Publish** the workflow and copy the webhook **Production URL**.
4. Copy `config.example.js` to `config.js`, set the URL, and open `index.html` in a browser (or paste the URL under Settings).

Settings also has an **Offline demo** mode, which runs the same decision engine in the browser without the network.

## Demo scenarios

| Message | Outcome |
|---|---|
| "Where is my order #1023?" | Auto-reply with live status |
| "#1022 arrived damaged, refund" | Rs.299 refund auto-approved |
| "WORST service ever!! #1025 ..." | Escalated (angry customer), with an AI summary |
| "Refund #1021, headphones broke" | Escalated (Rs.1499 is above the auto-approval limit) |

## Tech

n8n · Google Gemini API · HTML/CSS/JS
