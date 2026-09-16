# e2e

`e2e` is a portable product-lifecycle and readiness skill for teams shaping an
idea, learning what to build, delivering a change, operating it, and deciding
whether a release is ready for its intended users and operators. It gives a
user one clear entrypoint, a small set of assessment modes, and a canonical
place for product artifacts, requirements, observations, evidence, findings,
and decisions.

The initial release is usable as guidance and as a set of templates. It does
not ship an automation engine, a working `e2e` command, a package published to a
registry, or host adapters. Those are planned capabilities and are labelled as
such throughout this repository.

## Why this exists

Product and readiness work often fragments across idea notes, research plans,
design reviews, test runners, browser tools, security scanners, incident
checklists, and AI evaluation prompts. A green command or completed checklist
can be mistaken for proof that a product is useful or safe to release.

`e2e` provides a common contract for the work around those tools:

- frame problems, users or affected actors, hypotheses, alternatives, outcomes,
  constraints, and non-goals;
- plan discovery without presenting proposed research as validation;
- discover what applies to the product and its current goal;
- turn applicable controls into traceable tasks and checks;
- preserve the identity of the source, artifact, environment, and procedure;
- keep raw observations available while producing useful compact views;
- distinguish a task being complete from its check actually passing;
- select an explicit proof set for a decision; and
- keep technical readiness separate from product-learning decisions and human
  authorization to release.

This is a workflow and evidence boundary. It does not make an application
secure or replace domain owners, independent review, or existing test/release
systems.

## Who it is for

The repository is for product managers and sponsors, researchers, designers and
content or accessibility reviewers, engineers, QA/UAT reviewers, security and
privacy reviewers, service owners and SREs, AI quality/data owners, governance
roles, and maintainers building a host integration around the same evidence
contract.

Applicability is decided per assessment, with a reason and reassessment trigger
for excluded domains.

## Current maturity

| Area | Current status | What that means |
| --- | --- | --- |
| Portable prompt and workflow | **AVAILABLE_GUIDANCE** | The skill explains intent inference, routing, authorization boundaries, evidence, and decisions. |
| Lifecycle method | **AVAILABLE_GUIDANCE** | The lifecycle reference covers idea, discovery, product planning, design, build, review, QA, release, operate, and iterate with nonlinear entry. |
| Reference workflow | **AVAILABLE_GUIDANCE** | The workflow describes lifecycle context, progressive planning, collection, review, and release decision steps. |
| Checklists and report templates | **TEMPLATE** | Templates can be copied into an authorized run directory and filled by a human or host. |
| Product-planning templates | **TEMPLATE** | Brief, discovery-plan, and product-plan assets record intent and handoffs; they do not perform research or approve a product. |
| Synthetic evidence example | **TEMPLATE** | The example shows shape and status handling; all results are `NOT_RUN`. |
| Public research register | **REFERENCE** | Public sources are recorded for selective design lessons, not vendored as executable code. |
| Documentary source comparison | **REFERENCE** | A revision-pinned public-source comparison records documented capabilities and review limits; it is not a runtime benchmark. |
| Typed core model and evaluator | **PLANNED** | A future implementation will validate references, identity, freshness, proof sets, and decisions. |
| Router, runner, and resume state | **PLANNED** | A future implementation will plan modules and persist immutable run events. |
| Tool and document adapters | **PLANNED** | A future implementation may import qualified producer formats without making them release authorities. |
| CLI surface | **PLANNED** | A future host-facing command needs a versioned contract and qualification; no `e2e` command ships now. |
| Host plugin or package | **PLANNED** | Host compatibility requires a separately tested adapter and package qualification. |
| Benchmarks and support claims | **NOT_RUN** | No runtime, savings, certification, or cross-host support claim is made by this release. |

## Quickstart

The current release can be used anywhere a host can read a Markdown skill or
prompt. It does not require an install step or a provider account. Product
planning can start from a user request or other context without a repository or
artifact; record the missing identity as `UNKNOWN` with a reason.

```bash
git clone https://github.com/vuckuola619/e2e.git
cd e2e
sed -n '1,240p' skills/e2e/SKILL.md
```

