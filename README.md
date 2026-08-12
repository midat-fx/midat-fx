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
| **[kezek](https://github.com/midat-fx/kezek)** | Online booking platform for service businesses — Next.js 16, PostgreSQL, Redis, Tailwind. Booking wizard, role-gated admin with a live SSE calendar, CRM, waitlist, transactional-outbox notifications, window-function analytics | Double-booking prevented twice — Redis holds plus a Postgres `EXCLUDE USING gist` constraint — with a test that **races 100 clients for one slot**; 13-table multi-tenant schema, 55 tests, CI against live Postgres and Redis |
| **[Goodhart Gym](https://github.com/midat-fx/goodhart-gym)** | Ten deterministic coding-agent tasks with visible and held-out tests, reference solutions, plain-Python probes, and a sealed verifier that rebuilds from pristine sources | **21 adversarial submissions**, six reward-hacking classes, **41/41 verifier invariants**, 88 harness tests |
| **Private TypeScript platform** | Subscription billing and invoicing engine with a domain model, SQLite persistence, CLI, HTTP API, query language, import/export, and double-entry ledger | ~20k LOC, 138 files, 39 test files, 65 commits, Docker and CI |
| **[English Forge](https://github.com/midat-fx/english-forge)** | Local-first React/TypeScript and Tauri desktop application with versioned schema migrations, offline media handling, and macOS/Windows releases | ~36k LOC, 276 files, 64 test files |
| **[tech-salary-radar](https://github.com/midat-fx/tech-salary-radar)** | Daily ETL over Greenhouse, Lever, and Ashby; DuckDB analytics; LLM skill extraction behind an evaluation gate; React dashboard on Cloudflare Pages | 6,370+ live jobs, extraction micro-F1 0.87, five GitHub Actions workflows · [live dashboard](https://tech-salary-radar.pages.dev) |
| **[Deka](https://github.com/midat-fx/deka)** | Hybrid BM25/pgvector retrieval over Kazakhstan's 2026 Tax Code with deterministic tax logic and citation-grounded answers | 848 articles, retrieval hit@3 94%, ~120 tests |

## Engineering focus

- **Full-stack product delivery:** Next.js (App Router, RSC, server actions, route handlers),
  React and Tailwind on the front; PostgreSQL schema design, exclusion constraints and window
  functions underneath; Redis for reservations, sessions, rate limiting and pub/sub in between.
- **Coding-agent evaluation:** task specifications, reference patches, hidden
  tests, probes, grading rubrics, and reward-hacking defenses.
- **Reproducible systems:** Docker, GitHub Actions, deterministic fixtures,
  golden tests, strict typing, and environment-independent output.

Ankara, Türkiye (UTC+3) · Remote contract

[LinkedIn](https://www.linkedin.com/in/midat-faizov/) ·
[Email](mailto:faizov.midat@gmail.com)
