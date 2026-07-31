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

Interactive public proof: <https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html>

Browser proof manifest: <https://github.com/o-yutaka/AI-AI/blob/main/docs/assets/proof/visual-proof-manifest.json>

Deployment evidence: <https://github.com/o-yutaka/AI-AI/blob/main/docs/live-status.json>

### Problem addressed

A business agent should not call any tool it can describe. It should execute only actions currently allowed by the external system, require permissions and evidence, prevent detected sensitive values from crossing unsafe boundaries, pause high-impact operations for human approval, prevent duplicate side effects, and preserve a reproducible decision trace.

### Implemented system

#### Runtime and state

- FastAPI and Pydantic API boundary
- versioned action contract
- permission and evidence checks
- sensitive action-payload rejection
- exact tool and operation capability gate
- deterministic ranking and rejection reasons
- canonical SHA-256 observation and request fingerprints independent of run ID
- named approval and rejection flow
- explicit execution-attempt count
- stable idempotency replay and conflicting-request detection
- structured provider and executor failures
- SQLite WAL, busy timeout, unique idempotency key, and restart-safe traces
- Next.js operations dashboard

#### Provider and tool boundary

- OpenAI-compatible `/chat/completions` candidate planner
- goal and observation redaction before provider transmission
- typed validation of provider-generated candidates
- rejection of undeclared provider tool operations
- provider response limit enforced while streaming
- operator-configured HTTP tool registry
- exact fixed host, method, relative path template, and operation
- disabled redirects and request timeouts
- HTTP response limit enforced while streaming
- sensitive HTTP headers restricted to environment-variable references
- nested sensitive response-field redaction

#### Privacy boundary

- default sensitive-key detection for authorization, cookies, passwords, secrets, tokens, API keys, email, phone, and address variants
- configurable domain-specific sensitive keys
- nested mapping/list redaction
- free-text bearer, credential-assignment, email, and phone redaction
- redaction before provider transmission, persistence, API return, approval recording, audit events, and error recording
- detected sensitive action payloads blocked rather than rewritten and executed

#### Reproducible delivery

- committed Python development lock
- committed Python runtime lock
- committed npm lockfile
- Python 3.11 and 3.12 CI
- Ruff and 64 tests
- Next.js static export
- backend and frontend Docker builds
- non-root containers
- read-only filesystems and `no-new-privileges`
- API and web health checks
- Docker Compose real-start smoke
- Chromium interaction verification
- committed desktop, mobile, blocked, approval, idempotency, and GIF proof
- MIT license, security policy, changelog, ADRs, and dependency monitoring

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

Committed visual evidence:

- 1440 px waiting-approval screen
- 1440 px approved screen
- 1440 px blocked-candidates screen
- 1440 px idempotency-replay screen
- 390 px mobile waiting-approval screen
- compact proof GIF

### Reproducible review path

1. public interactive proof
2. `README.md`
3. `docs/assets/proof/visual-proof-manifest.json`
4. `control_plane/runtime.py`
5. `control_plane/security.py`
6. `control_plane/providers.py`
7. `control_plane/tools.py`
8. `control_plane/store.py`
9. `tests/test_runtime.py`
10. `tests/test_security.py`
11. `tests/test_hardening.py`
12. `tests/test_trace_execution_proof.py`
13. `tests/test_provider_privacy.py`
14. `tests/test_tools.py`
15. `scripts/capture_visual_proof.py`
16. `docs/adr/0003-data-boundary-and-streaming-limits.md`
17. `docs/evidence.md`
18. `docs/portfolio-audit-2026-08-01.md`

Primary commands:

```bash
docker compose up --build

python -m venv .venv
source .venv/bin/activate
pip install -r requirements.lock.txt
pip install --no-deps -e .
ruff check .
pytest -q

cd web
npm ci
npm run build
```

### Public-proof boundary

- The browser page executes the contract, policy, approval, blocking, idempotency, fingerprint, and trace lifecycle locally.
- Browser provider generation and tool execution are explicitly simulated.
- Content Security Policy disables browser network connections.
- Real OpenAI-compatible provider and HTTP adapter requests are backend implementations tested through controlled HTTP transports.
- The clean GitHub Pages URL is prepared but must not be described as live until repository-level Pages is enabled and HTTP verification succeeds.

### Explicit non-claims

This is a durable single-node reference system. It does not claim production authentication, tenant isolation, enterprise RBAC, distributed queues, multi-region replication, production customer traffic, load-test evidence, production SLOs, complete DLP, compliance certification, or audited security.

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
3. obsolete public repositories archived or made private only after unique work is preserved