Start by giving a capable host the skill at
[`skills/e2e/SKILL.md`](skills/e2e/SKILL.md), an authorized target, a concrete
goal, and a separate output run directory when the work produces one. A
readiness request looks like this:

```text
Use the e2e skill from skills/e2e/SKILL.md.
Goal: assess whether the authorized target is ready for the documented launch journey.
Target: /path/to/the-authorized-target  # replace with the actual target path
Run directory: /path/to/separate-authorized-run  # replace with an output path
Mode: PLAN_ONLY  # omit only when intent and existing authorization are clear
Scope: source, tests, configuration, documentation, and the release checklist.
Write proposed outputs only to the separate run directory named above.
```

Replace paths and scope with actual values. If mode is omitted, infer it from
intent and existing authorization. Begin with `PLAN_ONLY` for applicability
and a WBS; an authorized change may infer `IMPLEMENT_AND_VERIFY` without
repeating permission. `READ_ONLY_AUDIT` preserves the target tree.

For an idea or product-planning request, a repository is optional:

```text
Use the e2e skill from skills/e2e/SKILL.md.
Goal: decide what to learn before considering a small workflow improvement.
Phase: IDEA
Phase span: IDEA, DISCOVERY
Mode: PLAN_ONLY
Planning depth: Brief
Context: [paste the request, constraints, and any observed signals here]
Target: UNKNOWN — no repository or artifact exists yet.
Output: a product brief, proposed discovery questions, hypotheses, alternatives,
and a next-step recommendation. Mark proposed research NOT_RUN.
```

Choose `Direct` for a clear small existing-project change, `Brief` when product
intent or uncertainty needs a durable brief, and `Full` for multi-team or
high-impact work that needs a product plan and applicable design and assurance
artifacts. The planning depth does not add a mode or a release verdict.

The templates under [`skills/e2e/assets/`](skills/e2e/assets/) and guidance under
[`skills/e2e/references/`](skills/e2e/references/) show the expected shape.
Replace placeholders with observed information or `UNKNOWN`; never turn a
planned command, example screenshot, or empty result into a passing claim.

## Lifecycle phases vs assessment modes

The lifecycle axis locates work in the product journey. The mode axis describes
the action allowed for this request. Select exactly one mode, record one current
phase and an optional bounded span, and keep the axes separate. A phase never
grants permission, creates evidence, or decides release readiness.

| Lifecycle context | Mode example | Meaning |
| --- | --- | --- |
| `IDEA` | `PLAN_ONLY` | Frame an opportunity and its unknowns from supplied context. |
| `DISCOVERY` | `PLAN_ONLY` | Plan research or record proposed questions; execution is not implied. |
| `PRODUCT_PLANNING` | `PLAN_ONLY` | Define outcomes, scope, tradeoffs, dependencies, and measures. |
| `DESIGN` | `PLAN_ONLY` or `READ_ONLY_AUDIT` | Define or inspect behavior, interaction, architecture, and quality boundaries. |
| `BUILD` | `IMPLEMENT_AND_VERIFY` | Apply an already-authorized change and verify it. |
| `REVIEW` | `READ_ONLY_AUDIT` | Inspect a design, change, or evidence bundle without mutating the target. |
| `QA` | `IMPLEMENT_AND_VERIFY` or `READ_ONLY_AUDIT` | Run or review authorized checks and preserve their status. |
| `RELEASE` | `RELEASE_REVIEW` | Evaluate the exact candidate and proof set; rollout remains separately authorized. |
| `OPERATE` | `READ_ONLY_AUDIT` | Inspect operational signals, incidents, support, and recovery evidence. |
| `ITERATE` | `PLAN_ONLY` | Route learning to any earlier phase and create a new revision. |

The table gives examples, not a mandatory sequence. An existing product can
enter at `OPERATE`; a bug can enter at `BUILD`, `REVIEW`, or `QA`; and a clear
small fix can use the direct task/check path without a brief, research study,
PRD, or all ten phases. Discovery outcomes such as `continue`, `reframe`,
`pause`, and `stop` are product owner decisions. A recommendation to `validate`,
`pivot`, or `build` remains a proposal until an owner decides; these are
separate from `READY`, `CONDITIONALLY READY`, `NOT READY`, `UNDETERMINED`, and
authorization.

