---
type: playbook
status: active
created: 2026-09-20
last-reviewed: 2026-09-20
topics: [vibe-coding, workflow]
source: []
verified-in: []
---
# Vibe Coding

## Workflow

| Stage | Action | Approval / outcome |
| --- | --- | --- |
| Define | In Ocra, use `main` to define the intended feature or bug fix. | Clear scope. |
| Track | Create a GitHub issue only for meaningful-impact work. Skip it for trivial fixes and small documentation changes; use the applicable issue or PR template when needed. | Issue only when the work warrants one. |
| Isolate | Create a new Ocra worktree for implementation. | Isolated workspace. |
| Scout | Before coding, use Lavish to research the relevant codebase. Its artifact guides the coding agent; no separate execution spec is needed. Follow [[Documentation System for Vibe Coding]] when research yields durable knowledge. | Personally approve the artifact before the agent writes code. |
| Review | After coding, run `no-mistakes` to review the change. | Resolve outstanding problems. |
| Merge | Read and manually approve every pull request. | Never use automatic merging. |

## Model selection

| Task profile | Preferred model | Reasoning effort | Use when |
| --- | --- | --- | --- |
| Complex thinking and decisions | Codex GPT-5.6 Terra | High or xhigh | Complex planning, reasoning, brainstorming, discussion, bug fixing, important decisions, and in-app code review. |
| Research and scouting | Agnes 2.5 | High | Simple research, codebase scouting, web search, and subagent work. |
| Known, low-risk bug fix | Codex Luna | High | The root cause is known, the change is simple, and the cost or risk of being wrong is low. |
| Planned implementation | DeepSeek-V4-Pro-0813 `[modelscope]` | As needed | Implementing code from a clear, approved implementation plan. |

## Documentation

Follow [[Documentation System for Vibe Coding]] for documentation, ADR, and Lavish-artifact rules.

## Related

| Note | Purpose |
| --- | --- |
| [[Documentation System for Vibe Coding]] | Broader documentation approach. |
| [[GitHub Issue and PR Templates]] | Applicable GitHub templates. |

## Source

Personal workflow interview, 2026-09-20.
