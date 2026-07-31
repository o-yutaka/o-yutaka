# o-yutaka — AI Agent & Automation Engineer

I build the control layer around AI models: **agent runtimes, permissioned tool use, provider routing, human approval, durable decision traces, evaluation, and operations dashboards**.

My portfolio is organized around one principle:

> A useful AI system must show what it decided, why it decided it, what it was allowed to do, and how the result can be reproduced.

## Start here

| Target role | Best repository | What to review first |
|---|---|---|
| AI Agent platform / LLM infrastructure | [BLACK](https://github.com/o-yutaka/BLACK) | Architecture, provider routing, decision ledger, replay, verification gates |
| Python + FastAPI + Next.js AI application | [AI-AI](https://github.com/o-yutaka/AI-AI) | Contract enforcement, approval flow, SQLite durability, API tests, Docker Compose |
| Planning / simulation / strict external APIs | [black-pokemon-championship](https://github.com/o-yutaka/black-pokemon-championship) | Legal-action runtime, deterministic fallback, submission gates, evaluation harness |
| Python autonomous-runtime experiments | [black-core](https://github.com/o-yutaka/black-core) | Event bus, task execution, semantic memory, timeout and subprocess isolation |

Detailed claim boundaries and review paths: [`PROJECT_EVIDENCE.md`](PROJECT_EVIDENCE.md)

## Primary engineering work

### BLACK — Decision & Trust Operating System

A full-stack decision layer above interchangeable AI models and tools.

```text
Mission → Context → Candidate Arena → Evaluation → Capability Router
        → Plugin Runtime → Evidence → Verification → Decision Ledger → Replay
```

Implemented evidence includes:

- TypeScript monorepo with CLI and Next.js operations UI
- OpenAI-compatible, Ollama, and deterministic provider adapters
- Capability routing with success, latency, and cost telemetry
- Permission and policy gates for external actions
- SQLite source of truth plus append-only JSONL mirror
- deterministic Decision DNA fingerprints and replay verification
- plugin SDK, provider SDK, schema generation, secret redaction, and core-freeze governance
- 140+ unit/integration tests, 53 Playwright E2E tests, and documented verification evidence

Repository: [github.com/o-yutaka/BLACK](https://github.com/o-yutaka/BLACK)

### AI Agent Control Plane

A smaller public system that can be reviewed and run quickly.

```text
Next.js dashboard → FastAPI → Agent Runtime
                 → Contract / Permission / Evidence checks
                 → Human approval → Executor → Audit trace → SQLite
```

Implemented evidence includes:

- Python, FastAPI, Pydantic
- TypeScript, Next.js App Router, React
- versioned allowed-action contracts
- deterministic candidate ranking and exact rejection reasons
- high-impact approval and rejection flow
- idempotency conflict detection
- durable SQLite runs and approval continuation after restart
- Docker Compose named volume and GitHub Actions matrix

Repository: [github.com/o-yutaka/AI-AI](https://github.com/o-yutaka/AI-AI)

### BLACK Pokémon Championship Agent

A reliability case study for a stateful agent connected to a strict external simulation engine.

The value is not the game domain itself. The engineering transfer is:

- execute only actions currently exposed by the external system
- preserve option-index semantics without guessing
- reject invalid selections before execution
- enforce deterministic fallback under timeout or policy failure
- validate exact submission layout and dependencies
- separate fast screening evidence from promotion claims
- keep decision overlays and truth-ledger diagnostics

Repository: [github.com/o-yutaka/black-pokemon-championship](https://github.com/o-yutaka/black-pokemon-championship)

## Skills demonstrated

```text
AI Agent Runtime       LLM / Provider Routing      Human-in-the-loop
Python / FastAPI       TypeScript / Next.js        Pydantic / Zod
Tool Calling           Audit / Decision Traces     Evaluation Harnesses
Docker / CI            SQLite / Event Ledgers      External API Contracts
Policy Gates           Retry / Failure Design      Local and Cloud Models
```

## How I work

- Build the smallest end-to-end vertical slice before expanding architecture.
- Treat external action contracts as the source of truth.
- Keep claims tied to tests, logs, screenshots, or reproducible commands.
- Separate screening results from production or promotion claims.
- Preserve explicit failure states instead of hiding them behind fallback output.
- Prefer reversible changes, stable interfaces, and documented non-goals.

## Current focus

- AI automation and business-process improvement
- reliable multi-step agents
- OpenAI-compatible provider abstraction
- approval-aware external actions
- evaluation, observability, and replay
- full-stack AI operations interfaces

## Review order

1. Open [AI-AI](https://github.com/o-yutaka/AI-AI) for the fastest runnable full-stack review.
2. Open [BLACK](https://github.com/o-yutaka/BLACK) for the larger platform architecture and evidence trail.
3. Open [black-pokemon-championship](https://github.com/o-yutaka/black-pokemon-championship) for strict runtime and evaluation engineering.
