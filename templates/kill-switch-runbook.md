# Kill Switch Runbook

## Use This When

- an AI agent starts unsafe repeated actions
- a credential leak is suspected
- a queue targets the wrong destination
- production state changed unexpectedly

## Immediate Actions

1. stop the active runner or workflow
2. disable outbound credentials if needed
3. capture logs and artifact references
4. block further live jobs until review is complete

## Triage Questions

- what action was attempted
- which target system was involved
- was the run dry-run or live
- what credentials were accessible
- what customer or production impact exists

## Recovery

1. rotate affected secrets
2. restore safe configuration
3. confirm pending jobs are paused
4. document root cause and prevention

## Exit Criteria

- unsafe path disabled
- impact understood
- credentials rotated where necessary
- owner approved resumption
