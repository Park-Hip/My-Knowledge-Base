---
type: playbook
status: active
created: 2026-09-20
last-reviewed: 2026-09-20
topics: [documentation, vibe-coding]
source:
  - https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/adr-process.html
  - https://learn.microsoft.com/en-us/azure/well-architected/architect-role/architecture-decision-record
  - https://cloud.google.com/architecture/architecture-decision-records
  - https://martinfowler.com/bliki/ArchitectureDecisionRecord.html
verified-in: []
---

# Documentation System for Vibe Coding

## Start small

| Item | Role | Rule |
| --- | --- | --- |
| `README` | Public first impression for employers, peers, and visitors | Explain what the project is, why it matters, and its core work. Design its detailed structure when writing it. |
| `AGENTS.md` | Context and constraints for coding agents | Start from a generic baseline; add durable project-specific instructions during planning and implementation. |
| Code and tests | Current implementation detail | Keep local behavior, routine choices, and ordinary fixes here. |
| Other documentation | Future-you's project memory | Add it only when its trigger occurs. Do not scaffold every type at project creation. |

## Add documentation on demand

| Type | Create it when | It owns |
| --- | --- | --- |
| How-to | A repeatable task has ordered steps, external setup, or meaningful risk | Running, deploying, recovering, migrating, or releasing. |
| Reference | A fact is reused, must stay consistent, or is costly to rediscover | Configuration, schemas, external services, and behavior rules. |
| Architecture | Boundaries, components, or constraints are non-obvious | System shape and why its boundaries exist. |
| ADR | A decision is cross-cutting, hard to reverse, or consequential | Durable rationale that code cannot recover. |
| Conventions | Documentation rules recur and must stay consistent | Documentation roles, writing, naming, formatting, and evidence rules. |

## ADR and Lavish rules

| Situation | Action |
| --- | --- |
| Lavish research finds a durable decision | The coding agent drafts an ADR; approve it before implementation. |
| Decision affects security, data, API contracts, operations, dependencies, or material cost | Create an ADR. |
| Local framework choice, routine refactor, ordinary bug fix, or temporary detail | Keep the rationale in code, tests, or the pull request; do not create an ADR. |
| ADR content | Keep it short: context, options, decision, consequences, and evidence. |
| Decision changes | Create a successor ADR; preserve the old one as superseded. |
| Lavish artifact only plans implementation | Discard it. Extract durable decisions into ADRs and reusable, source-backed knowledge into Obsidian. |

## Documentation conventions

| Rule | Practice |
| --- | --- |
| Lead with the answer | Start with the conclusion, then supporting detail. |
| Use ISO dates | Write dates as `YYYY-MM-DD`. |
| Give facts one home | Link to the document that owns a fact; do not duplicate it. |
| Preserve evidence | Label claims verified, observed, or uncertain; retain their source. |
| State the role | Each document type names what it owns and its intended reader. |
| Maintain history | Rewrite stale guidance against current truth; supersede decisions rather than rewriting them. |

## Maintenance

When a meaningful change makes a document false or incomplete, update its owning document in the
same pull request. Retire or supersede obsolete guidance rather than leaving it stale.

## Related

- [[Vibe Coding]]
- [[Generic AGENTS.md Baseline]]
- [[Architecture Decision Record Template]]

## Sources

| Source | Use |
| --- | --- |
| Personal workflow interview, 2026-09-20 | Personal workflow rules. |
| [AWS ADR process](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/adr-process.html) | ADR process. |
| [Microsoft ADR guidance](https://learn.microsoft.com/en-us/azure/well-architected/architect-role/architecture-decision-record) | ADR guidance. |
| [Google Cloud ADR guidance](https://cloud.google.com/architecture/architecture-decision-records) | ADR guidance. |
| [Martin Fowler: ADR](https://martinfowler.com/bliki/ArchitectureDecisionRecord.html) | ADR background and format. |
