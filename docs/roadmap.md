# Roadmap

The roadmap turns the design into five implementation stages. All runtime
stages are `TODO`; the initial public release is complete only as guidance,
templates, and documentation. No dates or support promises are implied.

## Current release

### M0 — Public guidance and authoring resources

Status: `AVAILABLE_GUIDANCE` / `TEMPLATE`.

Deliverables:

- one self-contained skill with references and templates;
- lifecycle guidance covering idea through iteration, with phase context kept
  orthogonal to the four assessment modes;
- progressive product-planning templates for a brief, discovery plan, and
  product plan, including a direct path for small clear changes;
- coverage guidance for all sixteen baseline domains;
- public architecture, evidence, feature, quickstart, and roadmap documents;
- synthetic evidence examples that label every result as `NOT_RUN`; and
- public research and licensing boundaries.

Acceptance checks:

- a new contributor can find the skill and follow a PLAN_ONLY workflow;
- all ten lifecycle phases are named, nonlinear entry and iteration are
  explained, and phase context is not confused with mode or permission;
- planning depth scales from Direct to Brief to Full without making product
  ceremony mandatory for a small clear change;
- context-only idea planning can use `UNKNOWN` or reasoned `N/A` without
  inventing a repository, participant, demand, owner decision, or result;
- product artifacts preserve hypotheses, observations, proposals, decisions,
  unknowns, and superseded revisions as separate records;
- the four modes and four decisions have unambiguous meanings;
- templates connect requirements, controls, tasks, checks, evidence, findings,
  gates, acceptance, and decisions;
- no example claims a command, browser, provider, renderer, or runtime passed;
- no private source, artifact, identifier, credential, or local run result is
  distributed; and
- documents label future engine, CLI, host, adapter, and benchmark work as
  `PLANNED` or `NOT_RUN`.

## M1 — Core schema, integrity, and evaluator

Status: `TODO`. Dependency: M0 guidance and stable evidence vocabulary.

Tasks:

1. Define versioned typed entities for assessment, lifecycle phase and bounded
   phase span, subject, requirement,
   control, task, check definition, check run, gate, evidence, finding,
   unknown, acceptance, decision, and authorization.
2. Validate local IDs, typed references, dependency DAGs, extension fields, and
   status transitions.
3. Separate task completion from check outcome and retain retest history.
4. Preserve product artifact references, supersession, and lifecycle handoff
   fields without making them a release verdict or permission.
5. Verify path confinement, file existence, size/hash integrity, symlink policy,
   private pointers, and non-circular manifests.
6. Match evidence to control-specific source, artifact, environment, AI, UI,
   and time identities.
7. Implement a pure evaluator using selected proof sets and injected time.
8. Preserve migration aliases and report unmapped legacy fields without loss.

Acceptance checks:

- malformed, duplicate, dangling, stale, mismatched, and incomplete fixtures
  are rejected or remain unresolved for the documented reason;
- `DONE + NOT_RUN` is valid authoring state but cannot satisfy a runtime gate;
- a mandatory failure, missing proof, and conflicting retest produce distinct
  outcomes;
- all four decisions are deterministic for the same input;
- a technical decision never creates authorization; and
- tests use synthetic fixtures without network, provider, database, or source
  mutation.

## M2 — Router, runner, and resume state

Status: `TODO`. Dependency: M1 typed model and evaluator.

Tasks:

1. Build bounded discovery that records roots, include/exclude rules, file
   counts, unreadable paths, symlinks, submodules, and partial coverage.
2. Define a module registry with version, applicability, inputs, outputs,
   dependencies, resource estimate, permissions, and required gates.
3. Route selected details while retaining baseline coverage and explaining
   selected, skipped, conflicting, and unknown modules.
4. Plan typed tasks with preconditions, structured argv, expected results,
   evidence targets, owner, dependency predicates, timeout, and cleanup.
5. Enforce filesystem, process, network, credential, browser, tool, and upload
   capability boundaries at the host interface.
6. Store immutable events, checkpoints, generations, and partial evidence;
   support safe resume, quarantine, cancellation, budget cutoff, and cleanup.
7. Add `doctor`, `explain`, `status`, `resume`, `validate`, and `report` behavior
   only after their contracts and exit states are defined.

Acceptance checks:

- incomplete discovery cannot prove absence;
- a module conflict or dependency cycle is explicit and cannot select a winner
  silently;
- an unauthorized side effect does not occur and its state is recorded;
- a changed subject invalidates affected evidence and replans it;
- crash, replay, concurrent writer, corrupt state, timeout, and budget fixtures
  preserve a diagnosable ledger; and
- offline sample runs produce useful plans without fabricated results.

## M3 — Adapters, reports, and evidence export

Status: `TODO`. Dependency: M1 and M2 contracts.

Tasks:

1. Define adapter provenance, format versions, native-to-normalized status
   mapping, parser limits, and safe input boundaries.
2. Add fixture-backed importers for selected structured test/evaluation,
   security, and specification formats.
3. Require expected inventory, complete output, matching subject, and valid
   provenance before an imported result can support a control.
4. Generate offline indexes, scope/applicability views, checklists, WBS,
   findings, proof tables, UAT, decisions, and unknown registers from one model.
