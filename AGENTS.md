# Contributor guidance

This guide applies to the public `e2e` repository. It describes the documentation and skill kit currently shipped here; it does not assert that a runtime engine, command-line interface, plugin, or host adapter exists.

## Scope

- Keep the repository portable and self-contained. The skill entrypoint is `skills/e2e/SKILL.md`; its references and assets live inside that folder so the folder can be copied as a unit.
- Preserve one user entrypoint and one canonical evidence and decision authority. The four assessment modes are `PLAN_ONLY`, `READ_ONLY_AUDIT`, `IMPLEMENT_AND_VERIFY`, and `RELEASE_REVIEW`.
- Respect the user's request and existing authorization. Read-only reconnaissance and requested plan output are allowed when the request covers them. Implementation, runtime verification, network, installation, spend, commit, publication, deployment, comments, uploads, and other external mutation need explicit scope.
- Keep target source unchanged in `READ_ONLY_AUDIT`; place generated output in a separately authorized run directory. Preserve unrelated user changes in implementation work.

## Evidence and claims

- Separate observed facts, assumptions, proposals, owner decisions, and `UNKNOWN` items.
- Never invent commands, timestamps, hashes, approvals, findings, screenshots, benchmarks, compatibility, certifications, or runtime results. Templates intentionally use `UNKNOWN`, `NOT_RUN`, or null values.
- Keep task status separate from check status. `DONE` documentation does not make an unexecuted check `PASS`.
- Keep raw evidence immutable and addressable. Capture identity, procedure, output, exit status, signal, sensitivity, redaction, freshness, and review. Preserve context-loss manifests and graph freshness when using compaction or graph assistance.
- Use `READY`, `CONDITIONALLY READY`, `NOT READY`, or `UNDETERMINED` only under the evidence policy. A decision never grants authorization, and missing evidence is not a proven failure.

## Upstream and licensing

External sources in `research/upstreams.json` and `docs/ecosystem.md` are research references only. Before adapting or distributing material, inspect resource closure, source identity, license scope, notices, permissions, and applicable host capabilities. Mixed or unknown licensing keeps material reference-only until reviewed. Keep original repository material under the root MIT license without implying that upstream sources share it.

## Review and maintenance

Review changes for local link resolution, JSON validity, exact mode names, all 16 control areas, evidence truthfulness, and accidental credentials or private identifiers. Run the bundled skill validator when available; do not add dependencies solely to validate documentation. A normative-reference, source-pin, resource-hash, license, notice, permission, host, protocol, context-transform, graph-provider, or producer-schema change triggers review of affected controls and fixtures. Retain prior observations as historical records.

Do not add machine-specific model mandates, global settings, installation instructions that imply support, or automatic execution of external repositories. Keep this guide aligned with the public scope as the planned core evolves.
