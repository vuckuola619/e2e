# Product plan template

Use this concise plan for work whose product intent, coordination, impact, or
operational consequences need more structure than a direct task. Keep optional
sections only when their domains apply. A small, clear change can use the
existing task and check flow without completing this template.

```yaml
artifact_id: UNKNOWN
document_status: DRAFT
current_phase: PRODUCT_PLANNING
phase_span:
  - PRODUCT_PLANNING
owner: UNKNOWN
revision: UNKNOWN
supersedes: []
upstream_artifacts:
  - UNKNOWN
downstream_artifacts: []
subject:
  name: UNKNOWN
  repository_or_artifact: UNKNOWN
  identity_reason: "No repository or artifact was supplied, or identity is not yet established."
planning_status: DRAFT
```

## Outcome and users

- Product outcome: `UNKNOWN`
- Intended users or affected actors: `UNKNOWN`
- Jobs, journeys, or workflows: `UNKNOWN`
- Earliest measurable success signal: `UNKNOWN`
- Failure, harm, or stop signal: `UNKNOWN`
- Evidence or source for each signal: `UNKNOWN`

Do not turn an intended user, outcome, or measure into an observed fact without
source and scope.

## Scope and requirements

- In scope for this increment: `UNKNOWN`
- Explicit non-goals: `UNKNOWN`
- MVP priority and rationale: `UNKNOWN`
- Deferred scope and why it is deferred: `UNKNOWN`
- Resource or effort assumptions (proposed): `UNKNOWN`
- Functional requirements: `UNKNOWN`
- Nonfunctional requirements: `UNKNOWN`
- Acceptance boundary and measurable checks: `UNKNOWN`
- Open product decisions: `UNKNOWN`

### Applicable constraints

Record only the sections that apply, with an owner and a reason for omissions:

- UX, content, responsive, and accessibility states: `UNKNOWN`
- Architecture, data flow, integration, and migration: `UNKNOWN`
- Security, privacy, retention, and tenancy: `UNKNOWN`
- Legal, governance, and policy: `UNKNOWN`
- Reliability, capacity, observability, and recovery: `UNKNOWN`
- AI model, prompt, corpus, tool, training, or evaluation boundaries:
  `UNKNOWN`

## Options, dependencies, and risks

| Item | Options or dependency | Chosen / proposed direction | Reason and evidence | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

Include architecture options or an ADR link when a technical choice is
material. A proposal is not an implemented decision, and an owner or approval
cannot be inferred from a blank field.

## Delivery slices and handoffs

Use [`task.md`](task.md) for each atomic implementation or verification task;
the table below links those tasks without duplicating their full acceptance
schema. Any estimates or schedule are proposals until work actually occurs.

| Slice or task | Phase | Dependency | Existing task ID or link | Expected outcome | Verification target |
| --- | --- | --- | --- | --- | --- |
| `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` | `UNKNOWN` |

Link applicable rows to the existing trace
`CHK-* → TSK-* → REQ-* → GATE-* → EVD-*`. Keep implementation, review, QA, and
release work separately where their owners, environments, or evidence differ.

- Design artifact(s): `UNKNOWN`
- Build or implementation task(s): `UNKNOWN`
- Review and QA plan: `UNKNOWN`
- UAT or acceptance owner: `UNKNOWN`
- Dependencies and critical path: `UNKNOWN`
- Planned work status: `NOT_RUN` unless it actually ran

## Release and operations

- Candidate identity and provenance: `UNKNOWN`
- Rollout and exposure plan: `UNKNOWN`
- Rollback, kill, or recovery criteria: `UNKNOWN`
- Support handoff and runbook: `UNKNOWN`
- Operational owner and alert or SLO expectations: `UNKNOWN`
- Release evidence and proof-set link: `UNKNOWN`

These are expectations to plan. They do not prove a release review, deployment,
rollback exercise, or operational readiness occurred.

## Measurement and iteration

- Measurement window and source: `UNKNOWN`
- Outcome and operational signals to collect: `UNKNOWN`
- Feedback owner: `UNKNOWN`
- Revisit trigger: `UNKNOWN`
- Phase to revisit: `UNKNOWN`
- Next decision: `UNKNOWN`
- Superseded revision(s): `UNKNOWN`

Create a new plan revision when learning changes scope or direction. Preserve
prior plans, findings, and evidence as historical records.

## Continuity and limitations

- Upstream brief, discovery, and design IDs or paths: `UNKNOWN`
- Downstream task, check, release, and iteration IDs or paths: `UNKNOWN`
- Assumptions that remain untested: `UNKNOWN`
- Material unknowns and owners: `UNKNOWN`
- Document reviewer or acceptance: `UNKNOWN`

This is a planning artifact. It does not perform research, prove demand or
feasibility, approve a design, mark a task `DONE`, create a check `PASS`, issue
a readiness decision, or grant authorization. A missing repository or artifact
identity remains `UNKNOWN` with its reason and does not block context-only
planning.
