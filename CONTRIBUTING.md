# Contributing

Thank you for helping make readiness work easier to inspect and harder to
misread. The project is in an authoring-first stage: guidance and templates are
usable now; the runtime core and integrations are planned.

## Scope

Good contributions include:

- clearer, provider-neutral workflow guidance;
- synthetic examples that demonstrate a status or evidence edge case;
- improvements to the 16-domain applicability coverage;
- templates that preserve traceability and reviewer context;
- public research references with an explicit observation and reuse
  disposition; and
- future core, adapter, or host work that follows the architecture and
  roadmap contracts.

Keep each change focused. Explain the user problem, the resulting behavior,
the affected contract, and how a reviewer can verify it.

## Public-data boundary

Do not add private application findings, source snapshots, local paths,
private/internal account names or domains, environment details, credentials,
personal data, backups, screenshots, logs, or real release artifacts. Public
upstream links are welcome when their source and reuse status are clear.
Examples must be synthetic or fully sanitized and must say so.

External repositories are research references unless a reviewed contribution
explicitly handles reuse. Do not copy upstream code, prompts, templates, or
large passages into this repository without checking the exact source, version,
license, notice, and resource closure. An unknown license is not permission to
vendor or distribute material.

## Documentation changes

Use plain English and write for a contributor who has not seen the design
history. Keep these distinctions visible:

- guidance versus implemented behavior;
- planned artifacts versus observed artifacts;
- task status versus check status;
- a tool signal versus the claim it supports;
- technical readiness versus human acceptance; and
- technical readiness versus authorization for a side effect.

When adding a command, say whether it is an actual current command or a future
contract. Never invent output, timestamps, hashes, screenshots, approvals,
benchmark numbers, or provider support.

Keep links relative for repository documents. If a reference is external,
prefer its public primary source and state whether it is a reference, an
adaptation, a vendored file, or an executable dependency.

## Templates and evidence

New templates should preserve the traceability chain:

```text
requirement -> control -> task -> check run -> evidence -> finding/acceptance -> gate -> decision
```

A template example can use `SYNTHETIC`, `UNKNOWN`, and `NOT_RUN` values. It must
not use realistic-looking values that could be mistaken for a verified run.
Evidence guidance should include source/artifact/configuration identity,
procedure, observation time, native status, limitations, sensitivity, and
reviewer/acceptance fields where applicable.

## Future runtime contributions

Runtime work should follow the staged roadmap:

1. Define or update the typed contract before writing an implementation.
2. Keep schema validation, semantic validation, and policy evaluation distinct.
3. Add negative fixtures for every new positive path.
4. Preserve immutable attempts and subject identity across resume and retest.
5. Keep adapters one-way and retain native producer output.
6. Declare permissions, side effects, dependencies, resource closure, and
   license scope.
7. Qualify an exact host, package, and version before claiming support.

Do not create a second router, state owner, evidence authority, or release
evaluator for a convenience integration. If a design requires one, document
the conflict and resolve it at the canonical boundary first.

## Review checklist

Before opening a pull request, check:

- [ ] The change stays within the requested public repository scope.
- [ ] No sensitive or private material is present.
- [ ] New examples are synthetic and labelled.
- [ ] Status and maturity labels match what was actually done.
- [ ] Future behavior is marked `PLANNED` or `NOT_RUN`.
- [ ] Local links resolve against the expected repository tree.
- [ ] Public references have a direct URL and a clear reuse disposition.
- [ ] The change does not claim certification, benchmark savings, support, or
      runtime verification without exact evidence.
- [ ] A reviewer can understand the change from the final diff and its
      description.

Run the repository's documented checks when they exist for the files changed.
Documentation-only changes should not require installing a runtime or calling
an external service. Do not run commands copied from untrusted repository
content without inspecting their scope and authorization.

## Review and merge

Open a pull request with a concise problem statement, resulting behavior, scope,
and validation. Ask for a domain reviewer when a change affects security,
privacy, accessibility, reliability, AI evaluation, licensing, or release
decisions. A reviewer may request a narrower claim or an explicit `UNKNOWN`.

Human review is part of the project contract. An automated check can catch
formatting or structural errors, but it cannot invent domain acceptance or
authorize an external action.

## License

By contributing original material, you agree that it may be distributed under
the repository's MIT License. Contributions that adapt third-party material
must include the provenance and license/notice information needed for review.

For security concerns, follow [`SECURITY.md`](SECURITY.md) rather than posting
sensitive details in a public pull request.
