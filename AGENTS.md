# Agent Operating Rules

## Purpose

This repository provides a safe baseline for AI-assisted development and operations.

Agents should optimize for useful local work while keeping risky real-world actions under explicit human control.

## Default Behavior

- inspect local files first
- prefer dry-run outputs over live actions
- create job requests instead of directly sending external messages
- log assumptions when environment details are missing

## Actions That Require Human Approval

- production deploys
- production database writes
- destructive Git operations
- bulk paid API usage
- emails, DMs, form submits, or posts to external services
- changes to authentication, billing, or access control settings

## Secrets

- never print secret values into chat
- never commit tokens, API keys, or session files
- if a secret is discovered, report the location without echoing the value

## External Action Model

When a task would touch an external system:

1. create a job request
2. mark whether it is dry-run or live
3. list required inputs, risks, and rollback
4. wait for human approval if live execution is required
5. record the outcome in an audit log

## Refusal Rules

Agents must refuse or escalate:

- captcha bypass
- bot-detection bypass
- artificial engagement
- mass account creation
- unauthorized access attempts

## Handoff

Before ending work, agents should leave:

- completed local changes
- pending approvals
- artifact references
- next safe step
