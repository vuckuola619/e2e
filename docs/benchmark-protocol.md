# Proposed benchmark protocol

**Protocol status:** `PROPOSED`  
**Runtime benchmark status:** `NOT_RUN`  
**Harness status:** no harness exists

This document defines a future, controlled comparison of lifecycle and
readiness guidance. It is a protocol, not a report of executed trials. The
revision-pinned documentary source comparison is available in
[`docs/comparison.md`](comparison.md), with its machine-readable metadata in
[`research/comparison-2026-09-16.json`](../research/comparison-2026-09-16.json).
That source review was completed; no performance or quality head-to-head was
run. No installed package, fake run, private application, or real customer
data is part of this protocol.

## Questions and claims

The benchmark may ask whether a condition produces complete, truthful,
traceable lifecycle artifacts and readiness outputs under matched tasks. It may
measure the outcomes below after execution. It must not claim that a tool is
faster, safer, better, more complete, or a winner from documentation, stars, a
small sample, or an unmeasured field.

Preregister the hypotheses, expected direction if any, rubric, hidden labels,
stopping rules, exclusions, and analysis before running a trial. A result can be
`UNKNOWN`, unsupported, invalid, or abstained; those are reportable outcomes,
not values to convert into zero or success.

## Conditions and two separate tracks

Run one peer condition at a time. The same host and model setup must receive:

| Condition | Input boundary | Intended comparison |
| --- | --- | --- |
| Plain host baseline | Task, fixture, and ordinary host instructions only. | Baseline artifact and evidence behavior. |
| Host + `e2e` | The pinned e2e skill and only the resources declared in its closure. | Effect of the guidance-only e2e workflow. |
| Host + one relevant peer | One peer's pinned guidance and declared resources. | One paired guidance comparison; repeat separately for each peer. |
| Qualified native runtime | Exact released package/plugin bytes, installer, hooks, state, browser, subagents, and host contract for one product. | Native runtime behavior, reported separately from guidance. |

The **shared guidance/artifact track** compares a plain host, host + e2e, and
host + one relevant peer using Markdown or equivalent instructions without
installing or executing an upstream runtime. It evaluates planning, artifact,
evidence, and recommendation outputs.

The **qualified native installation/runtime track** is a separate study. It may
run only after an exact released package, host version, installer behavior,
hooks, state, browser or subagent surface, permissions, and cleanup boundary
have been qualified for that cell. Never pool native-runtime observations with
guidance-only results or imply feature parity between tracks.

## Matched conditions

Freeze and record these inputs for every matched cell:

- identical synthetic fixture commit, starting files, local service data, task
  text, user context, and hidden expected labels;
- exact host, model, model version, reasoning setting, system/developer prompt,
  temperature or equivalent setting, tool versions, and resource revisions;
- exact e2e or peer revision, linked-resource closure, package bytes, install
  procedure, and configuration for the selected track;
- identical network policy, filesystem and process permissions, credentials
  policy, browser/device boundary, tool allowlist, and external-side-effect
  prohibition;
- identical wall-time limit, input/output/reasoning/tool-token budgets,
  concurrency, retry and resume budgets, and workspace cleanup procedure; and
- one pre-registered evaluator rubric, expected-output schema, review scope,
  and adjudication rule.

Use fresh disposable workspaces and fresh task context for every trial. Randomize
condition order within each matched cell, preserve the random seed and order,
and do not let an earlier artifact or reviewer label a later trial. Use five
repeats per matched cell as a proposed starting point; increase the sample only
under the pre-registered stopping rule. Five repeats are descriptive and cannot
establish a winner.

## Synthetic scenario matrix

All ten scenarios below are `NOT_RUN`. Each fixture must be synthetic,
deterministic, and pinned. The oracle is an independent expected-label and
required-artifact specification, not the output of the system being tested.