## Assessment modes

There are exactly four assessment modes. The user's explicit mode wins. If no
mode is given, infer intent and existing authorization from the request and
record the selected mode. A request to write a prompt, plan, checklist, or
documentation is authoring work and selects `PLAN_ONLY`.

| Mode | Purpose | Allowed result |
| --- | --- | --- |
| `PLAN_ONLY` | Establish scope, applicability, requirements, tasks, checks, dependencies, and evidence targets. Explicitly authorized read-only reconnaissance may ground the plan. | No implementation or runtime validation run is implied. |
| `READ_ONLY_AUDIT` | Inspect an authorized target and collect non-mutating observations. | An audit record with evidence, limitations, and unresolved gaps. |
| `IMPLEMENT_AND_VERIFY` | Apply an authorized change, then run the checks needed to verify that change. | A traceable change and verification record; authorization still remains separate. |
| `RELEASE_REVIEW` | Evaluate the exact candidate artifact and evidence bundle for its release scope. | A decision with its proof set, obligations, and human acceptance state. |

Mode selection does not grant permissions. Carry existing authorization through
the workflow when scope still matches, record its limits, and treat a missing
permission or capability as an explicit gap.

## Coverage model

The baseline keeps all sixteen domains visible. Details can be loaded
selectively when a domain is applicable or discovery must resolve an unknown;
the baseline register remains complete so omitted guidance stays visible.

| # | Domain | Typical questions |
| --- | --- | --- |
| 1 | Scope and identity | Is the target, candidate, environment, authorization, and identity boundary explicit? |
| 2 | Requirements and design | Is intended behavior traceable to a coherent design and acceptance boundary? |
| 3 | Source and supply chain | Are source changes, dependencies, build inputs, provenance, and licenses controlled? |
| 4 | Application security | Are authentication, authorization, input, secrets, dependencies, and data boundaries verified? |
| 5 | Data, privacy, and migration | Are retention, deletion, tenancy, migration effects, audit access, and recovery obligations addressed? |
| 6 | QA/QC | Do tests cover critical paths, negative behavior, integration, regression, and known risk? |
| 7 | CI/CD | Are build, checks, promotion, environment separation, and rollback controls evidenced? |
| 8 | UI/UX/a11y | Do states, journeys, responsive behavior, keyboard use, semantics, and feedback work? |
| 9 | SRE/PRR | Are ownership, SLOs, capacity, alerts, runbooks, incidents, and operational readiness covered? |
| 10 | Recovery/continuity | Are backup, restore, failover, rollback, continuity, and recovery exercises evidenced? |
| 11 | AI-assisted | Are generated changes bounded, reviewed, reproducible, and free of untrusted instruction paths? |
| 12 | AI runtime/RAG | Are model, prompt, corpus, retrieval, claims, privacy, safety, cost, and failure behavior evaluated? |
| 13 | Agent/tool/MCP | Are tools allowlisted, authorized per action, bounded in depth and spend, and auditable? |
| 14 | Training | Are data provenance, consent, leakage, poisoning, reproducibility, evaluation, and rollback covered? |
| 15 | AI eval | Are representative holdouts, rubrics, graders, variance, slices, and regression thresholds defined? |
| 16 | UAT/governance | Do business roles, tenants, support, legal, security, and residual-risk owners accept the result? |

The exact control list belongs to the assessment and its selected policy. These
domains are a coverage contract, not a certification or a guarantee that every
question applies.

## Core design

The intended architecture has one user entrypoint and one canonical evidence
and decision authority. Skills, checklists, importers, graph views, browser
collectors, scanners, and test runners are inputs to that authority. They do
not publish a competing release verdict.

```text
user goal + existing authorization
        -> mode and scope inference
        -> applicability inventory and selected modules
        -> typed plan and controlled collection
        -> immutable observations and evidence references
        -> review, findings, acceptance, and proof-set selection
        -> technical decision (authorization remains separate)
```

The future typed core separates these concepts:

