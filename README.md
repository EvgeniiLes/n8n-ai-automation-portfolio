# n8n + Claude AI Automation Portfolio

A set of AI automation and agent workflows built with **n8n** and the **Claude API**, demonstrated on a realistic fictional e-commerce store, **GearUp** (sports/fitness equipment, retail + wholesale to gyms).

> These are showcase projects built end-to-end on test data to demonstrate design and implementation skills — not deployments for a real paying client. Every workflow is fully functional and was tested against live n8n with real API calls.

## What's inside

| # | Workflow | What it does |
|---|----------|---------------|
| 00 | Error Handler | Any failed automation sends a Telegram alert and logs a row to `ErrorLog` |
| 01 | B2B Lead Qualification | Wholesale form → validation → company website enrichment → **Claude scores the lead 0–100** and drafts a first email → CRM → hot leads trigger an instant Telegram alert, warm/hot leads get the email |
| 02 | Owner Ops AI Agent | **AI agent for the store owner in Telegram**: "how much did we sell yesterday?", "what's running out?", "top 5 this month", "create a promo code" |
| 03 | Customer Support Bot | **24/7 support bot**: FAQ, order status (with email verification), return requests, hand-off to a human |
| 04 | Order Sync & Inventory | Order webhook (Shopify-style) → duplicate protection → order saved → stock deducted → reorder alert |
| 05 | Daily AI Report | Every day at 09:00: KPIs computed in code, Claude adds a short commentary and 2 action items, report sent to Telegram |
| 06 | Stock-out Forecast | Combines sales velocity, incoming purchase orders, supplier lead time and MOQ to predict the exact day each SKU runs out, with a Telegram alert and Claude's action plan |
| 07 | RAG Knowledge Ingest | Documents → chunking → OpenAI embeddings → Qdrant vector store, with the source file stored as metadata |
| 08 | RAG Knowledge Assistant | Telegram agent that answers **only from the knowledge base**, cites the source file, and logs unanswered questions to a `KB_Gaps` sheet |

Workflows 00–06 import cleanly into n8n 2.40+ with no node-parameter errors, and their Code-node logic was run against test payloads. Workflows 07–08 (RAG) were imported into n8n 2.41 and checked against the installed node definitions (node types, versions and parameters all valid); they have not been run end-to-end against a live Qdrant/OpenAI account, so connect your own Qdrant, OpenAI, Anthropic and Telegram credentials to try them.

## Repository structure

```
workflows/        9 JSON files, ready to import into n8n (with placeholders for your own Sheet ID / chat ID)
screenshots/       canvas previews from a test n8n instance (credentials are fake)
case-studies/      5 detailed write-ups with architecture, features and screenshots
knowledge-base/    sample documents for the RAG assistant demo
```

## Stack

n8n · Claude (Anthropic API) · AI Agent + tools · RAG / Qdrant vector store · OpenAI embeddings · Google Sheets as CRM/DB · Telegram Bot API · Gmail · Webhooks · JavaScript

## Case studies

- [RAG Knowledge Assistant with Source Citations](case-studies/05-rag-knowledge-assistant.md) *(new)*
- [Stock-out Forecast & Reorder Alerts](case-studies/01-stockout-forecast.md)
- [AI Customer Support Bot](case-studies/02-support-bot.md)
- [AI Lead Qualification & CRM Routing](case-studies/03-lead-qualification.md)
- [Owner AI Agent & Daily Business Report](case-studies/04-owner-agent-report.md)

## Related project

- [mcp-gearup-ops](https://github.com/EvgeniiLes/mcp-gearup-ops): a Python **MCP server** for the same GearUp store (sales, stock, orders, leads, FAQ and a guarded promo-code tool), usable from Claude Desktop, Claude Code or Cursor, with end-to-end tests

## Reliability

Every workflow includes retries on external calls, a shared error-handling workflow (Telegram alert + error log), input validation and duplicate protection.

## Contact

Open to automation and AI-agent work — n8n, Make, Claude/OpenAI integrations, Telegram bots, and business-process automation.
