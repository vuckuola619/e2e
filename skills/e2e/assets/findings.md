# Findings table template

Use one row per distinct observed issue or unresolved material gap. A finding needs evidence or an explicit `UNKNOWN` reason. Do not infer a finding from a missing filename alone, and do not mark a candidate finding as confirmed without a valid procedure and review.

| Finding ID | Title and observed behavior | Severity | Likelihood | Impact | Exposure | Detectability | Evidence IDs | Checklist / task / requirement | Owner | Remediation or risk-acceptance task | Status | Release-blocking | Reviewer disposition |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| FND-EXAMPLE-001 | Describe one observed behavior or state the unresolved question | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | EVD-EXAMPLE-001 or UNKNOWN | CHK-EXAMPLE-001 / TSK-EXAMPLE-001 / REQ-EXAMPLE-001 | UNKNOWN | TSK-REMEDIATION-001 or TSK-RISK-ACCEPT-001 | OPEN | UNKNOWN | PENDING |

## Disposition rules

- `CANDIDATE`: plausible lead that still needs a reproducer, scope, or evidence.
- `CONFIRMED`: procedure ran with valid identity and evidence supports the observed behavior.
- `NEEDS_VALIDATION`: evidence exists but identity, coverage, freshness, or semantics are insufficient.
- `REJECTED`: review found that the claim is unsupported or outside scope; record the reason.
- `ACCEPTED_RISK`: a named owner accepted a nonblocking residual risk with deadline, monitoring, and rollback or kill criterion.
- `FIXED_PENDING_RETEST`: remediation was made but the applicable check has not yet produced fresh evidence.
- `CLOSED`: remediation or acceptance was verified by the required reviewer.

Severity and release blocking are separate. Set priority from impact, likelihood, exposure, detectability, and urgency; a mandatory gate can block release at any severity. A zero-finding result is meaningful only when the procedure, expected inventory, output validity, subject identity, and coverage are complete.
