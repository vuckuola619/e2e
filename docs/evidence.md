# Evidence and decisions

This document defines the public evidence contract for `e2e`. The templates
show the shape of a run; the initial release does not execute a check or create
real evidence.

## Evidence is a claim with a boundary

An evidence record should let an independent reviewer answer:

1. What was observed or attested?
2. Which subject and candidate did it describe?
3. Which procedure, version, and scope produced it?
4. When was it observed, and when was it collected or reported?
5. What raw bytes, result, assertion, or human decision support it?
6. What was skipped, truncated, redacted, or otherwise uncertain?

If an answer is missing, preserve the gap as `UNKNOWN`, `NOT_RUN`, or another
appropriate diagnostic. Do not fill it with a plausible timestamp, hash,
screenshot, actor, command result, or approval.

## Identity dimensions

Evidence reuse is per control. The record should include the dimensions the
control requires:

| Dimension | Examples |
| --- | --- |
| Source | Revision, tree or dirty-content manifest, relevant file hashes. |
| Artifact | Build, package, image, database snapshot, or deployment digest. |
| Environment | Configuration fingerprint, feature flags, region, runtime, and dependencies. |
| Procedure | Exact command or interaction, working directory, tool version, and expected result. |
| AI evaluation | Model/provider or snapshot, prompt/template, corpus, dataset, grader, rubric, and cache identity. |
| UI observation | Route, viewport, device, browser, locale, theme, state, and render/source hashes. |
| Human review | Reviewer role, name or stable identity, scope, disposition, and acceptance time. |

A hash confirms the bytes that were checked. It does not confirm that the
content is truthful, that the actor is authentic, or that the procedure covered
the whole system. A report timestamp cannot refresh an old observation.

## Evidence classes

Use the class that describes how the record was produced:

| Class | Use |
| --- | --- |
| `NEW_RUN` | A procedure was run against the current subject and its output was captured. |
| `STATIC_REVIEW` | A reviewer inspected source or configuration without running the system. |
| `HISTORICAL` | An older record is retained for context and explicitly remains historical. |
| `OWNER_ATTESTATION` | A named owner attested to a fact that the policy allows this method to cover. |
| `EXTERNAL_PENDING` | A referenced result exists outside the local bundle but has not yet been verified for this subject. |

An imported file does not become a trusted `NEW_RUN` merely because its name or
metadata claims a run ID. Verify the bytes, provenance, identity, procedure,
and scope before using it.

## Status vocabulary

Task state and check state are separate. A documentation task may be complete
while its runtime check remains `NOT_RUN`. The following are canonical check
statuses:

| Status | Meaning |
| --- | --- |
| `PASS` | The defined procedure completed sufficiently, output was valid and complete, and the expected result was met. |
| `FAIL` | The procedure and evidence were valid enough to show that the expected result was not met. |
| `NOT_RUN` | The check has not been attempted, including because a tool, credential, or authorized capability is unavailable. |
| `N/A` | Applicability was positively established as absent and includes a reassessment trigger. |
| `UNKNOWN` | Available evidence cannot establish the relevant fact or scope. |

A task or prerequisite may be `BLOCKED` when a specific dependency or
permission prevents progress. `BLOCKED` is a workflow diagnostic, not a
canonical `check_status`; keep the missing dependency and next action visible.

Some producer failures are evidence validity diagnostics rather than semantic
`FAIL` results. For example, malformed output, timeout, truncated capture, or
an invocation error should remain visibly invalid or unresolved. A nonzero exit
can represent a valid test finding only when the producer contract and parsed
coverage say so.

## Time and supersession

Keep these times distinct:

- `observed_at`: when the system, artifact, or reviewer observation occurred;
- `collected_at`: when the host captured or imported it; and
- `reported_at`: when a view or report was generated.

Add `valid_until` or invalidators only when the control has a reason for them.
Freshness is not a universal time-to-live. When a subject changes, retain the
old record, mark affected reuse invalid, and create a new attempt or
observation. Use `supersedes` to explain a relation; do not overwrite history.

## Artifact manifest

For each file or private pointer, record at least:

- evidence ID and related control, task, requirement, gate, and finding IDs;
- relative path or approved private pointer;
- media type, size, and SHA-256 of the actual bytes;
- producer, procedure, source and candidate identity;
- sensitivity and redaction state;
- observation and collection times;
- expected and actual result, native status, exit code, signal, and coverage;
- reviewer, limitation, and any invalidator or supersession relation.

Paths must be confined to the intended bundle. Reject traversal, ambiguous
duplicate references, missing files, symlink escapes, and size/hash mismatch.
Do not put a manifest's own digest inside the bytes it hashes.

## Raw and compact views

