# o-yutaka — AI Agent / Automation / Platform Engineer

I build the engineering layer around AI models: **agent runtimes, business automation, permissioned tool use, provider routing, human approval, evaluation, external API integration, reproducible execution, and terminal-first operations**.

> A useful AI system must show what it decided, why it decided it, what it was allowed to do, whether it executed, and how the result can be reproduced.

## Portfolio architecture

These repositories are presented as one engineering system, not as unrelated demos.

```text
                         BLACK
                Decision / Trust Platform
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
     AI-AI              popopo            Pokémon
 Business Agent       AI Product        Planning / Eval
 Control Plane        + API Policy       + Simulation
        │                  │                  │
        └──────────────┬───┴──────────────────┘
                       │
                 black-core
               Python Agent Runtime
                       │
              Agent Operations
             openclaw-bot-review*
```

`*` Fork/adaptation lineage is disclosed in that repository and is not presented as an original upstream project.

## Featured portfolio — every entry has a job

| Project | What it proves | Best-fit roles |
|---|---|---|
| **[BLACK](https://github.com/o-yutaka/BLACK)** | Decision platform, LLM/provider routing, plugins, evidence, replay, CLI, web operations | AI Platform / Agent / LLM / TypeScript |
| **[AI-AI](https://github.com/o-yutaka/AI-AI)** | Business AI Agent control plane, FastAPI, Next.js, approval, tool boundaries, idempotency, audit | AI Automation / Python / FastAPI / Agent |
| **[popopo](https://github.com/o-yutaka/popopo)** | AI product integration, FastAPI, OAuth2, external APIs, policy, privacy, live evidence | AI Product / API Integration / Full-stack |
| **[BLACK Pokémon Championship](https://github.com/o-yutaka/black-pokemon-championship)** | Stateful planning, strict external action contracts, simulation, fallback, evaluation, reproducible artifacts | Agent Planning / Evaluation / Reliability |
| **[black-core](https://github.com/o-yutaka/black-core)** | Python-first runtime, event bus, agent loop, executor, memory, controlled code execution | Python / Agent Runtime |
| **[openclaw-bot-review](https://github.com/o-yutaka/openclaw-bot-review)** | Agent operations dashboard, sessions, models, tokens, health, skills, channels | Agent Operations / Next.js / TypeScript |

## 1. BLACK — Decision & Trust Operating System

```text
Mission → Context → Candidate Arena → Evaluation → Capability Router
        → Plugin Runtime → Evidence → Verification → Decision Ledger → Replay
```

Evidence includes provider routing, plugin/provider SDKs, deterministic Decision DNA, replay verification, SQLite + JSONL ledgering, secret redaction, CLI, Next.js operations UI, 140+ unit/integration tests, 53 Playwright E2E checks, Storybook, and CI verification.

**Recruiter path:** `README.md` → `ARCHITECTURE.md` → `packages/runtime` → `packages/core` → `docs/evidence/`.

## 2. AI-AI — Business AI Agent Control Plane

A runnable full-stack reference for contract-aware, auditable, human-approved AI agents.

```text
OpenAI-compatible planner
        ↓
Contract / Permission / Evidence / Privacy gates
        ↓
Deterministic ranking
        ↓
Human approval when required
        ↓
Fixed tool adapter
        ↓
Audit / SQLite / Idempotent replay
```

Verified browser proof covers duplicate prevention, conflict rejection, blocked actions, approval gating, desktop/mobile evidence, FastAPI, Next.js, Docker, and CI.

**Live proof:** https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html

## 3. popopo — Production-oriented AI Product Integration

A working AI product prototype demonstrating:

- FastAPI + strict Pydantic contracts
- OAuth2 client credentials
- External API adapters
- Consent / crisis / privacy / cooldown policy
- Allowlisted retrieval
- Deterministic credential-free fallback
- Redacted live API evidence
- Automated API/media/submission tests
- GitHub Actions + Docker

The transferable pattern is:

```text
Event → Policy → Model → Allowlist → External API → Delivery Policy → Evidence
```

**Public demo:** https://o-yutaka.github.io/popopo/

## 4. BLACK Pokémon Championship — Stateful Agent Reliability

A stateful agent connected to a strict external simulation engine.

It proves:

- execute only currently exposed actions
- preserve option-index semantics
- reject invalid selections before execution
- deterministic fallback under timeout/error
- exact submission artifact verification
- regression/crash/speed screening
- honest separation of local screening and official evaluation

This is the planning/evaluation proof behind the business-agent work rather than a claim that the domain heuristic is universal.

## 5. black-core — Python Agent Runtime

Python-first runtime covering Event Bus, Task Intelligence, Goal Generation, Agent System, Executor/Code Runner, Autonomous Loop, and FAISS semantic memory.

The repository is being hardened toward the same portfolio gates used by the other projects: typed contracts, deterministic tests, CI, dependency locking, benchmarks, and explicit execution-policy verification.

## 6. openclaw-bot-review — Agent Operations

A dashboard-oriented engineering study around agent operations: model management, sessions, token usage, gateway health, skills, channels, alerts, and scheduling.

**Lineage is disclosed in the repository.** It is shown as architecture/operations experience, not as an original upstream implementation claim.

## Skill matrix

```text
AI Agent Runtime       LLM / Provider Routing      AI Automation
Python / FastAPI       TypeScript / Next.js        Pydantic / Zod
Tool Calling           Human-in-the-loop           Audit / Decision Trace
Evaluation Harness     Simulation / Planning       External API Contracts
OAuth2 / Policy        Docker / CI                 SQLite / Ledgers
Failure Recovery       Privacy Boundaries           Terminal-first Operations
```

## Review order

### Fastest 5-minute review

1. [AI-AI live proof](https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html)
2. [AI-AI repository](https://github.com/o-yutaka/AI-AI)
3. [BLACK repository](https://github.com/o-yutaka/BLACK)

### Deep technical review

4. [popopo](https://github.com/o-yutaka/popopo)
5. [BLACK Pokémon Championship](https://github.com/o-yutaka/black-pokemon-championship)
6. [black-core](https://github.com/o-yutaka/black-core)
7. [openclaw-bot-review](https://github.com/o-yutaka/openclaw-bot-review)

## Portfolio standard

Every featured repository is expected to expose the same evidence chain:

```text
Problem
  ↓
Architecture
  ↓
Working implementation
  ↓
Tests / CI
  ↓
Failure handling
  ↓
Reproducible evidence
  ↓
Claim boundary
  ↓
Business transfer
```

The goal is not to show many repositories. The goal is for **every featured repository to survive technical review on its own**.
