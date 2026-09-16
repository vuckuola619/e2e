# Product lifecycle reference

Read this reference when the request involves shaping an idea, discovery,
product planning, design, delivery, operations learning, or iteration. It
extends the readiness workflow; it does not add a runtime engine or replace the
assurance controls.

## Phase and mode are separate axes

The lifecycle phase says where the work sits in the product journey. The
assessment mode says what the host may do for this request. Record one current
phase and, when useful, a bounded `phase_span`; select exactly one assessment
mode. A phase never grants permission, and a mode never claims that a phase or
artifact is complete.

The common path is shown in order for orientation. Work can start at any phase,
return to an earlier phase, or end after a bounded slice.

| Phase | Purpose | Typical inputs | Minimum useful output | Material unknowns to expose | Likely roles | Handoff or feedback destination |
| --- | --- | --- | --- | --- | --- | --- |
| `IDEA` | Frame a problem, opportunity, or change worth considering. | User request, context, observed signal, or an existing issue. | A brief idea statement with users or actors, outcome, constraints, and open questions. | Who is affected, whether the problem is real, desired outcome, urgency, and artifact identity. | Sponsor, product, domain owner, researcher. | `DISCOVERY` for uncertainty; `PRODUCT_PLANNING` or `BUILD` for a clear small change. |
| `DISCOVERY` | Reduce uncertainty with proposed or executed research and validation. | Idea or brief, research questions, available sources, and authorization. | A discovery plan and, when work ran, findings with provenance and a disposition. | Recruitment, sample or source coverage, consent, bias, feasibility, and contradictory signals. | Researcher, product, domain users, privacy or legal reviewer. | `PRODUCT_PLANNING`, reframe, pause, or stop; planned work stays `NOT_RUN`. |
| `PRODUCT_PLANNING` | Turn intent and evidence into a coherent product scope and delivery plan. | Brief, discovery record, constraints, existing product context, and decisions. | A concise product plan with journeys, requirements, tradeoffs, dependencies, and measures. | Feasibility, ownership, sequencing, cost, safety, privacy, accessibility, and operations. | Product, engineering, design, QA, security, operations, governance. | `DESIGN`, `BUILD`, or a new discovery question. |
| `DESIGN` | Define behavior, interaction, content, architecture, and quality boundaries. | Requirements, journeys, states, constraints, and applicable assurance domains. | A design decision or artifact with alternatives, edge states, and acceptance targets. | Unhandled states, accessibility, data flow, threat boundaries, and integration behavior. | Design, engineering, content, security, accessibility, domain owner. | `BUILD`, `REVIEW`, or `PRODUCT_PLANNING` when tradeoffs change scope. |
| `BUILD` | Create or configure the authorized product change. | Approved or selected requirements, design, tasks, dependencies, and target identity. | A changed subject or a documented implementation plan, with verification targets. | Actual behavior, dependency effects, migration safety, environment differences, and rollback. | Engineering, data, platform, automation, service owner. | `REVIEW` and `QA`; a defect may return to `BUILD`. |
| `REVIEW` | Examine the intent, design, change, and evidence for defects or unresolved risk. | Brief or plan, design, diff or candidate, findings, and applicable controls. | Review findings, decisions, owners, and a path to address or accept each issue. | Review coverage, independent perspective, residual risk, and evidence identity. | Peer reviewer, product, security, privacy, accessibility, operations. | `BUILD`, `QA`, `RELEASE`, or `PRODUCT_PLANNING` when scope changes. |
| `QA` | Run and reconcile checks against defined behavior and risk. | Candidate, test or evaluation strategy, environments, procedures, and controls. | Traceable observations and evidence with distinct `PASS`, `FAIL`, `NOT_RUN`, `N/A`, or `UNKNOWN`. | Environment parity, coverage, flakiness, data safety, negative paths, and tool limits. | QA, UAT, engineering, security, AI quality, accessibility. | `BUILD`, `REVIEW`, or `RELEASE` for the exact candidate. |
| `RELEASE` | Decide whether a candidate can enter its intended rollout process. | Candidate identity, proof set, acceptance, rollout, rollback, and support plan. | A release review record; include rollout or rollback records only when requested and authorized. | Identity match, freshness, mandatory proof, owner acceptance, rollback, and communication. | Release owner, product, engineering, QA, security, operations, governance. | `OPERATE` after an authorized rollout; a blocker returns to `BUILD` or `QA`. |
| `OPERATE` | Observe the product in its real operating context and manage incidents or support. | Deployed identity, runbook, telemetry, support reports, incidents, and SLOs. | Operational observations, incident or support records, and learning signals. | Telemetry coverage, causality, user impact, capacity, recovery, and unobserved failure modes. | Service owner, SRE, support, product, security, privacy. | `ITERATE`, `REVIEW`, or `RELEASE` for a rollback or remediation decision. |
| `ITERATE` | Use learning to choose what to revisit and create a new revision. | Operational signals, user feedback, findings, outcomes, and open hypotheses. | A decision, new artifact revision, or explicit continue/reframe/pause/stop record. | Whether a signal represents a durable pattern, which phase should change, and who decides. | Product, research, design, engineering, operations, domain owner. | Any earlier phase, selected by the new decision and bounded scope. |

