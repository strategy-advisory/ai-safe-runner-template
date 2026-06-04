# ai-safe-runner-template

Reusable guardrails for AI-assisted development teams that need to keep external actions, production changes, and paid API usage under human control.

This repository is a lightweight starter kit for teams using AI coding agents such as Codex, Claude Code, or Cursor in real delivery environments.

## What It Helps With

- keeping AI agents away from direct external sends
- separating local execution from approval-required actions
- standardizing dry-run and audit-log workflows
- reducing risk around secrets, production changes, and destructive Git actions

## Who It Is For

- teams using AI agents in client work
- internal platform or ops teams
- solo maintainers who want a safer automation baseline

## Included

- `AGENTS.md`: agent operating rules
- `templates/safe-runner-policy.md`: default execution policy
- `templates/kill-switch-runbook.md`: incident response checklist
- `templates/external-action-queue.md`: approval queue template
- `templates/provider-account-matrix.md`: provider/account inventory template
- `examples/job-request.example.json`: dry-run job request example
- `examples/audit-log.example.jsonl`: audit log example

## Core Model

1. AI agents can do local analysis, coding, test preparation, and dry-run planning.
2. External sends, production changes, and paid bulk actions must become explicit job requests.
3. A human reviews the request, approves it, and executes it through a controlled runner.
4. The result is written to an audit log with references to artifacts and follow-up actions.

## Suggested Repository Layout

```text
.
|-- AGENTS.md
|-- CHANGELOG.md
|-- LICENSE
|-- README.md
|-- examples/
|   |-- audit-log.example.jsonl
|   `-- job-request.example.json
`-- templates/
    |-- external-action-queue.md
    |-- kill-switch-runbook.md
    |-- provider-account-matrix.md
    `-- safe-runner-policy.md
```

## Fast Start

1. Copy this repository.
2. Fill in `templates/provider-account-matrix.md`.
3. Adapt `AGENTS.md` to your environment.
4. Define what counts as an external action in `templates/safe-runner-policy.md`.
5. Run your first dry-run using `examples/job-request.example.json`.

## Design Principles

- local-first work
- explicit human approval for risky actions
- dry-run before live execution
- no secrets in chat or docs
- auditable evidence over informal memory

## Why We Built This

Teams using AI agents for real delivery work often discover the same gap: AI can accelerate coding and analysis, but the risky part is everything that crosses into the outside world.

This template packages a practical baseline for that gap. It helps teams separate local AI work from approval-required actions such as external sends, production changes, and bulk paid execution.

## Roadmap

- add a reference `safe-runner.mjs` implementation
- add sample approval workflows for GitHub, email, and deploy jobs
- add JSON schemas for job requests and audit logs
- add a small validation CLI for dry-run checks
- document integrations with common AI coding environments

## Non-Goals

- bypassing platform protections
- mass account creation or artificial engagement
- direct execution of unsafe production actions by AI

## License

MIT
