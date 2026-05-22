# Grant Reviewer Checklist

Status: reviewer-facing checklist.

Purpose: help a grant reviewer evaluate Causal Memory Layer (CML) quickly without reading the whole repository first.

## 3-minute path

Start here:

1. Read the root `README.md`.
2. Read `docs/GRANT_EVIDENCE.md`.
3. Read `docs/evidence/BENCHMARK_EVIDENCE_SNAPSHOT.md`.
4. Run the local validation commands below.
5. Review one concrete demo:
   - `docs/demo/DOCKER_CAUSAL_MEMORY_WALKTHROUGH.md`
   - `examples/api/causal_memory_demo.jsonl`

## Core claim to evaluate

```text
CML detects actions that appear operationally valid but are causally invalid
because authorization, intent, approval, or responsibility lineage is missing,
ambiguous, or broken.
```

Core invariant:

```text
A system may be functionally correct while being causally invalid.
```

## What to run

Fast validation:

```bash
pip install -e ".[dev]"
pytest
```

Safety benchmark:

```bash
python scripts/run_safety_eval.py
```

Docker demo:

```bash
docker compose up --build
```

Then, in a second terminal, follow:

```text
docs/demo/DOCKER_CAUSAL_MEMORY_WALKTHROUGH.md
```

## Evidence assets

| Evidence | Path | Reviewer question |
| --- | --- | --- |
| Grant package | `docs/GRANT_EVIDENCE.md` | Is the project framed with evidence and non-claims? |
| Benchmark snapshot | `docs/evidence/BENCHMARK_EVIDENCE_SNAPSHOT.md` | Are known failure classes reproducible? |
| Benchmark fixtures | `benchmarks/fixtures/` | Are expected audit findings testable? |
| Benchmark results | `benchmarks/RESULTS.md` | Are outcomes tracked? |
| Docker walkthrough | `docs/demo/DOCKER_CAUSAL_MEMORY_WALKTHROUGH.md` | Can a reviewer see the core idea locally? |
| API contract | `docs/api/HOSTED_AUDIT_API_MVP.md` | Is there a plausible API surface? |
| Audit glossary | `docs/audit/FINDINGS_GLOSSARY.md` | Are findings understandable? |
| LTP bridge | `docs/LTP_CML_BRIDGE.md` | How does CML relate to thread continuity? |
| Fintech framing | `docs/FINTECH_LIMIT_DEMO.md` | Why is this relevant to high-stakes workflows? |

## What CML currently demonstrates

CML currently demonstrates a narrow but important safety primitive:

```text
structured action trace
  -> causal chain reconstruction
  -> deterministic audit rules
  -> valid / invalid lineage finding
```

The current repository includes:

- a Python causal validation and audit engine;
- causal chain reconstruction utilities;
- CLI and API surfaces;
- deterministic benchmark fixtures;
- example logs and walkthroughs;
- documented audit findings;
- explicit scope boundaries and non-claims.

## Failure classes to look for

CML is designed to make these failures inspectable:

- missing parent authorization;
- malformed or ambiguous root authority;
- unmarked causal gaps;
- secret-to-network behavior without valid causal linkage;
- broken responsibility lineage across handoffs;
- plausible output traces disconnected from required evidence.

## What not to infer

CML does not currently claim:

- full AI alignment;
- production runtime enforcement;
- certified compliance;
- replacement of SIEM, EDR, IAM, tracing, or observability platforms;
- prevention of all unsafe actions;
- proof that an AI system is safe.

Safer interpretation:

```text
CML is a causal-validity audit primitive for structured action traces.
```

## Strongest grant-review interpretation

A strong grant-review interpretation is:

```text
CML contributes a testable oversight primitive for agentic AI systems:
it distinguishes operational success from causal legitimacy.
```

This is useful because increasingly capable agents will not only produce text; they will perform actions. For high-stakes settings, reviewers need evidence not only of what happened, but why an action was allowed and whether responsibility was preserved.

## Recommended reviewer verdict frame

A reviewer can score CML on four dimensions:

| Dimension | Question |
| --- | --- |
| Artifact maturity | Can the code and benchmark run locally? |
| Research clarity | Is the failure class precise and important? |
| Evidence quality | Are findings deterministic and reproducible? |
| Scope discipline | Are non-claims explicit and credible? |

## Bottom line

```text
CML is grant-reviewable because it is already an implemented artifact with
reproducible examples, benchmark evidence, and explicit safety boundaries.
```

It should be judged as an early open-source research infrastructure project, not as a finished production compliance platform.
