# Architecture

`e2e` is designed around one user entrypoint and one canonical evidence and
decision authority. The initial repository contains the contract and guidance;
the runtime layers described here are planned.

## Design goals

- Make the requested goal and existing authorization the starting point.
- Keep all applicable coverage visible while loading detailed guidance on
  demand.
- Tie every meaningful claim to a subject, procedure, time, and evidence.
- Preserve history and make retests, supersession, and uncertainty explicit.
- Keep task completion, check status, technical readiness, and authorization
  as separate concepts.
- Work offline when the selected procedure permits it.
- Make output useful to a human reviewer without discarding raw proof.

## Non-goals

The project is not a universal scanner, a replacement for every test runner, a
security certification, a deployment system, or a promise that a model can
sign off a release. It does not infer that an empty report means a clean
system, that a hash proves truth, or that a host's capability exists because a
module declares it.

## One authority, many inputs

The workflow accepts guidance and observations from several sources, but only
one typed model owns the traceability and decision path.

| Layer | Responsibility | Authority limit |
| --- | --- | --- |
| User entrypoint | Receive goal, target, constraints, and existing authorization. | Does not grant permissions or create evidence. |
| Intent and mode resolver | Select one of the four modes and record why. | Explicit user mode wins; it cannot widen scope. |
| Applicability inventory | Record observed facts, skipped areas, and unknowns. | Incomplete discovery cannot prove global absence. |
| Module router | Select compatible guidance, collectors, and importers. | Must respect mode, subject, host capability, maturity, and permission. |
| Planner | Create typed tasks, dependencies, expected results, and evidence targets. | Unknown commands become discovery work. |
| Runner or host | Execute an authorized procedure and capture native output. | Must enforce the host's available boundary and report gaps. |
| Adapter | Parse a qualified producer format into observations. | Never changes a native error into a release pass. |
| Context broker | Select or compact material for a consumer. | Must retain raw pointers, status, and a complete loss manifest. |
| Evidence store | Preserve immutable artifacts and identity metadata. | Does not authenticate claims merely through hashing. |
| Reviewer | Validate semantics, findings, and human acceptance. | A reviewer acts within the documented scope and role. |
| Evaluator | Apply policy to a selected proof set. | Produces a technical decision; never grants release authorization. |

This boundary prevents an imported score, a completed task checkbox, or an
advisory skill from silently becoming the release authority.

## Conceptual flow

```text
goal and authorization
  -> mode and scope
  -> inventory and applicability
  -> route compatible modules
  -> plan typed tasks and gates
  -> run authorized procedures
  -> retain native observations and immutable artifacts
  -> review findings, unknowns, and acceptance
  -> select valid proof set
  -> evaluate decision for the exact subject
```

The flow can pause after planning, after discovery, or after a check. A resume
operation must recheck the subject and all identity dimensions needed by the
affected controls. It may preserve history while invalidating stale evidence;
it must not treat a changed subject as the same candidate.

### Proposed design illustration

The following Mermaid flow is `PROPOSED` and is a design illustration only. It
is not a runtime observation, deployment topology, or evidence of an
implemented engine. The preceding text flow is the accessible summary.

```mermaid
flowchart LR
    A[Goal + existing authorization] --> B[Mode and scope]
    B --> C[Applicability inventory]
    C --> D[Selected modules]
    D --> E[Typed plan and gates]
    E --> F[Authorized procedures]
    F --> G[Immutable observations and evidence]
    G --> H[Review findings and acceptance]
    H --> I[Proof-set evaluation]
    I --> J[Technical decision]
    J -. authorization remains separate .-> K[Side effect permission]
```

## Typed model

The future core separates these records so that each can be validated and
reviewed independently:

| Record | Required meaning |
| --- | --- |
| Assessment | Scope, goal, mode, phase, policy, and top-level subject relation. |
| Subject | Source revision, dirty manifest, artifact, environment, and applicable identity dimensions. |
| Requirement | Desired behavior or obligation with provenance and applicability. |
| Control | A checkable statement, priority, method, required identity, and mandatory-gate relation. |
| Task | One unit of work with owner, precondition, dependency predicate, procedure, and cleanup. |
| Check definition | Versioned expected procedure and result semantics. |
| Check run | One immutable attempt, including native status, output references, and subject identity. |
| Observation | Structured result and limitation from a collector, importer, or reviewer. |
| Evidence | Artifact or attestation bound to a check, source, time, identity, and sensitivity policy. |
| Finding | A confirmed or candidate mismatch with evidence anchors, owner, and disposition. |
| Unknown | A bounded unresolved question with reason, owner, discovery task, and review trigger. |
| Acceptance | Identified human and role, or documented policy disposition, with scope, time, and conditions. |
| Gate | A policy boundary selecting required checks and proof conditions. |
| Decision | One of the four technical outcomes, with proof set and limitations. |
| Authorization | A separate grant for a side effect, with scope and expiry where applicable. |

