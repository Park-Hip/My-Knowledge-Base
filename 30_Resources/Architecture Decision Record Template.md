---
type: reference
status: active
created: 2026-09-20
last-reviewed: 2026-09-20
topics: [adr, decisions, documentation, vibe-coding]
source:
  - https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/adr-process.html
  - https://learn.microsoft.com/en-us/azure/well-architected/architect-role/architecture-decision-record
  - https://cloud.google.com/architecture/architecture-decision-records
  - https://martinfowler.com/bliki/ArchitectureDecisionRecord.html
verified-in: []
---

# Architecture Decision Record Template

Use this template for one durable, consequential project decision. Store the resulting ADR with the
project it governs, usually under `docs/decisions/`.

## Template

```markdown
# ADR-<number>: <clear decision title>

> **Status:** Proposed | Accepted | Superseded
> **Date:** YYYY-MM-DD

## Context
What decision is needed? State the current situation, constraints, and why code alone cannot answer
this question.

## Options considered
- **Option A:** benefit and trade-off.
- **Option B:** benefit and trade-off.

## Decision
We will …

## Consequences
What becomes easier, harder, more expensive, risky, or intentionally excluded?

## Evidence
Links to research, measurements, issues, pull requests, or official documentation.

## Related
Superseded ADR, successor ADR, or related architecture/reference documents.
```

## Rules

| Rule | Practice |
| --- | --- |
| Scope | One consequential decision per ADR. |
| Focus | Record why, trade-offs, and evidence; do not write an implementation plan. |
| Approval | Draft from Lavish research; approve before implementation. |
| History | Preserve accepted ADRs. Create a successor when the decision changes. |

## Sources

- [AWS ADR process](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/adr-process.html)
- [Microsoft ADR guidance](https://learn.microsoft.com/en-us/azure/well-architected/architect-role/architecture-decision-record)
- [Google Cloud ADR guidance](https://cloud.google.com/architecture/architecture-decision-records)
- [Martin Fowler: ADR](https://martinfowler.com/bliki/ArchitectureDecisionRecord.html)
