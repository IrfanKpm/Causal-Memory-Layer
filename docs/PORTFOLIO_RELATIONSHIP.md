# Portfolio Relationship

Status: reviewer-facing ecosystem note.

This document explains how CML fits into the broader trustworthy-agent evidence architecture.

Central map:

```text
https://github.com/safal207/L-THREAD-Liminal-Thread-Secure-Protocol-LTP-/blob/main/docs/ECOSYSTEM_SPIDER_MAP.md
```

## Role of this repository

CML is the causal permission and responsibility lineage layer.

It asks:

```text
Why was this action allowed?
```

and checks whether the causal parent, approval, intent, or responsibility chain is intact.

## Ecosystem position

```text
PythiaLabs — pre-execution evidence gates for high-risk agentic actions
LTP — path-level trace/replay/admissibility protocol
CML — causal permission and responsibility lineage
DMP — decision memory and irreversibility governance
LRI — living identity and relational invariants
```

## How CML connects to the other layers

| Layer | Relationship |
|---|---|
| PythiaLabs | CML provides causal permission signals that can help an action gate allow, block, or escalate a proposed action. |
| LTP | LTP preserves the path-level trace where CML causal validity can be inspected over time. |
| DMP | DMP preserves decision memory when a causally permitted action later creates durable or irreversible consequences. |
| LRI | LRI adds human identity and revisability boundaries when causal permission is not enough to protect the person. |

## Reviewer interpretation

CML should not be read as an ordinary logging tool.

Logs show what happened. CML checks why it was allowed.

## Non-claims

CML does not claim:

- full AI alignment;
- production security certification;
- regulatory compliance certification;
- replacement of logs, tracing, policy engines, or human review;
- universal prevention of unsafe actions.

The narrower claim is:

```text
CML is an open-source causal audit layer for checking permission and responsibility lineage in structured action traces.
```