| Concept | Meaning |
| --- | --- |
| Requirement / control | What must be true and how it is checked. |
| Task | Work to perform, with owner, dependencies, expected result, and cleanup. |
| Check run | One immutable attempt tied to a definition, subject, and procedure. |
| Observation | What a collector or reviewer saw, including native status and limitations. |
| Evidence | A traceable artifact or attestation tied to source, time, identity, and scope. |
| Finding / unknown | A material mismatch, unresolved question, or missing proof with owner and next step. |
| Acceptance | Identified human and role, or a documented policy disposition, for the applicable obligation. |
| Decision | A deterministic interpretation of the selected valid proof set. |
| Authorization | Permission to take a side-effecting action; never created by a positive decision. |

Failed and passing retests both remain in history. The evaluator selects a
proof set using identity, completeness, relevance, freshness, policy version,
and acceptance; it does not choose the newest or most flattering result alone.

## Decision semantics

The initial decision contract has four outcomes:

| Decision | Meaning |
| --- | --- |
| `READY` | Every applicable mandatory gate has valid, sufficiently fresh proof, required human acceptance is complete, and no release blocker remains. |
| `CONDITIONALLY READY` | Mandatory gates still pass; only bounded, nonblocking obligations remain, each with an owner, deadline, monitoring plan, and human acceptance. |
| `NOT READY` | A mandatory gate or release blocker is proven to fail, or a material risk lacks an accepted safe path. |
| `UNDETERMINED` | The available evidence, identity, access, or owner decision is insufficient to distinguish readiness. |

`READY` never authorizes deployment. A mandatory failure takes precedence over
missing evidence; missing or stale evidence without a proven failure remains
`UNDETERMINED`. Exceptions cannot downgrade mandatory controls. Each decision
lists its `GATE -> EVIDENCE` proof set and limitations.

## Evidence and identity

Evidence is useful only when a reviewer can tell what was observed, where it
came from, and which candidate it describes. Future records and current
templates therefore capture source/artifact/configuration identity, applicable
model/prompt/corpus identity, procedure and status, separate observation and
report times, sensitivity/redaction, reviewers, limitations, supersession, and
raw private pointers for reduced views.

Hashes establish byte identity for the material that was checked. They do not
prove that the content is true, that an actor is trustworthy, or that a scan
covered an entire system. A timestamp added during report generation does not
refresh an old observation.

## Repository tree

This is the initial public tree; the runtime engine is absent and its planned
structure appears next.

```text
e2e/
├── README.md
├── CONTRIBUTING.md
├── SECURITY.md
├── LICENSE
├── AGENTS.md
├── CHANGELOG.md
├── docs/
│   ├── quickstart.md
│   ├── architecture.md
│   ├── features.md
│   ├── evidence.md
│   ├── roadmap.md
│   ├── baselines.md
│   ├── ecosystem.md
│   ├── comparison.md
│   └── benchmark-protocol.md
├── research/
│   ├── upstreams.json
│   └── comparison-2026-09-16.json
└── skills/
    └── e2e/
        ├── SKILL.md
        ├── references/
        │   ├── workflow.md
        │   ├── lifecycle.md
        │   ├── controls.md
        │   └── evidence.md
        └── assets/
            ├── product-brief.md
            ├── discovery-plan.md
            ├── product-plan.md
            ├── checklist.md
            ├── task.md
            ├── findings.md
            ├── run-index.md
            └── evidence-manifest.example.json
```

Only the skill, references, and templates are intended for host copying. The
repository contains no private runs, raw application evidence, credentials,
local settings, or upstream source trees.

## Proposed core tree

The following is a design target for later runtime work, not a promise that
these files exist in the initial release.

```text
core/                         # PLANNED
├── model/                    # typed assessment, subject, control, task, run, evidence
├── validation/               # schema, references, DAG, integrity, freshness
├── policy/                   # proof-set evaluation and four decisions
├── discovery/                # bounded inventory and applicability facts
├── router/                   # module selection and conflict handling
├── runner/                   # argv, capability, budget, timeout, and cleanup boundary
├── state/                    # immutable event log, checkpoints, resume, quarantine
├── adapters/                 # qualified producer importers with native results retained
├── report/                   # offline views, indexes, and decision pack
└── export/                   # manifest, redaction, and package validation
schemas/                      # PLANNED versioned contracts
modules/                      # PLANNED selected capabilities, with resource closure
tests/                        # PLANNED synthetic conformance fixtures
```

