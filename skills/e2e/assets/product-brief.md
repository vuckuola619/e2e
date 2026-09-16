# Product brief template

Use this short brief when an idea has material product intent or uncertainty.
The direct path in [lifecycle.md](../references/lifecycle.md) is sufficient for
a small, clear change. Fill placeholders only with information that is actually
known; retain `UNKNOWN` when the source or decision is missing.

```yaml
artifact_id: UNKNOWN
document_status: DRAFT
current_phase: IDEA
phase_span:
  - IDEA
owner: UNKNOWN
revision: UNKNOWN
supersedes: []
upstream_artifacts: []
downstream_artifacts: []
subject:
  name: UNKNOWN
  repository_or_artifact: UNKNOWN
  identity_reason: "No repository or artifact was supplied, or identity is not yet established."
```

## Idea, problem, or opportunity

- Statement: `UNKNOWN`
- Who is affected or intended to benefit: `UNKNOWN` (state when this is an
  assumption rather than an observed population)
- Job, need, or outcome to understand: `UNKNOWN`
- Why now: `UNKNOWN`
- Desired product or service outcome: `UNKNOWN`

## Signals and evidence

| Signal or fact | Source / evidence ID | Observed when | Scope and limitations |
| --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

If there is no observed signal yet, say so. A request, stakeholder assertion,
interview plan, survey draft, or market hypothesis is not observed validation.

## Assumptions

| Assumption | Why it is being used | How it could be checked | Owner |
| --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

## Hypotheses

| Hypothesis | Confidence basis | Test or disconfirming signal | Decision threshold |
| --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

Hypotheses are propositions to test. Do not present confidence as customer
evidence or a validation result.

## Options and boundaries

- Alternatives considered: `UNKNOWN`
- Constraints (technical, legal, privacy, accessibility, operational, or
  resource): `UNKNOWN`
- Non-goals for this slice: `UNKNOWN`
- Material risks and affected domains: `UNKNOWN`
- Earliest useful success signal: `UNKNOWN`
- Failure or stop signal: `UNKNOWN`

## Open questions and next decision

| Question | Why it matters | Proposed next step | Decision owner | Status |
| --- | --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

- Proposed next step or disposition: `validate`, `pivot`/`reframe`, `build`,
  `pause`, `stop`, or `UNKNOWN`
- Actual owner disposition: `continue`, `reframe`/`pivot`, `pause`, `stop`, or
  `UNKNOWN`
- Handoff to product plan or discovery artifact: `UNKNOWN`
- Revisit phase if the next signal changes the premise: `UNKNOWN`

## Continuity

- Upstream artifact IDs or paths: `UNKNOWN`
- Downstream artifact IDs or paths: `UNKNOWN`
- Revision or supersession notes: `UNKNOWN`
- Operational or iteration signal to watch: `UNKNOWN`

This brief records intent and planning context. It does not prove demand,
feasibility, usability, safety, approval, acceptance, or release readiness.
Planned discovery remains `NOT_RUN`; a missing product or repository identity
remains `UNKNOWN` with its reason rather than blocking this brief.
