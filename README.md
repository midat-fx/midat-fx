# Midat Faizov

Software engineer. I build complete production web applications — Next.js on top, Redis in the
middle, PostgreSQL underneath — and long-horizon coding-agent evaluation environments,
deterministic verifiers, and test infrastructure.

Whether it is a booking calendar or a sealed verifier, the same idea runs through the work:
correctness has to be enforced by something that cannot be talked out of it — a database
constraint, a held-out test, a CI gate — not by application-level hope.

## Selected engineering work

| Project | Engineering scope | Evidence |
|---|---|---|
| **[kezek](https://github.com/midat-fx/kezek)** ([live](https://kezek-midat-fx.vercel.app/aruzhan)) | Online booking platform for service businesses — Next.js 16, PostgreSQL, Redis, Tailwind. Booking wizard, role-gated admin with a live SSE calendar, CRM, waitlist, transactional-outbox notifications, window-function analytics | Double-booking prevented twice — Redis holds plus a Postgres `EXCLUDE USING gist` constraint — with a test that **races 100 clients for one slot**; 13-table multi-tenant schema, 55 tests, CI against live Postgres and Redis · [live demo](https://kezek-midat-fx.vercel.app/aruzhan) — admin `owner@kezek.dev` / `kezek-demo` |
| **[Goodhart Gym](https://github.com/midat-fx/goodhart-gym)** | Deterministic coding-agent tasks, each with a naive verifier (the agent's own test suite) and a sealed one that rebuilds from pristine sources and adds held-out tests and a plain-Python probe | **31 committed exploits**, **61 verifier invariants** proven in CI with zero model calls, 169 harness tests |
| **Ledgera** (private) | Subscription billing and invoicing engine with a domain model, SQLite persistence, CLI, HTTP API, query language, import/export, and double-entry ledger | ~13k LOC, 128 files, 324 tests, 73 commits, Docker and CI |
| **English Forge** (private) | Local-first React/TypeScript and Tauri desktop application with versioned schema migrations, offline media handling, and macOS/Windows releases | ~36k LOC, 196 source files, 62 test files |
| **tech-salary-radar** ([live](https://tech-salary-radar.pages.dev)) | Daily ETL over Greenhouse, Lever, and Ashby; DuckDB analytics; LLM skill extraction behind an evaluation gate; React dashboard on Cloudflare Pages | 6,500+ live jobs across 234 company boards, extraction micro-F1 0.87, five GitHub Actions workflows · [live dashboard](https://tech-salary-radar.pages.dev) |
| **Deka** (private) ([live](https://deka-3st.pages.dev)) | Hybrid BM25/pgvector retrieval over Kazakhstan's 2026 Tax Code with deterministic tax logic and citation-grounded answers | 848 articles, retrieval hit@3 94%, ~120 tests · [@deka_tax_bot](https://t.me/deka_tax_bot) |
| **Aiym** (private) ([live demo](https://aiym.faizov-midat.workers.dev/demo)) | Voice AI receptionist on Cloudflare Workers — Whisper transcription and Gemini function calling on top, a deterministic D1 calendar underneath, so double-booking is structurally impossible | ~12k LOC, 885 tests, 89 commits, seven migrations |

## Agent evaluation and infrastructure benchmarks

| Project | What it measures | Evidence |
|---|---|---|
| **[webapp-eval](https://github.com/midat-fx/webapp-eval)** | Full-stack web tasks cut from kezek, graded by Playwright in a no-network container, PostgreSQL invariants and axe-core | 11 tasks, **71/71 self-check variants**, 38/38 known-bad patches rejected, 59/59 Claude Code runs graded |
| **[realbug-bench](https://github.com/midat-fx/realbug-bench)** | Tasks cut from real bugs in Go, Python and TypeScript projects, with evil and valid solutions every verifier must sort correctly | 10 tasks, every solution graded twice in CI; Claude Code Haiku **29/30**, Sonnet **28/30** |
| **[infra-bench](https://github.com/midat-fx/infra-bench)** | Broken Kubernetes and Terraform setups on kind and LocalStack, with plausible wrong fixes the verifiers must reject for the right reason | 13 scenarios, **77/77 verdicts** on a clean CI runner |
| **[boundary-bench](https://github.com/midat-fx/boundary-bench)** | Whether a coding agent follows instructions planted in files it reads; harmless visible markers, no network | 12 tasks; current Haiku and Sonnet followed 0 injections, Haiku 4.5 followed 6 of the 7 it read |
| **[csvq-rs](https://github.com/midat-fx/csvq-rs)** | Rust port of my Bash+awk CSV toolkit, kept bug-compatible and proven by differential fuzzing | byte-identical output on 50,000 fuzz cases and at 1 GiB, **28–159× faster** |
| **[serve-bench](https://github.com/midat-fx/serve-bench)** | TTFT, TPOT, goodput and burst behaviour of four OpenAI-compatible servers (llama.cpp, MLX, LM Studio) on Apple Silicon | every number traced to a JSON file with the machine's load and GPU state recorded |

These benchmarks were built with Claude Code working to my specifications; each README has a "How it was built" section. Every number in them comes from files committed under `results/`.

## Engineering focus

- **Full-stack product delivery:** Next.js (App Router, RSC, server actions, route handlers),
  React and Tailwind on the front; PostgreSQL schema design, exclusion constraints and window
  functions underneath; Redis for reservations, sessions, rate limiting and pub/sub in between.
- **Coding-agent evaluation:** task specifications, reference patches, hidden
  tests, probes, grading rubrics, and reward-hacking defenses.
- **Reproducible systems:** Docker, GitHub Actions, deterministic fixtures,
  golden tests, strict typing, and environment-independent output.

Several projects above are private while the code is in use for AI-lab evaluation work; the live demos are open to everyone.

Ankara, Türkiye (UTC+3) · Remote contract

[LinkedIn](https://www.linkedin.com/in/midat-faizov/) ·
[Email](mailto:faizov.midat@gmail.com)