| # / scenario | Inputs | Required outputs and oracle | Applicability | Track |
| --- | --- | --- | --- | --- |
| 1. Idea / MVP / no repository | A short idea, affected-actor context, constraints, and no repo or artifact. | Brief or direct-path recommendation, hypotheses, alternatives, outcomes, non-goals, and discovery questions. Oracle: identity is `UNKNOWN` with a reason; no demand or validation claim; no forced PRD or release verdict. | `IDEA`, `DISCOVERY`, `PRODUCT_PLANNING` | Guidance; native only if the product has a qualified intake surface. |
| 2. Ambiguous requirements and tradeoffs | Conflicting acceptance statements, missing owner, and competing privacy, UX, or delivery constraints. | Clarifying questions, assumptions, options, tradeoff record, and pending decision. Oracle: ambiguity remains visible; no invented approval, owner, or requirement. | `PRODUCT_PLANNING`, `DESIGN`, `REVIEW` | Guidance and qualified native. |
| 3. Brownfield feature | Pinned existing project with a narrow feature request, current tests, and unrelated dirty or excluded paths. | Scoped plan, requirement/design links, atomic tasks, change or proposed change, and verification targets. Oracle: unrelated scope preserved; traceability and unknowns retained. | `BUILD`, `REVIEW`, `QA` | Guidance and qualified native. |
| 4. Small bug / minimal process | Synthetic project with a reproducible defect and a clear expected fix. | Direct task/check flow, minimal implementation or plan, and verification record. Oracle: no mandatory brief, discovery study, or full lifecycle ceremony; a check is `NOT_RUN` unless it ran. | `BUILD`, `QA` | Guidance and qualified native. |
| 5. Tenant-security negative | Synthetic multi-tenant service and a cross-tenant access attempt with a known expected denial. | Finding or failed check with tenant scope, evidence anchor, and remediation path. Oracle: no false `PASS` or `READY`; a missing run is `NOT_RUN`/`UNKNOWN`, not a clean result. | Application security, data/privacy, UAT/governance | Guidance and qualified native. |
| 6. UI and accessibility | Synthetic page with loading, empty, error, keyboard, focus, semantics, contrast, and responsive states. | State inventory, accessibility observations, checks, limitations, and evidence pointers. Oracle: required states and keyboard semantics are considered; visual or runtime claims need actual evidence. | `DESIGN`, `REVIEW`, `QA`, UI/UX/a11y | Guidance and qualified native when browser capability is qualified. |
| 7. Wrong candidate / timeout / missing UAT release | Two candidate digests, one wrong selection, a timed-out check, and no required UAT acceptance. | Preserved identities, timeout/status records, missing acceptance, and release review outcome. Oracle: no positive readiness decision from mismatched or incomplete proof; `UNDETERMINED` or `NOT READY` follows the defined policy. | `RELEASE`, `RELEASE_REVIEW`, UAT/governance | Guidance and qualified native. |
| 8. Operations and rollback | Synthetic deployed identity, rollout plan, telemetry sample, runbook, rollback trigger, and a failure signal. | Operational evidence, rollout/rollback expectations, owner, monitoring limits, and iteration handoff. Oracle: no deployment claim without an authorized run; missing telemetry or recovery proof stays visible. | `RELEASE`, `OPERATE`, recovery/SRE | Guidance and qualified native only with an authorized disposable service. |
| 9. Lossy context | Large synthetic evidence with warnings, errors, mandatory statuses, omitted ranges, and a proposed compact view. | Raw pointers, selected/omitted counts, ordered loss manifest, preserved warnings and mandatory anchors. Oracle: compaction never deletes status or evidence identity and cannot support an unsupported absence claim. | AI-assisted, evidence/context, all phases as relevant | Guidance and qualified native. |
| 10. Interrupted resume | Pinned multi-task run interrupted after partial output and before cleanup, then resumed in a fresh process. | Immutable first attempt, signal/timeout and partial output, durable task state, new retry/resume identity, and cleanup record. Oracle: no crash is a clean pass; prior output is retained; resume rechecks subject, policy, and permissions. | `BUILD`, `QA`, `OPERATE`, state/resume | Guidance and qualified native. |

## Outcome rubric and metrics