5. Generate applicable diagram descriptors and editable source with basis,
   source refs, render status, source hash, render hash, and semantic review.
6. Export immutable bundles with sensitivity, redaction, raw/private pointers,
   sanitized relations, and manifest validation.

Acceptance checks:

- unknown producer versions, malformed inputs, empty outputs, missing cases,
  parser errors, and incomplete suites cannot produce a false `PASS`;
- native output and normalized observations remain linked;
- rendered output, parser success, and semantic review are separate checks;
- HTML/report output escapes input and works offline;
- raw and redacted artifacts have distinct hashes and relations; and
- at least one renderer or producer is labelled supported only after exact
  qualification evidence exists.

## M4 — Packaging and conformance

Status: `TODO`. Dependency: M1–M3 and an exact host contract.

The revision-pinned public source comparison is a `REFERENCE` artifact for
documented capability coverage. It is separate from a controlled runtime
benchmark. No equal-task trial, effectiveness result, time saving, quality
result, or false-readiness measurement is claimed; those remain `NOT_RUN` until
the protocol has been executed with matched conditions.

Tasks:

1. Create small synthetic good/bad fixtures for API, browser, RAG, agent,
   training, and non-AI profiles with independent expected labels.
2. Implement negative conformance cases for integrity, identity/time,
   workflow, state, adapters, output provenance, redaction, and human
   acceptance.
3. Compare baseline and unified workflows only with equal task set, host/model,
   prompt, tool permission, seed, and time/token/cost budgets.
4. Measure valid-report time, clarification count, evidence completeness,
   false `READY`, finding precision/recall, cost, and resume success with clear
   denominators; record `UNKNOWN` or `NOT_RUN` when usage is unavailable.
5. Build a package containing only declared core, schemas, docs, resources,
   fixtures, and notices; test install, offline run, update, rollback, and
   uninstall in a disposable environment.
6. Reconcile source pins, file hashes, resource closure, license/notice scope,
   host requirements, and maturity before distribution.

Acceptance checks:

- independent labels include valid positive and negative cases;
- the source comparison and any runtime benchmark are clearly separated, with
  runtime effectiveness and false-readiness claims remaining `NOT_RUN` until
  matched trials exist;
- no false `READY` occurs on the required negative matrix;
- metrics distinguish false-ready decisions, false-positive findings, and
  unsupported or abstained cases;
- benchmark quality preserves exit/signal/status and mandatory evidence
  anchors before any savings claim;
- package closure contains no private runs, credentials, source tree, cache,
  or undeclared resource; and
- host support is advertised only for the exact qualified package and host.

## M5 — Curated capability and context extension

Status: `TODO`. Dependency: M1–M4 and a reviewed capability decision record.

Tasks:

1. Select a minimal capability set from public research using applicability,
   value, maintenance, host capability, license, and resource-closure checks.
2. Extend the registry with maturity, entrypoint, recursive resources, hashes,
   source pin/blob, license/notice, permissions, formats, limits, and
   qualification IDs.
3. Enforce one canonical router, one primary design module per applicable UI
   scope, and at most one graph provider.
4. Implement a loss-aware context broker with raw retrieval, omitted counters,
   ordered loss manifest, status fidelity, and freshness metadata.
5. Add direct-source fallback for stale, partial, or unavailable graph views.
6. Qualify a security importer and a first-party design-review importer with
   synthetic error, clean, cache, subject-mismatch, accessibility, and
   provenance fixtures.
7. Re-run package conformance and benchmark checks whenever a pin, resource,
   permission, transform, provider, or license changes.

Acceptance checks:

- unknown pins, living-source mixes, unknown license scope, undeclared nested
  resources, changed hashes, and missing host capabilities keep modules from
  being called supported;
- raw evidence remains immutable and retrievable after compaction;
- stale graph data never proves absence and direct fallback remains visible;
- scanner zero-count, cache, missing-output, and error cases map distinctly;
- UI observations do not create human acceptance or a visual quality verdict;
- unauthorized egress, upload, comment, or write is blocked and recorded; and
- selected modules pass the exact M4 conformance and package qualification
  required for their claimed maturity.

## Dependencies and stop conditions

The stages are deliberately sequential at their contract boundaries. Stop a
dependent stage when the prior model, identity, status, resource closure, or
host contract cannot be verified. Preserve an `UNKNOWN` or `NOT_RUN` record and
continue independent documentation work where possible.

Do not weaken a mandatory gate to make a fixture pass, merge a historical run
with a new subject, copy upstream material with unresolved license scope, or
claim support from a fake host. A provider or transform update is a supply
chain change and requires requalification of the affected package and evidence.

## Maintenance triggers

Review the roadmap when:

- a normative reference or required policy changes;
- the schema, policy, status mapping, or context transform changes;
- a host, tool, provider, graph implementation, or renderer is added or
  upgraded;
- a resource pin, license, notice, permission, or file hash changes;
- a new product profile introduces a domain or identity dimension; or
- a benchmark, conformance fixture, or security review reveals a regression.

Historical records remain immutable. New runs and new qualification evidence
must carry their own identities and timestamps.