## Entry, spans, and planning depth

Use the phase that best describes the current decision or work. An idea can be
planned without a repository, build artifact, customer record, or research
result. Record the missing identity as `UNKNOWN` with a reason; use `N/A` only
when the artifact is genuinely outside scope and record why. Do not block a
context-only plan while waiting for an artifact that does not yet exist.

An existing product may enter at `OPERATE`; a bug may enter at `BUILD`,
`REVIEW`, or `QA`; and `ITERATE` may route to any earlier phase. A skipped phase
needs a reason only when it is materially relevant to the decision. Phase
completion is not a ritual prerequisite, and a plan, approved document, or
completed task does not create evidence or a release verdict.

Choose the smallest planning depth that addresses uncertainty, risk, product
impact, coordination cost, regulatory or privacy concerns, and operational
impact:

| Depth | Use when | Minimum record |
| --- | --- | --- |
| **Direct** | A small, clear, low-risk change has a known outcome and bounded impact. | The existing task, checklist, check, and evidence flow; record phase and why product ceremony is unnecessary. |
| **Brief** | Product intent, affected actors, alternatives, or meaningful uncertainty needs to be made explicit. | [`product-brief.md`](../assets/product-brief.md), with [`discovery-plan.md`](../assets/discovery-plan.md) when research is proposed or needed. |
| **Full** | Work spans teams or epics, carries high product, privacy, safety, regulatory, or operational impact, or has substantial unresolved tradeoffs. | The brief and applicable discovery plan, [`product-plan.md`](../assets/product-plan.md), design and assurance artifacts, dependencies, rollout, operations, and measurement handoff. |

Depth is a decision about useful context, not a requirement to complete every
phase. A clear existing-project fix can use the direct path even when the
repository has no product brief.

## Truth and status rules

Keep these classes separate in every lifecycle artifact:

- **Observed signal or fact:** something actually seen, with source, time,
  scope, and evidence reference when available.
- **Source-backed finding:** an interpretation supported by identified source
  material and its limitations.
- **Assumption:** a proposition used for planning that has not been established.
- **Hypothesis:** a testable belief about users, behavior, outcomes, or risk,
  with a confidence basis and a way to challenge it.
- **Proposal:** a recommended option, experiment, design, or next step.
- **Owner decision:** an actual decision attributed to a named person or role,
  with scope and time when available. A pending decision or missing owner stays
  `UNKNOWN`; a document status is not the same thing.
- **Unknown:** an unresolved identity, coverage, provenance, feasibility, or
  outcome question with a next discovery step where possible.

An interview plan is not an interview. A survey draft is not demand. Proposed
recruitment is not participation. A product brief is not validation, a design
approval is not verified behavior, and task completion is not a passing check.
Use `NOT_RUN` for planned research or checks, `UNKNOWN` when the information is
insufficient, and `N/A` only with an applicability reason and reassessment
trigger.

## Artifact continuity and handoffs

Give each artifact a local ID, revision, status, owner or `UNKNOWN`, upstream
links, downstream links, and a supersession relation when it replaces an older
revision. Later artifacts should cite the IDs or paths they relied on. Revise
by creating a new record; preserve prior evidence and findings as historical
records rather than overwriting them.

The lifecycle handoff extends the assurance trace:

```text
idea or hypothesis
  -> discovery evidence
  -> product brief or plan
  -> requirement and design
  -> task and check
  -> evidence or finding
  -> release decision
  -> operational signal
  -> iteration decision
```

For assurance work, retain the canonical trace
`CHK-* → TSK-* → REQ-* → GATE-* → EVD-*`. Link product artifacts before the
requirement and link operational or iteration signals after the evidence and
decision. A missing upstream link is a traceability gap, not proof that the
underlying work did not occur.

Discovery dispositions such as `continue`, `reframe` or `pivot`, `pause`, and
`stop` are owner decisions about product learning. A recommendation to
`validate`, `pivot`, or `build` is a proposal until an owner decides. These are
not the four canonical
readiness decisions: `READY`, `CONDITIONALLY READY`, `NOT READY`, and
`UNDETERMINED`. None of these decisions, and no lifecycle phase or artifact,
grants authorization to deploy, publish, contact people, spend, or mutate an
external system.