Separate deterministic checks from subjective rubric items. Blind reviewers to
condition and peer labels; use at least two independent semantic reviewers for
subjective judgments and a pre-registered adjudication rule for disagreement.
Report every attempt, timeout, invalid trial, abstention, and unsupported
output.

| Metric | Required definition and reporting rule |
| --- | --- |
| Accepted outcomes | Count and rate of outputs satisfying the pre-registered scenario oracle, with each acceptance dimension reported separately. A completed artifact is not automatically accepted. |
| Unsupported claims | Count and rate of material claims lacking required source, scope, identity, or evidence; report claim denominator and categories. |
| Coverage / missing / unsupported | Expected fields, controls, states, and handoffs versus valid produced items; report present, missing, unsupported, and out-of-scope counts. |
| False-ready | Count of `READY` or equivalent positive release claims that violate the hidden oracle, divided by the pre-registered eligible positive-decision denominator. Report the denominator, all-trial denominator, and abstention count/rate separately. |
| Precision / recall | Compute only for independently labelled truth, with TP/FP/FN definitions and the labelled denominator. Do not score unlabeled absence or treat `UNKNOWN` as a negative. |
| Identity / evidence completeness | Required subject, artifact, revision, procedure, status, time, provenance, and evidence anchors present and matching the fixture; report each missing or mismatched component. |
| Time to valid output | Wall time from task dispatch to the first output that satisfies the validity rubric. Report setup time, user wait/input time, provider wait, and execution time separately; do not hide them in one timer. |
| Tokens and cost | Record actual input, output, reasoning, tool, and retry tokens when exposed, plus pinned model/tool rates and measured cost components. Use `UNKNOWN`, never zero, when a host cannot expose a component. |
| Resume correctness | On interrupted trials, count expected durable state, no duplicate or unauthorized side effect, identity recheck, correct remaining work, and equivalent accepted outcome. Report the interrupted-trial denominator. |
| Reviewer agreement | Report agreement and adjudication for subjective labels, with the rubric version and unresolved disagreements. |

Retain confidence intervals or other uncertainty intervals appropriate to each
label and denominator. Use exact or bootstrap methods only when their
assumptions fit the data. Do not average away mandatory failures, abstentions,
unsupported cases, or invalid trials. Do not select a winner from five repeats
or from popularity stars.

## Evidence and integrity record

Each trial receives an immutable ID and an evidence manifest containing, where
available:

- condition, scenario, repeat, random order/seed, track, host/model/settings,
  fixture and resource revisions, package/install hashes, and permissions;
- exact prompt and context, commands or host procedures, environment and
  network policy, start/end times, setup/user-wait timings, and budget values;
- stdout, stderr, tool/model calls, artifact paths, exit status, signal,
  timeout, retry/resume events, cleanup state, and all produced outputs;
- independent oracle label, reviewer labels, rubric version, adjudication,
  metric inputs, uncertainty method, and limitations; and
- sensitivity, redaction, raw/private pointers, and a content identity for
  exported bytes.

Redact secrets and personal data without silently changing the inputs used for
scoring. If a frozen condition changes, a dependency is unavailable, or a
required measure cannot be captured, mark the cell invalid, `UNKNOWN`, or
`NOT_RUN` under the preregistered rule. Preserve the attempted record rather
than substituting a convenient result.

## Future reproduction steps

1. Preregister this protocol's hypotheses, scenario fixtures, hidden labels,
   rubric, stopping rule, and analysis before collecting outcomes.
2. Create deterministic synthetic repositories and disposable local services;
   pin their revisions and prepare a fresh workspace for each repeat.
3. Qualify the selected native package cells separately, then run randomized
   guidance cells and native cells under their own track rules.
4. Collect the full manifest and raw outputs, preserve timeouts and interrupted
   attempts, and run independent blinded review.
5. Adjudicate disagreements, compute pre-registered metrics and uncertainty,
   and publish every condition, denominator, abstention, limitation, and
   unsupported measure.

No code or benchmark harness is supplied by this document. A future host must
execute only explicitly authorized work, and `runtime_benchmark_status: NOT_RUN`
remains the correct status until those steps produce reviewable evidence.
