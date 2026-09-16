# Features

The feature list is split by maturity so readers can see what is usable in the
initial release and what still requires implementation and qualification.

## Available guidance and templates

| Feature | Status | Description |
| --- | --- | --- |
| One user entrypoint | **AVAILABLE_GUIDANCE** | Start from a goal, target, constraints, mode, and existing authorization. |
| Four-mode workflow | **AVAILABLE_GUIDANCE** | Use `PLAN_ONLY`, `READ_ONLY_AUDIT`, `IMPLEMENT_AND_VERIFY`, or `RELEASE_REVIEW`. |
| Applicability ledger | **TEMPLATE** | Keep all sixteen domains visible and record applicability, reason, owner, and trigger. |
| Work breakdown structure | **TEMPLATE** | Break applicable controls into atomic tasks with dependencies and evidence targets. |
| Evidence contract | **AVAILABLE_GUIDANCE** | Bind observations to subject, procedure, time, identity, status, and limitations. |
| Proof-set decisions | **AVAILABLE_GUIDANCE** | Explain how valid evidence supports `READY`, `CONDITIONALLY READY`, `NOT READY`, or `UNDETERMINED`. |
| Finding and unknown register | **TEMPLATE** | Track evidence anchors, owners, dispositions, deadlines, and discovery paths. |
| Run index | **TEMPLATE** | Point reviewers to scope, artifacts, checks, findings, acceptance, and decisions. |
| Synthetic manifest | **TEMPLATE** | Demonstrate schema shape without pretending that example results were executed. |
| Selective integration strategy | **AVAILABLE_GUIDANCE** | Keep baseline coverage complete while loading specialist modules only when needed. |
| Public ecosystem research | **REFERENCE** | Record public observations and uncertainty without vendoring upstream content. |

Use the skill and its resources as a portable starting point. A host still
performs the work, applies its own authorization model, and supplies any
collector or sandbox. Availability of a document is not availability of a
runtime capability.

## Planned runtime features

These features are design targets. They are not implemented by the initial
release and must not be described as working commands or integrations.

### Typed core and validation

The core is planned to validate versioned entities, local IDs, references,
dependency graphs, evidence integrity, identity requirements, and state
transitions. It should reject duplicate IDs, dangling references, path escapes,
missing artifacts, hash mismatches, and positive statuses without sufficient
proof.

### Router, runner, and resume

The router is planned to select modules using applicability, mode, subject,
host capabilities, permissions, maturity, freshness, and budget. The runner is
planned to use structured arguments, bounded resources, explicit capabilities,
timeouts, cancellation, and cleanup. The state layer is planned to replay
immutable events and invalidate evidence when the subject changes.

### Adapters and report generation

Qualified adapters may import structured test results, evaluation exports,
security observations, and specification artifacts. Each adapter must retain
the native result, version, expected coverage, diagnostics, and provenance. A
report generator may create offline indexes and views from the same model. It
must not turn a completed document or a renderer success into a runtime pass.

### CLI, plugin, and host adapters

The command surface, plugin format, and host adapters are `PLANNED`. A future
release must define their input/output and permission contracts, qualify an
exact host and package, and preserve the same canonical model. The initial
release has no `e2e` command and does not claim compatibility with any host.

### Resource closure and packaging

Future packages must declare every supporting reference, schema, template,
script, binary, and linked document required by a module. Hashes, source pins,
license/notice status, host capabilities, and qualification evidence must be
checked before a module is called supported.

### Context broker and graph fallback

The planned context broker will keep raw evidence retrievable while producing
loss-aware compact views. A single qualified local graph provider may be used
as an accelerator. Direct source confirmation remains available, and stale or
partial graph data produces a visible limitation.

### Design and security observations

First-party design review can eventually normalize viewport, route, state,
theme, accessibility, interaction, and visual observations. A security
importer can eventually normalize scanner output and cache provenance. Both
remain observation producers; the core evaluator retains decision ownership.

## Coverage by domain

The baseline makes these domains inspectable. The examples are prompts for
applicability and evidence planning, not a claim that every project needs all
of them.

| Domain | Example coverage |
| --- | --- |
| Scope and identity | Target, candidate, environment, authorization, and identity dimensions. |
| Requirements and design | Intended behavior, architecture boundaries, traceability, and change impact. |
| Source and supply chain | Source changes, dependencies, build inputs, provenance, licenses, and notices. |
| Application security | Authentication, authorization, input handling, injection, secrets, dependencies, and audit trails. |
| Data, privacy, and migration | Collection, retention, deletion, tenant isolation, migration effects, and access review. |
| QA/QC | Unit, contract, integration, end-to-end, negative, regression, concurrency, and flaky-test handling. |
| CI/CD | Reproducible build, protected checks, artifact identity, promotion, rollout, and rollback. |
| UI/UX/a11y | Loading, empty, error, keyboard, semantics, contrast, responsive states, and manual journey review. |
| SRE/PRR | Owner, SLI/SLO, capacity, saturation, retries, graceful degradation, alerts, and incident practice. |
| Recovery/continuity | Backup, restore, failover, rollback, disaster recovery, and recovery evidence. |
| AI-assisted | Bounded instructions, minimum access, source review, dependency provenance, and reproducible verification. |
| AI runtime/RAG | Intended use, model/prompt/corpus identity, retrieval support, safety, privacy, latency, cost, and failure behavior. |
| Agent/tool/MCP | Allowlist, per-tool authorization, parameter validation, side-effect preview, limits, memory, and audit chain. |
| Training | Dataset provenance, consent, leakage, poisoning, reproducibility, evaluation, and rollback. |
| AI eval | Holdout data, rubric, ground truth, grader, variance, slices, regression, and cost/latency measures. |
| UAT/governance | Business scenarios, role/tenant effects, support handoff, legal/privacy/security decisions, and named acceptance. |

## Safety properties

The workflow is designed to preserve these distinctions:

- a task marked complete can still have a check marked `NOT_RUN`;
- a command error is distinct from a tested negative result;
- a missing or stale proof is distinct from a proven failure;
- a score is distinct from the claims its component checks support;
- a source-derived or proposed diagram is distinct from observed topology;
- a compact view is distinct from the raw artifact it references;
- a technical decision is distinct from human acceptance; and
- an accepted authorization is distinct from a technical `READY` decision.

These are contract goals for the planned core and authoring rules for the
current guidance. They are not claims that the runtime has already enforced
them.

## Non-goals and deferred choices

The initial release intentionally leaves these choices open:

- the first production host and its plugin format;
- the exact CLI name, packaging metadata, and installation route;
- which browser, scanner, model, or graph provider receives qualification;
- universal support across languages, frameworks, clouds, or providers;
- an aggregate “readiness score” that hides mandatory controls;
- automatic deployment, comments, uploads, commits, or external messaging; and
- claims about token reduction, benchmark performance, or certification.

Each choice needs a decision record and evidence at the time it is implemented.

## How to read the status labels

`AVAILABLE_GUIDANCE` means a human or host can use the documented method.
`TEMPLATE` means the structure is ready to copy and fill with real facts.
`REFERENCE` means research material informs design but is not a capability.
`PLANNED` means implementation is future work. `NOT_RUN` means no qualifying
execution has occurred for the claim. These labels should survive export and
review.
