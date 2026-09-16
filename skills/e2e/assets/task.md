# Task template

Copy this template for an atomic work item. Replace placeholders with facts from the assessment. Keep task status independent from check status: authoring a task does not run its check. `UNKNOWN` is preferred to an invented command, owner, identity, timestamp, or hash.

```yaml
id: TSK-EXAMPLE-001
parent: ROOT
goal: "One observable outcome for one bounded task"
priority: P1
role: accountable role
owner: UNKNOWN
verifier: UNKNOWN
reviewer: UNKNOWN
applicability_profile:
  - software
requirements:
  - REQ-EXAMPLE-001
checklist_items:
  - CHK-EXAMPLE-001
gate_ids:
  - GATE-EXAMPLE-001
dependencies: []
environment: local
preconditions:
  - "[ ] Authorized subject and scope are recorded"
  - "[ ] Source or artifact identity is captured"
  - "[ ] Required tool capability and data boundary are available"
steps:
  - "1. Confirm the recorded subject identity and authorized scope."
  - "2. Perform the single bounded action described by goal."
  - "3. Compare the observed result with the acceptance criteria."
  - "4. Capture the evidence record before producing a summary."
acceptance_criteria:
  - "[ ] The stated outcome is observed for the selected subject."
  - "[ ] The expected data or state effect is recorded with its limitation."
  - "[ ] The evidence ID is linked to the checklist, requirement, gate, and task."
verification:
  command: UNKNOWN
  cwd: UNKNOWN
  inputs:
    - "subject_identity: UNKNOWN"
    - "configuration_identity: UNKNOWN"
  expected_output: "UNKNOWN until discovery establishes the exact procedure and expected result"
evidence:
  - "EVD-EXAMPLE-001; path=UNKNOWN; media_type=UNKNOWN; sha256=UNKNOWN; observed_at=UNKNOWN"
cleanup_or_rollback: "N/A only when the task made no change; otherwise record an exact reversible cleanup or rollback"
risks:
  - "The subject, procedure, or expected output may be incomplete"
blockers:
  - "UNKNOWN until required identity, access, and owner decisions are checked"
release_blocking: null
release_blocking_reason: "UNKNOWN until applicability and gate policy are established"
deferral:
  reason: N/A
  owner: UNKNOWN
  expires_at: N/A
  reentry_trigger: N/A
estimate_and_parallel_lane: "Estimate UNKNOWN; lane UNKNOWN until dependencies are resolved"
task_status: TODO
check_status: NOT_RUN
```

Before marking a task `DONE`, check all applicable acceptance boxes, attach evidence IDs, handle cleanup or rollback, and record verifier and reviewer completion. Use `IN_REVIEW` when execution is complete but review is pending. Use `DEFERRED` only with a reason, owner, expiry, and re-entry trigger. Use `N/A` only with applicability evidence. A completed task may still have `check_status: NOT_RUN` when it only authored a plan.
