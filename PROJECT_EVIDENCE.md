# Project Evidence Index

This index separates implemented evidence from future work so every portfolio claim can be reviewed without private context.

## Review rule

```text
Claim → source file → test or command → artifact/log → stated limitation
```

A project is portfolio-ready only when a reviewer can follow that chain.

---

## 1. AI Agent Control Plane

Repository: <https://github.com/o-yutaka/AI-AI>

Verified public mirror: <https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html>

Deployment evidence: <https://github.com/o-yutaka/AI-AI/blob/main/docs/live-status.json>

### Problem addressed

A business agent should not call any tool it can describe. It should execute only actions currently allowed by the external system, require permissions and evidence, pause high-impact operations for human approval, prevent duplicate side effects, and preserve the decision trace.

### Implemented system

- FastAPI and Pydantic API boundary
- versioned action contract
- permission and evidence checks
- deterministic runtime ranking and rejection reasons
- named approval and rejection flow
- idempotency and conflicting-request detection
- structured executor failures
- restart-safe SQLite persistence
- Next.js operations dashboard
- OpenAI-compatible `/chat/completions` candidate planner
- typed validation of provider-generated candidates
- rejection of undeclared provider tool operations
- operator-configured HTTP tool registry
- exact tool and operation lookup
- fixed host, method, and path templates
- disabled redirects and request timeouts
- environment-only adapter secrets
- Docker Compose persistent volume
- GitHub Actions for Python, Ruff, frontend build, static export, and Docker images
- self-contained public browser demonstration with external connections disabled by CSP

### Reproducible review path

1. public interactive mirror
2. `README.md`
3. `control_plane/runtime.py`
4. `control_plane/providers.py`
5. `control_plane/tools.py`
6. `control_plane/store.py`
7. `tests/test_runtime.py`
8. `tests/test_persistence.py`
9. `tests/test_providers.py`
10. `tests/test_tools.py`
11. `docs/adr/0001-durable-run-store.md`
12. `docs/adr/0002-provider-tool-boundary.md`
13. `docs/portfolio-audit-2026-08-01.md`

Primary commands:

```bash
docker compose up --build
pytest -q
ruff check .
```

### Current public-proof boundary

- The RawGitHack mirror is independently verified as HTTP 200 in `docs/live-status.json`.
- The clean GitHub Pages URL is prepared but must not be described as live until repository-level Pages is enabled and the evidence file records successful build, deployment, and HTTP verification.
- The browser demo simulates provider and executor behavior locally; the real OpenAI-compatible provider and HTTP adapters are backend implementations.
- The current screenshot is existence evidence, not readable trace evidence; the repository audit requires a higher-resolution desktop and mobile replacement.

### Explicit non-claims

This is a durable single-node reference system. It does not claim production authentication, tenant isolation, enterprise RBAC, PostgreSQL, durable distributed queues, production traffic, load-test evidence, production SLOs, or compliance certification.

---

## 2. BLACK

Repository: <https://github.com/o-yutaka/BLACK>

### Problem addressed

AI applications often route models and tools without preserving why a provider was chosen, which evidence supported a result, whether an action was permitted, or whether the same decision can be reproduced later.

### Implemented system

- Mission compiler and shared runtime used by CLI and web API
- candidate arena and policy evaluation
- capability and provider router
- OpenAI-compatible, Ollama, and deterministic provider adapters
- plugin and provider SDKs
- evidence verification and decision ledger
- SQLite source of truth with append-only JSONL mirror
- deterministic Decision DNA and replay verification
- Next.js operations interface and Storybook
- Playwright and axe-core E2E checks
- secret broker and redaction tests
- core-freeze policy enforced in CI

### Reproducible review path

1. `README.md`
2. `ARCHITECTURE.md`
3. `docs/evidence/acceptance-criteria.md`
4. `docs/evidence/ci-verification.md`
5. `docs/contracts/`
6. `packages/core/`
7. `packages/runtime/`
8. `packages/providers/`
9. `packages/storage/`

Primary verification command:

```bash
pnpm run verify
```

### Evidence documented in the repository

- 140+ unit and integration tests
- 53 Playwright E2E tests
- `packages/core` coverage reported as 81.39%
- secret scan with zero findings
- real OpenAI-compatible provider verification recorded against LM Studio

### Explicit non-claims

BLACK is a production-ready MVP and reference platform, not proof of multi-region operation, enterprise customer traffic, audited regulatory compliance, or independently certified security.

---

## 3. BLACK Pokémon Championship Agent

Repository: <https://github.com/o-yutaka/black-pokemon-championship>

### Problem addressed

A stateful agent connected to an external engine must select only legal option indexes, preserve exact engine semantics, stay within runtime budgets, package an exact submission tree, and distinguish crash screening from performance claims.

### Implemented system

- reviewed canonical deck and entrypoint
- source, runtime, and archive layout contracts
- exact required-file allow-list
- deck and ACE-spec validation
- legal selection validator
- deterministic fallback for timeout, exceptions, and invalid selections
- decision overlay with runtime source, warnings, and truth ledger
- reproducible submission builder
- fast parallel regression and crash screen

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
| Engine-exposed option indexes | API and tool allow-list |
| Hidden-state discipline | Evidence and observation boundary |
| Invalid selection rejection | Contract validation |
| Turn and resource planning | Cost, permissions, and workflow state |
| Deterministic fallback | Safe degraded operation |
| Replay and evaluation harness | Regression and policy promotion gates |

### Explicit non-claims

Fast evaluation is crash, speed, and regression screening. It is not presented as official leaderboard evidence or a universal business-agent benchmark.

---

## Account-level checks still required

The following are GitHub account or repository settings and cannot be proven by repository text alone:

1. GitHub Pages enabled with GitHub Actions as the source
2. actual profile pins set to `AI-AI`, `BLACK`, and `black-pokemon-championship`
3. obsolete public repositories archived or made private after unique work is preserved
