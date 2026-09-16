# Discovery plan template

Use this plan when a product decision depends on research or validation. It
describes proposed work until a host or researcher actually performs it. Link it
to a brief or product plan and create a new revision when the question changes.

```yaml
artifact_id: UNKNOWN
document_status: DRAFT
current_phase: DISCOVERY
phase_span:
  - IDEA
  - DISCOVERY
owner: UNKNOWN
revision: UNKNOWN
supersedes: []
upstream_artifacts:
  - UNKNOWN
downstream_artifacts: []
subject:
  name: UNKNOWN
  repository_or_artifact: UNKNOWN
  identity_reason: "No repository, participant record, or source identity was supplied, or it is not yet established."
decision_to_inform: UNKNOWN
research_status: NOT_RUN
decision_owner: UNKNOWN
```

## Decision and questions

- Decision this work should inform: `UNKNOWN`
- Primary research question: `UNKNOWN`
- Secondary questions: `UNKNOWN`
- Possible dispositions: `continue`, `reframe`, `pause`, `stop`
- Decision criteria or thresholds: `UNKNOWN`

## Hypotheses and confidence

| Hypothesis | Current confidence basis | What would support it | What would weaken it |
| --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

Confidence is a planning statement. It is not a result, demand estimate, or
customer decision.

## Method and boundaries

- Selected method or experiment: `UNKNOWN`
- Why this method fits the question: `UNKNOWN`
- Participants, users, or data sources: `UNKNOWN`
- Recruitment or source-selection rationale: `UNKNOWN`
- Proposed sample or stopping rule: `UNKNOWN`
- Authorization and accountable owner: `UNKNOWN`
- Privacy, consent, retention, and sensitive-data boundary: `UNKNOWN`
- Known limitations, bias, and exclusions: `UNKNOWN`
- Tools, environments, or providers needed: `UNKNOWN`

Proposed recruitment and a sample plan do not establish that anyone
participated. Use `UNKNOWN` rather than inventing people, counts, dates, quotes,
or source coverage.

## Evidence targets

| Expected observation or artifact | Provenance to capture | Evidence location / ID | Status |
| --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `NOT_RUN` |

For any executed study, preserve the procedure, source or participant boundary,
observation time, raw material where authorized, redaction, and limitations. If
the work did not run, leave findings empty and keep the status `NOT_RUN`.

## Findings and interpretation

### Observed findings

| Observation | Source / evidence ID | Scope and limitations |
| --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

### Interpretation and proposals

- Interpretation supported by the observations: `UNKNOWN`
- Proposed product or research implication: `UNKNOWN`
- Contradictory or negative evidence: `UNKNOWN`
- Unresolved unknown: `UNKNOWN`

Keep observed findings separate from interpretation. A planned interview,
survey, prototype test, or experiment cannot populate this section as if it ran.

## Decision and handoff

- Decision owner: `UNKNOWN`
- Decision record or date: `UNKNOWN`
- Actual disposition: `UNKNOWN`
- Handoff to product brief or product plan: `UNKNOWN`
- New research question or phase to revisit: `UNKNOWN`
- Superseded discovery artifact(s): `UNKNOWN`
- Next evidence or re-entry trigger: `UNKNOWN`

Discovery decisions are owner decisions about learning. They do not produce a
`READY`, `CONDITIONALLY READY`, `NOT READY`, or `UNDETERMINED` release verdict,
and they never grant authorization. If a repository, participant record, or
source is not available, retain `UNKNOWN` and its reason rather than blocking a
context-only plan.