IDs are local to an assessment. A framework ID may be mapped only after the
official source and version have been verified; a mapping describes relevance,
not certification.

## Identity and freshness

Evidence reuse is control-specific. The evaluator should require only the
identity dimensions that the selected control declares, for example:

- source revision and dirty file manifest for source-sensitive checks;
- build or image digest for an artifact check;
- configuration and environment fingerprint for operational behavior;
- model, prompt, corpus, and grader identity for an AI evaluation; and
- browser, device, route, viewport, theme, and state for a UI observation.

Every observation has an observation time separate from collection and report
times. Expiration, an invalidator, a changed identity, or an incomplete scope
can make evidence insufficient without deleting its historical record.

## Routing and capabilities

The proposed registry describes each module's role, version, resource closure,
supported formats, required identity, host capabilities, permissions,
side-effects, budget estimate, maturity, and qualification evidence.

Routing considers applicability, mode, subject, available host capabilities,
permissions, freshness needs, and policy. It keeps baseline probes visible and
loads specialist details only when needed. Two modules that claim the same
primary role or compete for the same writer are a conflict that needs an
explicit disposition.

The initial strategy is deliberately small:

- one canonical router and evaluator;
- existing project tools where their output can be verified;
- one qualified primary design-review provider for an applicable UI scope;
- at most one graph provider, with direct-source fallback; and
- advisory modules that can inform a review but cannot emit a verdict.

Unknown provider versions, unresolved licenses, missing resources, and missing
host capabilities keep a module unavailable or experimental. A research URL is
not an executable registry entry.

## Execution boundary

If a future host executes a procedure, the runner contract should receive
structured arguments, a confined working directory, an environment allowlist,
timeout, output limit, budget, target identity, and granted capabilities. It
must not interpolate untrusted repository text into a shell command.

Capabilities are separate from permissions:

| Capability | Example question |
| --- | --- |
| Filesystem read/write | Which exact paths may be read or written? |
| Process execution | Which procedure and executable are authorized? |
| Network | Is egress needed, to which scope, and for what reason? |
| Credentials | Which identity may be used, and can the value enter evidence? |
| Browser or device | Which route, account, viewport, and side effects are allowed? |
| Tool, connector, or MCP call | What schema, resource, recipient, and action boundary applies? |
| Commit, comment, upload, or deploy | Has the user explicitly authorized this external effect? |

The host enforces these boundaries. A Python subprocess or a prompt saying
“ignore malicious input” is not a sandbox.

## State, resume, and concurrency

The planned state layer uses immutable events for plan creation, collection,
review, and decision. A materialized view may be rebuilt from those events.
Writers use atomic writes and a generation or lock check. Workers cannot write a
final verdict directly.

Resume checks source and dirty state, artifact and configuration identity,
policy and schema versions, module/resource versions, and the dimensions
required by the controls being resumed. If they change, the run retains prior
history, records invalidation, and replans affected work. Corrupt state is
quarantined for diagnosis; it is not merged silently with a new run.

## Context and graph views

Context compaction is a consumer convenience. Raw stdout and stderr, stream
ordering where available, exit code, signal, timeout, native status, and
diagnostics remain separately addressable. A compact view includes selected raw
IDs and hashes, selection query, omitted counts, loss reasons, transform
version, freshness, and limitations.

A graph can accelerate retrieval but cannot prove that a claim is absent. The
graph record must include corpus and source identity, parser/config version,
indexed/pending/skipped/error inventory, dirty state, and built/observed times.
If it is stale or partial, direct source inspection can create a new evidence
observation. Without coverage and source confirmation, “not found” remains
`UNKNOWN`.

## Adapter boundary

An adapter preserves the producer's native payload and maps it to normalized
observations. It validates format version, input bytes, expected coverage,
subject identity, and provenance. It distinguishes passed, failed, skipped,
error, incomplete, and unavailable states according to the producer contract.

An aggregate score or exit code is a signal, not a universal verdict. A
missing output with a zero counter, an empty assertion set, a cached result for
another subject, or a parse error cannot fill a mandatory proof gap.

## Release decision boundary

The evaluator is intended to be a pure function of assessment, policy, valid
evidence, accepted obligations, and an injected evaluation time. It does not
perform network calls, run a model, mutate files, or create authorization.

The decision record points to a selected proof set. It keeps mandatory and
nonblocking obligations visible, shows unresolved unknowns, and includes the
shortest executable path to the next possible decision.

## Public-data boundary

This repository contains original synthesis, generic examples, and links to
public references. It does not distribute private application findings, local
run outputs, credentials, source snapshots, or copied upstream skill/code.
External references keep their own license and terms. See
[`docs/ecosystem.md`](ecosystem.md) for the research register.
