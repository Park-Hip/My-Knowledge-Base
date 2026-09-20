---
type: reference
status: active
created: 2026-09-20
last-reviewed: 2026-09-20
topics: [github, templates, workflow, vibe-coding]
source:
  - https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository
  - https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms
  - https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository
  - https://docs.github.com/en/code-security/concepts/vulnerability-reporting-and-management/coordinated-disclosure
verified-in: []
---

# GitHub Issue and PR Templates

Use these templates for meaningful-impact work. Keep trivial fixes and small documentation changes
out of the issue tracker unless they need durable tracking.

## Baseline

| Item | Decision |
| --- | --- |
| Issue format | YAML Issue Forms in `.github/ISSUE_TEMPLATE/` |
| PR format | Markdown in `.github/pull_request_template.md` |
| Issue types | Bug report, change proposal, operational follow-up |
| Blank issues | Disabled |
| Labels | Start with `bug`, `proposal`, and `follow-up`; add workflow labels only when they help. |
| Security | Do not report vulnerabilities in public issues; add `SECURITY.md` or private reporting when relevant. |

## Issue-template configuration

```yaml
# .github/ISSUE_TEMPLATE/config.yml
blank_issues_enabled: false
```

## Bug report

```yaml
# .github/ISSUE_TEMPLATE/bug-report.yml
name: Bug report
description: Report a defect in behavior, documentation, or operations.
labels: [bug]
body:
  - type: textarea
    id: actual
    attributes:
      label: Actual behavior
      description: What happened?
    validations:
      required: true
  - type: textarea
    id: expected
    attributes:
      label: Expected behavior
      description: What should have happened, and why?
    validations:
      required: true
  - type: textarea
    id: repro
    attributes:
      label: Steps to reproduce
      description: Give minimal numbered steps from a clean environment.
    validations:
      required: true
  - type: input
    id: environment
    attributes:
      label: Version and environment
      description: Include the app/version, OS, browser, runtime, or deployment details. Write N/A only when not applicable.
    validations:
      required: true
  - type: input
    id: reproduction-link
    attributes:
      label: Minimal reproduction link
      description: Optional public repository, sandbox, or recording.
  - type: textarea
    id: evidence
    attributes:
      label: Evidence
      description: Optional logs, screenshots, traces, or related issues. Redact credentials, tokens, and personal data.
```

## Change proposal

```yaml
# .github/ISSUE_TEMPLATE/change-proposal.yml
name: Change proposal
description: Propose a meaningful, contract-affecting, or uncertain change before implementation.
labels: [proposal]
body:
  - type: dropdown
    id: tier
    attributes:
      label: Tier
      description: Planned changes need a proposal; research-led changes also need evidence.
      options:
        - Planned - behavior, contract, operational, or multi-file change
        - Research-led - uncertain, irreversible, or architectural choice
    validations:
      required: true
  - type: textarea
    id: outcome
    attributes:
      label: Goal and expected outcome
      description: State the observable end state, not implementation steps.
    validations:
      required: true
  - type: textarea
    id: scope
    attributes:
      label: Change surface and exclusions
      description: What changes, and what is explicitly out of scope?
    validations:
      required: true
  - type: textarea
    id: compatibility
    attributes:
      label: Compatibility boundary
      description: Name affected APIs, schemas, contracts, data, operations, or documented claims. Write "No boundary change" if none.
    validations:
      required: true
  - type: textarea
    id: verification
    attributes:
      label: Verification plan
      description: List focused checks, full gates, and a manual check with its expected result.
    validations:
      required: true
  - type: textarea
    id: rollback
    attributes:
      label: Rollback
      description: How will the change be undone if it fails after merge?
    validations:
      required: true
  - type: textarea
    id: evidence
    attributes:
      label: Research evidence
      description: For research-led changes, link measurements, spikes, or primary sources.
```

## Operational follow-up

```yaml
# .github/ISSUE_TEMPLATE/operational-followup.yml
name: Operational follow-up
description: Track a risk, known issue, or follow-up discovered during other work.
labels: [follow-up]
body:
  - type: textarea
    id: finding
    attributes:
      label: Finding
      description: What was observed, where, and why does it matter? Link the originating issue, PR, evaluation, or incident.
    validations:
      required: true
  - type: dropdown
    id: priority
    attributes:
      label: Priority
      options:
        - High - blocks release, correctness, or safety
        - Medium - should be addressed soon
        - Low - fix when convenient
    validations:
      required: true
  - type: textarea
    id: done-when
    attributes:
      label: Done when
      description: State the observable condition that closes this issue.
    validations:
      required: true
```

## Pull-request template

```markdown
<!-- .github/pull_request_template.md -->

## Summary

<!-- What changed and why. Use `Closes #<issue>` for tracked work, or write `No issue — minor fix`. -->

## Verification

<!-- List exact commands and their results. -->

- `<command>` — <result>

## Manual check

<!-- State the step and expected result. -->

- [ ] <step> → <expected result>

## Risks and follow-ups

<!-- Behavior, compatibility, data, deployment, or operational risks. Link follow-up issues rather than silently expanding scope. -->

- None.

## Documentation and ADR impact

<!-- Which documented claims become true or false? Was an ADR added, changed, or unnecessary? -->

- None.

## Known issues

- None.
```

## Maintenance

Review templates when they create repeated confusion, fields are consistently ignored, or the
project workflow changes. Keep required fields limited to evidence genuinely needed to act.

## Related

- [[Vibe Coding]]
- [[Documentation System for Vibe Coding]]

## Sources

| Source | Use |
| --- | --- |
| [GitHub: Issue Form syntax](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms) | YAML form fields and validation. |
| [GitHub: template configuration](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository) | Template chooser and blank-issue setting. |
| [GitHub: PR templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository) | PR-template locations and Markdown format. |
| [GitHub: coordinated disclosure](https://docs.github.com/en/code-security/concepts/vulnerability-reporting-and-management/coordinated-disclosure) | Private vulnerability reporting. |
| Mature OSS template research: Kubernetes, Terraform, AWS CLI, React, Next.js, Go, Turborepo, and Rust, 2026-09-20 | Field and triage patterns. |
