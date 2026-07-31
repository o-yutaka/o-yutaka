# o-yutaka — AI Agent & Automation Engineer

I build the control layer around AI models: **agent runtimes, permissioned tool use, OpenAI-compatible providers, human approval, durable decision traces, evaluation, and operations dashboards**.

> A useful AI system must show what it decided, why it decided it, what it was allowed to do, and how the result can be reproduced.

## Featured portfolio

| Project | Working evidence | Review |
|---|---|---|
| **AI Agent Control Plane** | Live interactive approval flow, FastAPI, Next.js, OpenAI-compatible planner, allow-listed HTTP tools, SQLite durability | **[Open live demo](https://o-yutaka.github.io/AI-AI/)** · [Repository](https://github.com/o-yutaka/AI-AI) |
| **BLACK** | Decision and trust platform with provider routing, policy gates, evidence, replay, CLI, and operations UI | [Repository](https://github.com/o-yutaka/BLACK) |
| **BLACK Pokémon Championship Agent** | Strict external-action contracts, deterministic fallback, planning, evaluation, and submission verification | [Repository](https://github.com/o-yutaka/black-pokemon-championship) |

Detailed claim boundaries and review paths: [`PROJECT_EVIDENCE.md`](PROJECT_EVIDENCE.md)

## AI Agent Control Plane — fastest review

```text
OpenAI-compatible provider → candidate actions
                           → contract / permission / evidence checks
                           → deterministic selection
                           → human approval
                           → allow-listed tool adapter
                           → audit trace → SQLite
```

Implemented evidence:

- public interactive browser demo requiring no secret and creating no external side effect
- Python, FastAPI, Pydantic, TypeScript, Next.js, and React
- OpenAI-compatible `/chat/completions` candidate planner
- provider output validated as typed action candidates
- rejection of undeclared provider tool operations
- fixed-host, fixed-method, fixed-path HTTP JSON adapters
- environment-only secret resolution, disabled redirects, timeout, and response-size bounds
- versioned allowed-action contracts and per-action permissions
- deterministic ranking and exact rejection reasons
- high-impact approval and rejection flow
- idempotency conflict detection
- durable SQLite runs and approval continuation after restart
- Python 3.11/3.12, Ruff, static export, and Docker builds in GitHub Actions

Live demo: https://o-yutaka.github.io/AI-AI/

Repository: https://github.com/o-yutaka/AI-AI

## BLACK — Decision & Trust Operating System

A full-stack decision layer above interchangeable AI models and tools.

```text
Mission → Context → Candidate Arena → Evaluation → Capability Router
        → Plugin Runtime → Evidence → Verification → Decision Ledger → Replay
```

Implemented evidence includes:

- TypeScript monorepo with CLI and Next.js operations UI
- OpenAI-compatible, Ollama, and deterministic provider adapters
- capability routing with success, latency, and cost telemetry
- permission and policy gates for external actions
- SQLite source of truth plus append-only JSONL mirror
- deterministic Decision DNA fingerprints and replay verification
- plugin SDK, provider SDK, schema generation, secret redaction, and core-freeze governance
- unit/integration tests, Playwright E2E tests, and documented verification evidence

Repository: https://github.com/o-yutaka/BLACK

## BLACK Pokémon Championship Agent

A reliability case study for a stateful agent connected to a strict external simulation engine.

The transferable engineering is:

- execute only actions currently exposed by the external system
- preserve option-index semantics without guessing
- reject invalid selections before execution
- enforce deterministic fallback under timeout or policy failure
- validate exact submission layout and dependencies
- separate fast screening evidence from promotion claims
- keep decision overlays and truth-ledger diagnostics

Repository: https://github.com/o-yutaka/black-pokemon-championship

## Skills demonstrated

```text
AI Agent Runtime       LLM / Provider Routing      Human-in-the-loop
Python / FastAPI       TypeScript / Next.js        Pydantic / Zod
Tool Calling           Audit / Decision Traces     Evaluation Harnesses
Docker / CI            SQLite / Event Ledgers      External API Contracts
Policy Gates           Failure Design              Local and Cloud Models
```

## How I work

- Build the smallest end-to-end vertical slice before expanding architecture.
- Treat external action contracts as the source of truth.
- Keep claims tied to tests, logs, screenshots, or reproducible commands.
- Separate screening results from production or promotion claims.
- Preserve explicit failure states instead of hiding them behind fallback output.
- Prefer reversible changes, stable interfaces, and documented non-goals.

## Review order

1. Open the [AI-AI live demo](https://o-yutaka.github.io/AI-AI/) for the fastest product review.
2. Open [AI-AI](https://github.com/o-yutaka/AI-AI) for the implementation and test evidence.
3. Open [BLACK](https://github.com/o-yutaka/BLACK) for the larger platform architecture.
4. Open [black-pokemon-championship](https://github.com/o-yutaka/black-pokemon-championship) for strict runtime and evaluation engineering.
