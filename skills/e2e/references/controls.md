# Controls reference

Use this reference to decide which controls apply. The 16 areas are an inventory, not a claim that every subject needs every control. For each area, record `APPLICABLE`, `PARTIAL`, `UNKNOWN`, or `N/A` with a reason, accountable owner, evidence target, and reassessment trigger. Use the rows in [../assets/checklist.md](../assets/checklist.md) for a traceable starting set.

## Applicability questions

Ask these questions before selecting modules:

1. What subject, journey, artifact, data, actor, tenant, and environment are being evaluated?
2. Does the subject contain a UI, API, persistent data, model, retrieval corpus, agent, tool, training pipeline, or production operation?
3. Which controls are mandatory for the intended release or risk profile, and who set that policy?
4. What source, artifact, model, prompt, corpus, and configuration identity can be established?
5. Which tool capabilities, credentials, network access, browser actions, or human decisions are authorized?

## 1. Scope and identity

Establish source revision and dirty state, artifact or image digest, dependency and SBOM inventory, runtime topology, owners, data classes, tenants, threat actors, trust boundaries, third parties, critical journeys, and changes from the baseline. Identity must be specific enough to bind an observation to the subject being decided.

## 2. Requirements and design

Trace intended behavior, nonfunctional requirements, abuse cases, acceptance criteria, decisions, API and schema compatibility, feature flags, deprecations, and residual-risk ownership. Requirements are policy inputs; a design document is not proof that behavior exists.

## 3. Source and supply chain

Review branch and change protection, least privilege, secret handling, source and dependency pins, licenses and notices, vulnerability response, build isolation, provenance, SBOM, artifact signing and verification, immutable promotion, and relevant supply-chain controls. A declared license or lock file needs scope and identity review.

## 4. Application security

Assess authentication, MFA where needed, session and token lifecycle, server-side authorization, object and tenant boundaries, validation, injection, browser protections, SSRF and egress, uploads and archive paths, deserialization, cryptography and keys, secret rotation, error leakage, rate and resource limits, audit trail, break-glass access, headers, and dependency or container findings.

## 5. Data, privacy, and migration

Check inventory and lineage, minimization, consent and purpose, retention and deletion, residency, encryption, key access, tenant isolation, integrity and idempotency, migration compatibility, backfill, concurrency, rollback or roll-forward, replica, queue, cache and object consistency, masked test data, and redacted logs.

## 6. QA, QC, and test strategy

Trace requirements to tests. Cover unit, contract, integration, real data stores where applicable, negative and abuse paths, property or fuzz testing where valuable, concurrency, regression, browser and device journeys, smoke, performance, load, soak, failure injection, flaky-test handling, test-data isolation, coverage risk, severity triage, and fresh report retention.

## 7. CI/CD and release

Assess reproducible clean builds, lint and type checks, static and security checks, required-check enforcement, trusted runners, protected secrets, environment separation, artifact promotion, exact tested-versus-promoted digest, approvals, canary or progressive rollout, rollback triggers, migration ordering, post-release smoke, and the release evidence bundle.

## 8. UI, UX, and accessibility

When a UI is applicable, inspect loading, empty, error, success, and disabled states; information architecture; hierarchy and copy; design tokens; typography, spacing, density, affordance, feedback, responsive reflow and zoom; keyboard order and focus; navigation; semantic names, roles and values; label and error relationships; dialog focus; announcements; contrast and non-color cues; target size; reduced motion; locale formats; destructive confirmation; latency feedback; field versus lab performance; screenshots; and manual journey evidence. Automated checks alone do not establish accessibility conformance.

## 9. Reliability, SRE, and production readiness

Identify service owner and on-call, SLI/SLO and error budget, dependency objectives, capacity and quota, saturation, timeout and retry policy, backoff and jitter, circuit breaking, idempotency, graceful degradation, poison and dead-letter queues, health and readiness semantics, golden signals, alert routing, dashboards, log and trace correlation, deploy markers, runbooks, incident severity and escalation, maintenance, toil, and defined DORA measurements.

## 10. Recovery and continuity

Set approved RPO and RTO. Verify backups for every data class, off-host or immutable retention, restore, point-in-time recovery, corruption and ransomware scenarios, provider or region dependencies, failover and failback, credential recovery, reconciliation, business continuity, tabletop exercise, and actual restore evidence. A backup script without a restore result is incomplete evidence.

## 11. AI-assisted engineering

Review repository instructions, bounded task scope, minimum file/network/tool access, secret exclusion, untrusted issue and document inputs, dependency provenance, diff review, generated-test adequacy, migration and infrastructure review, prompt and version recording, reproducible commands, preservation of user changes, and an independent human or automated check. Prompt text is guidance, not a security boundary.

## 12. AI runtime and retrieval

If a model or retrieval feature reaches users or business processes, assess intended and prohibited use, model and provider identity, prompt version, corpus source and freshness, retrieval relevance, citation support, correctness, abstention, contradiction and unsupported claims, direct and indirect prompt injection, poisoning, disclosure, output encoding and validation, authorization before and after inference, human oversight, feedback, drift, rollback, latency, token and cost budget, cancellation, provider errors, repeated-run variance, and redacted telemetry.

## 13. Agent, tool, and MCP behavior

For model-directed tools or MCP, assess allowlists and schemas, per-tool authorization, least-privilege identity, confused-deputy risk, parameter validation, side-effect preview and approval, idempotency, transaction and compensation boundaries, recursion and delegation limits, time and spend budgets, inter-agent trust, memory provenance and deletion, tool-result injection, audit chain, kill switch, and applicable protocol capability, transport, authentication, session, origin, consent, elicitation, sampling, server and tool trust, and compatibility controls. Mark non-applicable protocol fields with evidence.

## 14. Training and fine-tuning

When there is a training pipeline, verify dataset provenance, license and consent, PII handling, labeling quality, split and leakage controls, poisoning defenses, reproducibility, model registry, evaluation, bias, safety and security review, release card, rollback, and deletion or unlearning obligations. Without a training pipeline, record why this area is `N/A` and the trigger for reassessment; do not confuse human training with model training.

## 15. AI evaluation

Use representative data and a separated holdout. Define a domain rubric, ground truth, reviewer process, retrieval and semantic correctness, source support, abstention, privacy, security, authorization, latency, and cost as distinct measures. Add deterministic cases, calibrated graders, repeated runs, variance, language, tenant and risk slices, adversarial cases, regression thresholds, and versions or hashes for dataset, prompt, corpus, grader, model, and code. Do not average away a security or unsupported-claim failure.

## 16. UAT and governance

Validate business journeys, roles and tenants, data effects, reconciliation, operational handoff, support, runbook and training, legal, privacy, security and AI-quality decisions, known limits, residual-risk acceptance, rollback rehearsal, and named sign-off by the applicable Product, Service or SRE, Security, Data, AI Quality, and Release owners. UAT and sign-off are human decisions; an agent cannot sign them.

## Status and ownership rules

`PASS` is reserved for a run with valid expected output and matching identity. `FAIL` is a valid observed mismatch. `NOT_RUN` records absent execution or capability. `UNKNOWN` records insufficient evidence, identity, coverage, provenance, freshness, or owner decision. `N/A` requires an applicability record and reassessment trigger. Keep task status independent from check status: authored tasks may be complete while their runtime checks remain `NOT_RUN`.
