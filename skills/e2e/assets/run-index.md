# Run index template

Create one index per assessment or run directory. Keep historical attempts immutable and link a retry instead of overwriting the previous record.

```yaml
run_id: RUN-EXAMPLE-001
assessment_mode: PLAN_ONLY
document_status: DRAFT
subject:
  name: UNKNOWN
  scope: UNKNOWN
  environment: local
  source_revision: UNKNOWN
  dirty_state: UNKNOWN
  artifact_identity: UNKNOWN
authorization:
  requested_action: "Plan and record an assessment"
  authorized_scope: UNKNOWN
  external_mutation_allowed: false
  owner_decisions_needed:
    - UNKNOWN
people:
  accountable_owner: UNKNOWN
  verifier: UNKNOWN
  reviewer: UNKNOWN
  required_signers: []
policy:
  version: UNKNOWN
  applicability_profile: UNKNOWN
  selected_modules: []
  rejected_or_held_modules: []
tasks:
  index: UNKNOWN
  status: TODO
  dependency_graph: UNKNOWN
  cycles: UNKNOWN
  critical_path: UNKNOWN
evidence:
  manifest: UNKNOWN
  raw_location: UNKNOWN
  redacted_view: UNKNOWN
  evidence_ids: []
  freshness_rule: UNKNOWN
findings:
  table: UNKNOWN
  open_count: UNKNOWN
decision:
  value: UNDETERMINED
  proof_set: []
  exceptions: []
  acceptance: UNKNOWN
  decision_time: UNKNOWN
  next_executable_path: UNKNOWN
limitations:
  - "This template contains no runtime observation or approval."
attempts:
  - attempt_id: ATTEMPT-EXAMPLE-001
    execution_status: NOT_STARTED
    check_status: NOT_RUN
    supersedes: []
    reason: "Template only"
```

The index should link scope, assumptions, applicability, requirements, gates, checklist, WBS, test or evaluation plan, findings, runbook and rollback, UAT and sign-off, decision, diagrams, and evidence manifest. Do not fill in timestamps, hashes, commands, approvals, or results unless they were actually produced.
