# Midat Faizov

AI engineer building grounded LLM products end to end: retrieval, evals, voice, and $0-infra deployments on Cloudflare Workers.

**What I optimize for:** LLMs that cite or refuse, deterministic code in legally and financially sensitive paths, and eval gates in CI so quality regressions fail the build.

## Projects

| Project | What it is | Proof |
|---|---|---|
| **[Deka](https://github.com/midat-fx/deka)** | Grounded Telegram assistant for Kazakhstan's 2026 Tax Code — hybrid BM25 + vector RAG over all 848 articles; answers must cite an article or refuse | retrieval **hit@3 94%**, MRR 0.71, eval gate in CI · [live bot](https://t.me/deka_tax_bot) |
| **[tech-salary-radar](https://github.com/midat-fx/tech-salary-radar)** | Self-updating dashboard of the tech job market — daily ETL over Greenhouse/Lever/Ashby ATS APIs, LLM skill extraction, DuckDB analytics | **6,370+ live jobs** · extraction **micro-F1 0.87**, CI-gated · [live dashboard](https://tech-salary-radar.pages.dev) |
| **[Aiym](https://github.com/midat-fx/aiym-receptionist)** | Voice AI receptionist — Whisper STT + Gemini function calling + ElevenLabs TTS; a deterministic booking engine owns the calendar, so double-booking is impossible at the DB level | [live demo](https://aiym.faizov-midat.workers.dev/demo) — book an appointment in 60 seconds |
| **[DifyGram](https://github.com/midat-fx/difygram)** | Turn any Dify / n8n / HTTP agent into a Telegram bot with ChatGPT-style streaming — one free Cloudflare Worker | **107 unit tests, zero runtime dependencies** · [demo bot](https://t.me/difygram_demo_bot) |

Also: [English Forge](https://github.com/midat-fx/english-forge) — local-first desktop English trainer for macOS & Windows (placement, SRS, listening & speaking; no account, no cloud).

## How I work

- **Eval-first:** golden sets and CI gates on every LLM path — retrieval hit@k, answer faithfulness, extraction F1. A regression blocks the deploy.
- **LLM where it helps, determinism where it must:** tax-regime logic, booking calendars, and money math are pure, unit-tested code; the LLM only understands language.
- **$0/month production:** Cloudflare Workers / Pages / D1, GitHub Actions cron, free-tier LLMs — every project above runs live for free.

**Stack:** TypeScript · Python · Cloudflare Workers/Pages/D1/KV · Gemini · Whisper · BM25 / pgvector · DuckDB · Vitest

📫 midat.faizov@gmail.com
