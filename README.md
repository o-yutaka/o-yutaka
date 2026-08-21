# o-yutaka

## 個人でAIを触り始めた夢物語

最初は、ただAIで何ができるのかを試していただけだった。

モデルを触って、プロンプトを書いて、AI同士をつないで、思いついた仕組みを一つずつ実装した。
そのうち「AIそのものを作る」よりも、**AIをどう判断させ、どう組み合わせ、どう安全に実行させ、どう検証するか**の方に興味が移っていった。

このGitHubは、その夢物語をコードにしていった記録です。

今は、AIモデルの上にある **Decision / Agent / Execution / Verification のレイヤー**を作っています。

> AIを置き換えるのではなく、AIをどう使うかを設計する。

## 今つくっているもの

```text
                         BLACK
                Decision / Trust OS
                           │
          ┌────────────────┼────────────────┐
          │                │                │
        AI-AI           KAIROS          BLACK Pokémon
   Agent Control      Business OS       Planning / Eval
          │                │                │
          └────────────────┼────────────────┘
                           │
                      black-core
                 Python Agent Runtime
                           │
                Competition / Research
                     HROS / Lab
```

これらは別々の思いつきではなく、同じ問いを違う場所で実装したものです。

**「AIをどう制御し、現実の実行につなげるか」**

## Featured Projects

### 1. BLACK — Decision & Trust Operating System

[BLACK](https://github.com/o-yutaka/BLACK)

AIモデルの上位にある意思決定・検証・実行レイヤー。

```text
Mission
  ↓
Context
  ↓
Candidate Arena
  ↓
Evaluation
  ↓
Capability Router
  ↓
Plugin Runtime
  ↓
Evidence
  ↓
Verification
  ↓
Decision Ledger
  ↓
Replay
```

LLM / Provider routing、Plugin、Evidence、Verification、Decision Ledger、Replay、CLI、Web UI、SQLite、CI、E2Eまでを一つの実行系として構築しています。

**このプロジェクトが今の中心です。**

### 2. AI-AI — AI Agent Control Plane

[AI-AI](https://github.com/o-yutaka/AI-AI)

企業向けAI Agentを、自由に動かすのではなく、**契約・権限・証拠・人間承認の中で安全に実行するControl Plane**。

```text
LLM
 ↓
Candidate
 ↓
Contract / Permission / Evidence
 ↓
Ranking
 ↓
Human Approval
 ↓
Tool Execution
 ↓
Audit / Replay
```

FastAPI、Next.js、Docker、SQLite、Idempotency、Privacy Gate、Tool Allow-list、Browser proofまで実装しています。

**Live proof:** https://raw.githack.com/o-yutaka/AI-AI/main/docs/live-demo.html

### 3. KAIROS — Autonomous Business OS

[KAIROS](https://github.com/o-yutaka/KAIROS)

AIの判断を、実際の仕事・案件・収益へつなげるためのBusiness OS構想。

```text
WORLD
 ↓
RECON / INTELLIGENCE
 ↓
SIGNAL
 ↓
OPPORTUNITY
 ↓
BLACK DECISION
 ↓
EXECUTION
 ↓
REVENUE
 ↓
FEEDBACK
 ↓
WORLD
```

Multi-LLM、Web intelligence、Opportunity generation、GitHub Issue → AI → PR → Deploy、Autonomous loopなどを組み合わせています。

### 4. BLACK Pokémon Championship — Stateful Agent Reliability

[BLACK Pokémon Championship](https://github.com/o-yutaka/black-pokemon-championship)

ゲームAIとして作ったものですが、実際に検証したかったのは **外部エンジンに接続されたAgentをどう安全に動かすか** です。

```text
External Observation
 ↓
Policy
 ↓
Legal Action Validation
 ↓
Execute
 ↓
Fallback on Error
 ↓
Audit / Artifact
```

Action contract、invalid output rejection、timeout、deterministic fallback、artifact verification、multi-process simulation、honest evaluation boundaryを実装しています。

### 5. black-core / HROS — Agent Runtime & Research

[black-core](https://github.com/o-yutaka/black-core)  
[HROS](https://github.com/o-yutaka/HORS)

Python-first Agent Runtime、Event Bus、Task / Goal Intelligence、Executor、Memory、Autonomous Loop。

その上で、HROSでは `bible / adr / rfc / prompts / core / kernel / capability / service / infrastructure / workspace / experiments / logs` まで含めて、**AIシステムそのものを研究・運用するための土台**を作っています。

## いま興味がある領域

```text
AI Agent Runtime
LLM / Provider Routing
Prompt Engineering
AI Orchestration
Tool Calling / MCP
Human-in-the-loop
Decision Systems
Evaluation / Simulation
Failure Recovery
Evidence / Audit / Replay
Business Automation
AI + External APIs
```

## 考えていること

AIは、モデル単体では完成しない。

どのモデルを使うか。
どこまでAIに任せるか。
何を証拠とするか。
どの操作を許可するか。
失敗したらどう戻すか。
同じ判断をもう一度再現できるか。

そういう**モデルの外側**を作ることに興味があります。

> Models change.
> Providers change.
> Prompts change.
> Good systems should remain explainable.

## このGitHubについて

このアカウントには、完成した製品だけではなく、途中の実験や失敗も含まれています。

最初の「AIで何かできるかもしれない」という夢物語から、

```text
AIを触る
 ↓
AIを組み合わせる
 ↓
Agentにする
 ↓
Decisionを持たせる
 ↓
Executionを制御する
 ↓
Verificationする
 ↓
Evidenceを残す
 ↓
Replayする
 ↓
Business / Competition / Researchへ広げる
```

という形に変わってきました。

**まだ途中です。**

このGitHubは、その途中をそのまま公開しています。
