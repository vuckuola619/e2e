# Contributor guidance

This guide applies to the public `e2e` repository. It describes the documentation and skill kit currently shipped here; it does not assert that a runtime engine, command-line interface, plugin, or host adapter exists.

## Scope

- Keep the repository portable and self-contained. The skill entrypoint is `skills/e2e/SKILL.md`; its references and assets live inside that folder so the folder can be copied as a unit.
- Preserve one user entrypoint and one canonical evidence and decision authority. The four assessment modes are `PLAN_ONLY`, `READ_ONLY_AUDIT`, `IMPLEMENT_AND_VERIFY`, and `RELEASE_REVIEW`.
- Respect the user's request and existing authorization. Read-only reconnaissance and requested plan output are allowed when the request covers them. Implementation, runtime verification, network, installation, spend, commit, publication, deployment, comments, uploads, and other external mutation need explicit scope.
- Keep target source unchanged in `READ_ONLY_AUDIT`; place generated output in a separately authorized run directory. Preserve unrelated user changes in implementation work.

## Product lifecycle

- Preserve the ten lifecycle phases: `IDEA`, `DISCOVERY`, `PRODUCT_PLANNING`,
  `DESIGN`, `BUILD`, `REVIEW`, `QA`, `RELEASE`, `OPERATE`, and `ITERATE`.
- Keep lifecycle phase and bounded phase span separate from the four assessment
  modes and from release decisions or authorization. Work may enter at any
  phase; iteration may route to an earlier phase.
- Scale planning depth with uncertainty, risk, product impact, coordination,
  regulatory/privacy concerns, and operational impact. A clear small change may
  use the direct task/check path; a brief or full product artifact is not a
  universal prerequisite.
- Product artifacts must distinguish observations, source-backed findings,
  assumptions, hypotheses, proposals, attributed owner decisions, and
  `UNKNOWN` items. Planned research is `NOT_RUN`.
- Use `UNKNOWN` or reasoned `N/A` for missing or out-of-scope identities; never
  invent demand, participants, dates, approvals, sign-off, owners, outcomes, or
  runtime results. New revisions link upstream and downstream artifacts and
  supersede prior records without overwriting historical evidence.

## Evidence and claims

- Separate observed facts, assumptions, proposals, owner decisions, and `UNKNOWN` items.
- Never invent commands, timestamps, hashes, approvals, findings, screenshots, benchmarks, compatibility, certifications, or runtime results. Templates intentionally use `UNKNOWN`, `NOT_RUN`, or null values.
- Keep task status separate from check status. `DONE` documentation does not make an unexecuted check `PASS`.
- Keep raw evidence immutable and addressable. Capture identity, procedure, output, exit status, signal, sensitivity, redaction, freshness, and review. Preserve context-loss manifests and graph freshness when using compaction or graph assistance.
- Use `READY`, `CONDITIONALLY READY`, `NOT READY`, or `UNDETERMINED` only under the evidence policy. A decision never grants authorization, and missing evidence is not a proven failure.

## Upstream and licensing

External sources in `research/upstreams.json`, the comparison snapshot, and
`docs/ecosystem.md` are research references only. The documentary comparison is
separate from a head-to-head runtime benchmark, which remains `NOT_RUN` until
matched trials exist. Before adapting or distributing material, inspect
resource closure, source identity, license scope, notices, permissions, and
applicable host capabilities. Mixed or unknown licensing keeps material
reference-only until reviewed. Keep original repository material under the root
MIT license without implying that upstream sources share it.

## Review and maintenance

Review changes for local link resolution, JSON validity, exact mode names, all
10 lifecycle phases, all 16 control areas, phase/mode separation, progressive
planning depth, evidence truthfulness, and accidental credentials or private
identifiers. Check that product brief, discovery plan, and product plan links
remain closed inside the skill folder and that comparison links point to the
documentary artifacts. Run the bundled skill validator when available; do not
add dependencies solely to validate documentation. A normative-reference,
source-pin, resource-hash, license, notice, permission, host, protocol,
context-transform, graph-provider, producer-schema, lifecycle, or product
artifact change triggers review of affected controls and fixtures. Retain prior
observations as historical records.

Do not add machine-specific model mandates, global settings, installation instructions that imply support, or automatic execution of external repositories. Keep this guide aligned with the public scope as the planned core evolves.