Host sandboxing, browser execution, network controls, and model providers are
recorded capabilities, never inferred from a module name.

## Selective integration strategy

The first useful run should carry a small qualified set. The router keeps the
full baseline visible while loading detail only when facts, applicability, or
an unresolved unknown calls for it.

- Keep one canonical router and one decision evaluator.
- Use existing project tools when they already produce trustworthy evidence.
- Add one importer at a time with a versioned format fixture and explicit
  status mapping.
- Choose at most one primary design-review provider for an applicable UI scope.
- Choose at most one graph provider; preserve direct source inspection as a
  fallback and treat graph absence as `UNKNOWN`, not proof of absence.
- Treat style, planning, context, and compression helpers as advisory inputs.
- Require resource closure, provenance, permissions, license status, and host
  capability before calling a module qualified.
- Keep network, credentials, comments, uploads, commits, and writes behind the
  selected mode and the user's authorization.

Public references are research inputs, not copied project content; their
licenses do not automatically apply here or to another dependency. See
[`docs/ecosystem.md`](docs/ecosystem.md) for the research register.

## Documentation map

| Document | Use it for |
| --- | --- |
| [`docs/quickstart.md`](docs/quickstart.md) | A first PLAN_ONLY or audit workflow and output expectations. |
| [`docs/architecture.md`](docs/architecture.md) | The canonical model, boundaries, flow, and future runtime shape. |
| [`docs/features.md`](docs/features.md) | Available guidance, templates, planned runtime features, and non-goals. |
| [`docs/evidence.md`](docs/evidence.md) | Evidence identity, statuses, proof sets, redaction, and decision rules. |
| [`docs/roadmap.md`](docs/roadmap.md) | Actionable runtime milestones and acceptance checks. |
| [`docs/baselines.md`](docs/baselines.md) | Normative and reference baselines selected for future assessments. |
| [`docs/ecosystem.md`](docs/ecosystem.md) | Public upstream observations and reuse dispositions. |
| [`docs/comparison.md`](docs/comparison.md) | Revision-pinned documentary comparison; runtime results remain `NOT_RUN`. |
| [`docs/benchmark-protocol.md`](docs/benchmark-protocol.md) | Criteria and protocol for a future controlled comparison. |
| [`research/comparison-2026-09-16.json`](research/comparison-2026-09-16.json) | Public comparison snapshot metadata and review scope. |
| [`skills/e2e/references/lifecycle.md`](skills/e2e/references/lifecycle.md) | Lifecycle phases, progressive depth, handoffs, truth rules, and iteration. |
| [`skills/e2e/assets/product-brief.md`](skills/e2e/assets/product-brief.md) | Brief template for product intent, hypotheses, outcomes, and boundaries. |
| [`skills/e2e/assets/discovery-plan.md`](skills/e2e/assets/discovery-plan.md) | Discovery template for proposed research, evidence, findings, and dispositions. |
| [`skills/e2e/assets/product-plan.md`](skills/e2e/assets/product-plan.md) | Product plan template for prioritized scope, requirements, delivery, release, operations, and measurement. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | How to improve guidance, templates, and future runtime work. |
| [`SECURITY.md`](SECURITY.md) | Safe handling and reporting of security issues. |

## Limitations

The initial release does not run commands, open browsers, call providers,
inspect live systems, validate artifacts, or grant release authorization. Its
application and runtime evidence examples are synthetic and `NOT_RUN`; the
public source comparison is documented separately and does not establish
effectiveness. It makes no certification, enterprise readiness, benchmark, host
support, security coverage, or product-correctness claim.

A future engine can only make claims supported by its exact package, host,
version, source, test fixture, and qualification evidence. A successful parser,
render, checklist, or model score will remain distinct from semantic review and
release acceptance.

## Contributing and license

Start with [`CONTRIBUTING.md`](CONTRIBUTING.md), keep changes focused, and
preserve the public-data boundary. New examples should be synthetic, clearly
labelled, and free of secrets, personal data, private identifiers, and
unverified claims.

Original material is MIT; see [`LICENSE`](LICENSE). External links and research observations retain their own licenses and terms. No external source is vendored by this initial release.
