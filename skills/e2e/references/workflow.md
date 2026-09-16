# Workflow reference

This file describes how to use the `e2e` skill as a portable planning and assessment guide. It does not provide a runner, plugin, command-line program, or host adapter. The host decides which tools exist and must report unavailable capabilities explicitly.

## 1. Establish the assessment packet

Create a small index for each assessment with these fields:

| Field | Required content |
| --- | --- |
| Subject | Product, service, workflow, repository, model-backed feature, or release artifact in scope |
| Scope | Included paths, services, journeys, tenants, environments, controls, and exclusions |
| Mode | Exactly one of `PLAN_ONLY`, `READ_ONLY_AUDIT`, `IMPLEMENT_AND_VERIFY`, `RELEASE_REVIEW` |
| Identity | Revision, dirty-state record, artifact digest, image/model/prompt/corpus identity where relevant |
| Authorization | User request, authorized actions, expiration or boundary, and unresolved owner decisions |
| People | Accountable owner, verifier, reviewer, acceptance signers required by applicability |
| Sensitivity | Data classes, private evidence location, redaction policy, retention, and export audience |
| Time | Observation time for each run; report time is separate and never substituted for observation time |
| Status | `DRAFT`, `REVIEWED`, or `APPROVED` for the document itself; check status remains separate |

Keep observed facts, assumptions, proposed controls, owner decisions, and `UNKNOWN` items in separate sections. An absent file is not proof that a control is absent; an existing file, test, workflow, dashboard, or score is not proof that the control passed.

## 2. Route one entrypoint

Use one router to select the minimum set of typed roles:

1. control and requirement definitions;
2. advisory guidance or design review;
3. observation producers or importers;
4. context selection and retrieval;
5. canonical evidence validation and release evaluation.

The router should explain each selection with applicability, mode, source identity, maturity, host capability, permission, budget, freshness requirement, and conflict outcome. A module may be selected as guidance without being trusted to produce observations. An importer may parse a native result without deciding a release verdict. A context provider may reduce input without deleting raw evidence.

Resolve resource closure before using a module. Record every linked prompt, schema, script, template, binary, notice, license, and transitive reference that is required for the selected operation. Unknown licensing or missing files keeps the resource reference-only or unqualified. Do not load an entire catalog into context to answer a narrow task.

Choose no more than one primary provider for a role that has canonical authority, such as a release evaluator or graph source. A second provider may be an independent comparison or fallback only when the contract states how disagreement is handled. UI modules are routed only when a UI is applicable. Graph and compaction modules are accelerators; they cannot prove that a symbol, dependency, defect, or evidence item does not exist.

## 3. Dispatch by mode

### `PLAN_ONLY`

Produce a scope and applicability matrix, requirements, gates, checklist trace, task graph, verification commands, evidence targets, risks, ownership, and cleanup plan. Read-only reconnaissance of the authorized subject is allowed when it grounds the plan; record its identity and limitations. Commands that are not known remain `UNKNOWN`. Do not implement, verify runtime behavior, install a tool, contact a provider, or mutate external state. Writing the requested plan or authorized run output does not require a new permission.

### `READ_ONLY_AUDIT`

Inspect only the authorized subject and preserve the subject's state. Capture revision, dirty state, source or artifact identity, tool versions, command and working directory, output and exit status for each real check. Store generated reports and private raw evidence in the separately authorized run directory. A report can describe gaps without changing the target. If an inspection would write to the target, stop that check as `NOT_RUN` and use a safe direct-source or disposable mirror path only when separately authorized.

### `IMPLEMENT_AND_VERIFY`

Before changing files or configuration, restate the authorized change scope and capture the starting identity. Make the smallest change that satisfies the task. Preserve unrelated user changes. Verify the changed behavior with a defined command or human procedure, capture fresh evidence, and record cleanup or rollback. A successful edit is not a passing release check until the applicable verification and review are complete.

### `RELEASE_REVIEW`

Bind the review to the exact candidate artifact and release scope. Check that the tested artifact and promoted artifact have matching identity and provenance, that mandatory evidence is fresh and complete, and that required human acceptance is named. Deployment, publication, commit, comment, upload, or approval actions are separate operations requiring their own authorization.

## 4. Build the trace and DAG

For every material checklist item, create a requirement and gate, then one or more atomic tasks:

`CHK-* → TSK-* → REQ-* → GATE-* → EVD-*`

Use the task template in [../assets/task.md](../assets/task.md). A subtask has one main verb, one outcome, one owner role, one environment, and one verification. Include precondition, action, expected state or data effect, evidence capture, and cleanup in its acceptance. A task may be `DONE` while its check is `NOT_RUN`; documentation completion does not create runtime evidence.

Draw a dependency graph and run a cycle check before execution. Report topological order, parallel lanes, critical path, external credentials or decisions, and release-blocking gates. Separate the pre-promotion graph from release and post-deployment work. Keep deployment and final human sign-off as distinct tasks even when the selected mode permits implementation.

Use `DEFERRED` only with a reason, owner, expiry, and re-entry trigger. Use `N/A` only with applicability evidence and a reassessment trigger. If a finding has no fix in scope, create a time-bounded risk-acceptance task; an unowned finding is not resolved by a report.

## 5. Resume without overwriting evidence

Each attempt is immutable. A retry creates a new attempt and preserves the prior result, even when it failed. A resume may continue only from the last durable task state and must recheck subject, policy, artifact, authorization, and dependency identity. A changed dirty diff, policy, selected module, source hash, or configuration invalidates claims that depend on the old identity. Never choose the best or newest result without checking identity, completeness, and relevance.

On interruption, retain partial stdout/stderr, signal or timeout, exit code when available, diagnostics, completed task IDs, remaining tasks, and cleanup state. A crash or cancellation is not a clean check. If the host cannot safely resume, mark the affected evidence `NOT_RUN` or `UNKNOWN` and provide the next executable discovery task.

## 6. Route failures and uncertainty

Use producer status, evidence validity, and canonical check status as separate fields. A valid producer finding may normalize to `FAIL`; a missing, malformed, stale, cached-for-another-subject, or invocation-error result is invalid or unresolved. Zero findings is meaningful only when the expected case inventory, output, subject identity, and producer semantics are complete.

When a graph or compact view is stale, preserve the warning and coverage. Read the authorized source directly to create a new source-confirmed observation if possible. If source confirmation is unavailable, keep the absence claim `UNKNOWN`. A lossy context view must show selected and omitted counts, loss reason codes, transform version, freshness, and retrieval references to raw artifacts.

## 7. Close the assessment

Publish a findings table, evidence manifest, decision proof set, limitations, and shortest executable path to the next decision. Use exactly one final decision: `READY`, `CONDITIONALLY READY`, `NOT READY`, or `UNDETERMINED`. A positive decision requires applicable mandatory evidence, candidate identity, and required human acceptance. A conditional decision may contain only nonblocking, bounded, accepted obligations. The decision does not grant authorization to deploy or publish.