Raw stdout, stderr, structured output, screenshots, traces, and other sensitive
artifacts may need a private location. A public or agent-facing compact view
can point to those records while reducing context. The compact view must retain:

- selected raw evidence IDs and hashes;
- the selection query and ordering;
- included and omitted counts by native status;
- each dropped range or field and the loss reason;
- transform version, configuration, and freshness;
- provider diagnostics and limitations; and
- a retrieval path subject to the access boundary.

If a mandatory assertion, warning, error, status, or evidence anchor may have
been dropped without an explainable manifest, use an uncompressed fallback or
mark the view insufficient. A graph or cache can accelerate retrieval but
cannot replace canonical raw evidence.

## Findings, unknowns, and acceptance

A finding should name its control, scope, evidence anchors, status or
disposition, priority, owner, due date or review trigger, and remediation or
retest path. A candidate that lacks supporting evidence remains a candidate.

An unknown should say why the fact is unresolved, what is blocked, who owns the
discovery task, and when it must be reviewed again. `N/A` is stronger than
“nothing found” and therefore requires applicability evidence.

Human acceptance is a separate record. It must identify the human reviewer by
name or stable identity and include that person's role, scope, decision,
conditions, time, and any deadline or rollback trigger. A role label without an
identified human is not a sign-off. An AI-generated statement, checkbox, or
report cannot manufacture human acceptance.

## Proof-set selection

A gate selects exact check runs and evidence IDs with a reason. The evaluator
should verify:

1. the proof belongs to the current subject and required identity dimensions;
2. the procedure and producer format are supported and complete;
3. the evidence is sufficiently fresh for that control;
4. mandatory checks and required acceptance are covered;
5. conflicting or superseded attempts have a documented disposition; and
6. any limitation or redaction does not remove a mandatory proof anchor.

The selected set is a reproducibility aid. It is not simply the newest result,
the highest score, or the shortest report.

## Decision rules

| Decision | Rule |
| --- | --- |
| `READY` | All applicable mandatory gates pass with valid evidence and required human acceptance. |
| `CONDITIONALLY READY` | All mandatory gates pass and each remaining obligation is nonblocking, bounded, owned, time-limited, monitored, and accepted. |
| `NOT READY` | A mandatory gate or release blocker is proven to fail, or a material risk has no accepted safe disposition. |
| `UNDETERMINED` | Evidence, subject identity, access, applicability, or acceptance is insufficient to decide. |

Mandatory failure takes precedence over missing proof. Missing, expired, or
identity-mismatched proof without a proven failure is generally
`UNDETERMINED`. An exception may document a disposition but cannot silently
make a mandatory control optional. `READY` never grants authorization for a
deployment or other side effect.

## Diagram evidence

When a diagram is applicable, its evidence record should include editable
source and render artifacts, `basis` (`SOURCE_DERIVED`, `OBSERVED`, `PROPOSED`,
or `UNKNOWN`), subject/environment and `as_of` time, source/evidence references
for nodes and edges, assumptions, and semantic limitations. Record parser,
renderer, and semantic-review statuses separately, together with renderer
version, safe command, working directory, exit status, source hash, and render
hash. A source hash and render hash are different values. Missing renderer or
unexecuted render is `NOT_RUN`/`UNKNOWN`; parser success alone does not validate
the meaning of a diagram. Include a short text summary for accessibility. The
skill's [evidence reference](../skills/e2e/references/evidence.md) captures the
same public contract in a portable template.

## Example of a synthetic record

The repository example uses placeholders and `NOT_RUN` statuses. It is a
shape example only and is not validated against an implemented schema:

```json
{
  "evidence_id": "EVD-SYNTHETIC-001",
  "synthetic": true,
  "evidence_class": null,
  "planned_evidence_class": "NEW_RUN",
  "subject": "SYNTHETIC_SUBJECT",
  "observed_at": null,
  "check_status": "NOT_RUN",
  "expected": "A complete authorized check result",
  "actual": null,
  "limitations": ["Synthetic example; no command was executed."]
}
```

Nulls and labels in an example must stay explicit. They are not permission to
invent values in a real run.

## Review before export

Before sharing an evidence pack, a reviewer should confirm that:

- raw and sanitized artifacts have separate hashes and relations;
- no secret, personal data, private path, backup, or credential entered the
  public bundle;
- the selected proof set is complete for the claimed decision;
- source, artifact, configuration, model, corpus, and time identities match;
- redaction and context loss are visible; and
- the decision, acceptance, and authorization records are separate.

No executed product-readiness or comparative runtime evidence is included.
Public-source metadata is documented in the [source comparison](comparison.md).
Future qualification must show actual command, host, tool, and version details
before advertising support.
