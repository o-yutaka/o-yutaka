# Project Evidence Index

This file separates implemented evidence from future work so each repository can be reviewed without relying on broad portfolio claims.

## 1. BLACK

Repository: <https://github.com/o-yutaka/BLACK>

### Problem addressed

AI applications often route models and tools without preserving why a provider was chosen, which evidence supported a result, whether an action was permitted, or whether the same decision can be reproduced later.

### Implemented system

- Mission compiler and shared runtime used by both CLI and web API
- candidate arena and policy evaluation
- capability/provider router
- OpenAI-compatible, Ollama, and deterministic provider adapters
- plugin and provider SDKs
- evidence verification and decision ledger
- SQLite source of truth with append-only JSONL mirror
- deterministic Decision DNA and replay verification
- Next.js operations interface, Storybook, and accessibility E2E checks
- secret broker and redaction tests
- core-freeze policy enforced in CI

### Reproducible review path

1. `README.md`
2. `ARCHITECTURE.md`
3. `docs/evidence/acceptance-criteria.md`
4. `docs/evidence/ci-verification.md`
5. `docs/contracts/`
6. `packages/core/`, `packages/runtime/`, `packages/providers/`, `packages/storage/`

Primary verification command:

```bash
pnpm run verify
```

### Evidence currently documented in the repository

- 140+ unit/integration tests
- 53 Playwright E2E tests
- `packages/core` coverage reported as 81.39%
- secret scan with zero findings
- real OpenAI-compatible provider verification recorded against LM Studio

### Explicit non-claims

BLACK is a production-ready MVP/reference platform, not proof of multi-region operation, enterprise customer traffic, or audited regulatory compliance.

---

## 2. AI Agent Control Plane

Repository: <https://github.com/o-yutaka/AI-AI>

### Problem addressed

A business agent should not call any tool it can describe. It should execute only actions currently allowed by the external system, require permissions and evidence, pause high-impact operations for human approval, prevent duplicate side effects, and preserve the decision trace.

### Implemented system

- FastAPI and Pydantic API boundary
- versioned action contract
- permission and evidence checks
- deterministic ranking and rejection reasons
- named approval/rejection flow
- idempotency and conflicting-request detection
- structured executor failures
- pluggable run repository
- restart-safe SQLite persistence
- Next.js operations dashboard
- Docker Compose persistent volume
- GitHub Actions for Python, frontend build, and Docker images

### Reproducible review path

1. `README.md`
2. `control_plane/runtime.py`
3. `control_plane/store.py`
4. `tests/test_runtime.py`
5. `tests/test_persistence.py`
6. `docs/adr/0001-durable-run-store.md`

Primary commands:

```bash
docker compose up --build
pytest -q
ruff check .
```

### Explicit non-claims

This is a durable single-node reference system. It does not claim production authentication, tenant isolation, PostgreSQL, durable distributed queues, real SaaS connectors, load-test evidence, or production SLOs.

---

## 3. BLACK Pokémon Championship Agent

Repository: <https://github.com/o-yutaka/black-pokemon-championship>

### Problem addressed

A stateful agent connected to an external engine must select only legal option indexes, preserve exact engine semantics, stay within runtime budgets, package an exact submission tree, and distinguish crash screening from performance claims.

### Implemented system

- reviewed canonical deck and entrypoint
- source/runtime/archive layout contracts
- exact required-file allow-list
- deck and ACE-spec validation
- legal selection validator
- deterministic fallback for timeout, exceptions, and invalid selections
- decision overlay with runtime source, warnings, and truth ledger
- reproducible submission builder
- fast parallel regression/crash screen

### Reproducible review path

1. `README.md`
2. `submission_contract.py`
3. `black_engine/runtime.py`
4. `black_engine/policy.py`
5. `scripts/static_gate.py`
6. `scripts/build_submission.py`
7. `scripts/fast_eval.py`

Primary commands:

```bash
python scripts/static_gate.py
python -m pytest -q
python scripts/build_submission.py --cg-dir /path/to/cg --out artifacts/submission.zip
```

### Engineering transfer

| Competition runtime | Business-agent equivalent |
|---|---|
| Engine-exposed option indexes | API/tool allow-list |
| Hidden-state discipline | Evidence and observation boundary |
| Invalid selection rejection | Contract validation |
| Turn/resource planning | Cost, permissions, and workflow state |
| Deterministic fallback | Safe degraded operation |
| Replay/evaluation harness | Regression and policy promotion gates |

### Explicit non-claims

Fast evaluation is documented as crash, speed, and regression screening. It is not presented as official leaderboard evidence or a universal business-agent benchmark.

---

## Review principle

```text
Claim → Source file → Test or command → Artifact/log → Stated limitation
```

A project is considered portfolio-ready only when a reviewer can follow that chain without private context.
