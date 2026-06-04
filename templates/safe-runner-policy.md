# Safe Runner Policy

## Goal

Allow AI agents to prepare work safely while preventing direct uncontrolled execution of risky actions.

## Allowed Without Additional Approval

- local file reads and edits
- static analysis
- test preparation
- dry-run planning
- artifact generation without external side effects

## Approval-Required Actions

- outbound email, DM, or social posting
- form submission to third-party services
- production deploys
- production data mutation
- paid API bulk execution
- destructive repository or infrastructure actions

## Required Fields For Live Jobs

- owner
- requested action
- target system
- business reason
- dry-run result
- risk summary
- rollback plan
- approval record

## Logging Requirements

- timestamp
- actor
- requested mode: `dry-run` or `live`
- target
- result
- artifact references
- follow-up actions

## Guardrails

- no secrets in logs
- no silent retries for unsafe external actions
- no live execution if rollback is undefined
- no production action when the owner is unavailable
