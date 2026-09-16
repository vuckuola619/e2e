# Evidence reference

Use this reference when an assessment produces observations, imports a producer result, compacts context, or evaluates release readiness. It defines a portable evidence contract; it is not an evidence collector or validator implementation.

## Evidence record

Each evidence item should carry, or explicitly mark `UNKNOWN`, the following fields:

| Field | Meaning |
| --- | --- |
| `evidence_id` | Stable unique ID such as `EVD-...`; never reuse an ID for a new attempt |
| `evidence_class` | `NEW_RUN`, `STATIC_REVIEW`, `HISTORICAL`, `OWNER_ATTESTATION`, or `EXTERNAL_PENDING` |
| Links | Checklist, task, requirement, gate, and finding IDs supported by this item |
| Subject identity | Source revision and dirty state, artifact digest, environment, and applicable model, prompt, corpus, image, or config identity |
| Procedure | Exact command or human procedure, working directory, tool or producer version, and invocation inputs |
| Result | Expected and actual result, stdout/stderr artifacts, exit code, signal or timeout, native producer status, and separate `execution_status` |
| Time | `observed_at` for the run; report or export time is a separate field |
| Integrity | File path, media type, size, SHA-256, sensitivity, redaction state, and private pointer where needed |
| Review | Actor, reviewer, disposition, limitations, and whether required human acceptance is complete |
| Check state | `PASS`, `FAIL`, `NOT_RUN`, `N/A`, or `UNKNOWN`; use `UNKNOWN` for insufficient evidence rather than hiding it in prose |

Hashes identify bytes, not truth, authorization, actor identity, or semantic correctness. An imported timestamp, subject, score, count, or producer assertion is a claim until the collector verifies its identity and scope. Keep source, configuration, model, prompt, corpus, and artifact identity separate so a result cannot silently cross candidates.

## Status mapping

- `PASS`: the defined check ran, output was valid and complete for its expected inventory, identity matched, and the actual result met the expected result.
- `FAIL`: the check ran validly and the actual result violated the expected result or a mandatory assertion.
- `NOT_RUN`: the check did not execute because a tool, permission, credential, host capability, or explicit authorization was unavailable. Include the reason and a next task.
- `N/A`: applicability was established and documented with evidence and a reassessment trigger.
- `UNKNOWN`: evidence is insufficient or identity, coverage, freshness, provenance, or owner decision is unresolved. It is not a pass or a failure.

Keep `execution_status`, producer status, evidence validity, and canonical check status in different fields. `execution_status` can be `NOT_STARTED`, `STARTED`, `COMPLETED`, `INTERRUPTED`, `ERROR`, or `UNKNOWN`; retain it for every attempt so a failed process is never erased. A nonzero exit can be a legitimate finding only after output validity and producer semantics are established. Timeout, parser, invocation, dependency, or internal errors are invalid or unresolved evidence and normally use `check_status=UNKNOWN` with the actual execution status recorded. An empty result or zero finding count is useful only when output, expected case inventory, coverage, subject, freshness, and producer contract all match.

## Immutable attempts and freshness

Store each attempt as a new immutable record. Preserve failed, superseded, and partial attempts and explain why a gate selects one attempt. A retry is not allowed to erase a failure. Recheck identity before resume or decision: source change, dirty diff, artifact digest, policy version, configuration, model, prompt, corpus, or selected module can invalidate dependent evidence.

Freshness is per control and procedure. Historical evidence remains historical; it can establish a baseline or satisfy a policy that explicitly accepts it, but it does not become a new run because a report was regenerated. Separate observation time from report time, and record the retention or expiry rule when one exists.

## Context views and loss

Capture raw stdout and stderr before filtering, compaction, or retrieval. A context view records:

- view, schema, module, router, policy, run, and subject identity;
- selected raw evidence IDs and hashes, selection query, included and omitted counts by native status;
- transform version and configuration, ordered loss manifest, truncation or timeout diagnostics;
- actual token or byte counts when measured, freshness, provider diagnostics, limitations, and retrieval references.

Lossy transformation is allowed for advisory context only when status, mandatory control anchors, assertions, warnings, errors, and evidence links survive. If a line or field is dropped, state why and how to retrieve it. When loss cannot be explained, use the raw or uncompressed view. A compact view cannot replace the raw artifact for mandatory evidence.

## Diagram evidence

For every applicable diagram, keep an editable source and its rendered artifact as separate evidence. Record `basis` as `SOURCE_DERIVED`, `OBSERVED`, `PROPOSED`, or `UNKNOWN`; subject, `as_of`, revision or artifact identity, evidence anchors, assumptions, and gaps; renderer and version, exact command and working directory, exit status, and separate SHA-256 values for source and render. If a renderer is unavailable or not run, mark the render `NOT_RUN` or `UNKNOWN`. A parse or render success proves syntax or pixels only; it does not prove semantic truth, topology, or runtime behavior.

## Graph freshness

For graph-assisted discovery, record source or corpus identity, per-file hashes or revision references, parser and configuration version, indexed, pending, skipped, and error inventories, built and observed times, and dirty state. A stale or incomplete graph must be visible in the report. Direct source reading can produce a new source-confirmed observation; it does not retroactively make the graph fresh. A `not found` result without complete coverage and direct confirmation remains `UNKNOWN`.

## Redaction and export

Keep raw private evidence addressable by evidence ID while exporting a sanitized view for broader audiences. Record sensitivity, redaction state, omitted fields, transformation version, and a private pointer when raw content is withheld. Secret scanners and clean output are only one check; a scanner result never proves that all secrets or personal data are absent. Never publish credentials, personal data, raw backups, unreviewed logs, or private run paths.

## Proof set and release decision

The final record includes candidate identity, applicable mandatory gates, a selected proof set (`GATE-* → EVD-*`), failed or missing evidence, exceptions, named human acceptance, decision time when an actual decision is made, and limitations. Use exactly one decision: `READY`, `CONDITIONALLY READY`, `NOT READY`, or `UNDETERMINED`.

`READY` requires every applicable mandatory gate to have fresh valid proof, matching candidate identity, required acceptance, and no release blocker. `CONDITIONALLY READY` still requires all mandatory gates to pass and permits only bounded, nonblocking obligations with owner, deadline, monitoring, acceptance, and rollback or kill criteria. Proven mandatory failure or unsafe side effect is `NOT READY`. Missing evidence, identity, access, applicability, or owner decision is `UNDETERMINED` until resolved. A readiness decision never grants deployment or publication authorization.

Use [../assets/evidence-manifest.example.json](../assets/evidence-manifest.example.json) as a shape-only synthetic example. It intentionally contains no real timestamps, hashes, approvals, commands, or runtime results.
