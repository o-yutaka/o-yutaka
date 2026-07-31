# o-yutaka — AI Agent & Automation Engineer

I build the control layer around AI models: **agent runtimes, permissioned tool use, OpenAI-compatible providers, human approval, deterministic decision traces, evaluation, and operations dashboards**.

> A useful AI system must show what it decided, why it decided it, what it was allowed to do, whether it executed, and how the result can be reproduced.

## Featured portfolio

| Project | Working evidence | Review |
|---|---|---|
| **AI Agent Control Plane** | Browser-operated approval, blocking, idempotency, deterministic fingerprints, FastAPI, Next.js, real provider/tool boundaries, SQLite durability | **[Open live proof](https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html)** · [Repository](https://github.com/o-yutaka/AI-AI) |
| **BLACK** | Decision and trust platform with provider routing, policy gates, evidence, replay, CLI, and operations UI | [Repository](https://github.com/o-yutaka/BLACK) |
| **BLACK Pokémon Championship Agent** | Strict external-action contracts, deterministic fallback, planning, evaluation, and submission verification | [Repository](https://github.com/o-yutaka/black-pokemon-championship) |

Detailed claim boundaries and review paths: [`PROJECT_EVIDENCE.md`](PROJECT_EVIDENCE.md)

## AI Agent Control Plane — fastest review

[![AI Agent Control Plane proof](https://raw.githubusercontent.com/o-yutaka/AI-AI/main/docs/assets/proof/ai-agent-control-plane-proof.gif)](https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html)

```text
OpenAI-compatible provider → untrusted candidate actions
                           → contract / permission / evidence checks
                           → sensitive-data and exact-tool gates
                           → deterministic ranking
                           → human approval
                           → fixed HTTP tool adapter
                           → redacted result / error
                           → audit trace + SQLite + idempotency
```

### Browser-verified proof

```json
{
  "different_run_ids_same_input": true,
  "duplicate_execution_count": 1,
  "blocked_execution_count": 0,
  "conflict_execution_count": 0,
  "approved_execution_count": 1
}
```

The Chromium workflow operates the public demo and verifies:

- same canonical input produces the same SHA-256 request fingerprint even with different run IDs
- duplicate idempotency replay returns the existing run without a second execution
- conflicting input under the same key is rejected
- contract, permission, evidence, and unregistered-tool violations are blocked with execution count `0`
- a high-impact action remains at execution count `0` before approval and becomes `1` after approval
- committed 1440 px desktop proof, 390 px mobile proof, and a short GIF

### Backend implementation

- Python, FastAPI, Pydantic, TypeScript, Next.js, and React
- OpenAI-compatible `/chat/completions` candidate planner
- provider observations redacted before transmission
- typed provider output and undeclared tool-operation rejection
- fixed-host, fixed-method, fixed-path HTTP adapters
- sensitive adapter headers restricted to environment-variable references
- response limits enforced while streaming, disabled redirects, and timeouts
- recursive secret/PII redaction before persistence, API return, approvals, audit events, and errors
- versioned action contracts, permissions, evidence requirements, deterministic ranking, and exact rejection reasons
- named approval and rejection flow
- explicit execution count, idempotent replay, and conflict detection
- SQLite WAL, busy timeout, unique idempotency keys, and restart-safe approvals
- committed Python runtime/development locks and npm lockfile
- non-root, read-only Docker Compose stack with health-gated startup

### Verified engineering gates

```text
Python 3.11 / 3.12     Ruff + 64 tests PASS
Next.js                npm lock + static export PASS
Dependency locks       runtime / dev / frontend PASS
Browser proof          Chromium interaction contract PASS
Docker                 API + web image builds PASS
Compose                real startup + both health checks PASS
```

Live proof: <https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html>

Evidence manifest: <https://github.com/o-yutaka/AI-AI/blob/main/docs/assets/proof/visual-proof-manifest.json>

Repository: <https://github.com/o-yutaka/AI-AI>

The clean GitHub Pages URL is prepared at `https://o-yutaka.github.io/AI-AI/`, but it is not represented as live until repository-level Pages is enabled and HTTP verification succeeds.

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
- 140+ unit/integration tests, 53 Playwright E2E checks, Storybook, and documented verification evidence

Repository: <https://github.com/o-yutaka/BLACK>

## BLACK Pokémon Championship Agent

A reliability case study for a stateful agent connected to a strict external simulation engine.

Transferable engineering:

- execute only actions currently exposed by the external system
- preserve option-index semantics without guessing
- reject invalid selections before execution
- enforce deterministic fallback under timeout or policy failure
- validate exact submission layout and dependencies
- separate crash screening from promotion claims
- preserve decision overlays and truth-ledger diagnostics

Repository: <https://github.com/o-yutaka/black-pokemon-championship>

## Skills demonstrated

```text
AI Agent Runtime       LLM / Provider Routing      Human-in-the-loop
Python / FastAPI       TypeScript / Next.js        Pydantic / Zod
Tool Calling           Audit / Decision Traces     Evaluation Harnesses
Docker / CI            SQLite / Event Ledgers      External API Contracts
Policy Gates           Privacy Boundaries          Failure Design
```

## Review order

1. Open the [AI-AI live proof](https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html).
2. Inspect the [proof manifest](https://github.com/o-yutaka/AI-AI/blob/main/docs/assets/proof/visual-proof-manifest.json).
3. Open [AI-AI](https://github.com/o-yutaka/AI-AI) for implementation, tests, locks, Docker, and claim boundaries.
4. Open [BLACK](https://github.com/o-yutaka/BLACK) for the larger decision-platform architecture.
5. Open [black-pokemon-championship](https://github.com/o-yutaka/black-pokemon-championship) for strict runtime and evaluation engineering.
