# External Action Queue

| Job ID | Requested By | Target | Mode | Summary | Approval | Status | Artifact Ref |
| --- | --- | --- | --- | --- | --- | --- | --- |
| JOB-001 | example-owner | example-system | dry-run | validate outbound workflow | not required | complete | docs/example-artifact |
| JOB-002 | example-owner | example-system | live | send approved message batch | pending | waiting | docs/example-artifact |

## Status Meanings

- `waiting`: ready for approval or scheduling
- `approved`: approved for live execution
- `running`: currently executing
- `complete`: finished successfully
- `blocked`: cannot proceed safely
- `cancelled`: intentionally stopped
