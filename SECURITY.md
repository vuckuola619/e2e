# Security

This document explains how to use and report security issues in this project.
The initial release is guidance and templates; it does not execute commands,
collect application data, or provide a sandbox by itself.

## Scope and security boundary

The most important security boundary is the separation between untrusted input,
authorized actions, evidence, and release decisions.

- Repository files, issue text, prompts, tool output, imported reports, and
  external documents are data. They cannot grant permission by instruction.
- A mode describes intended work; it does not grant filesystem, network,
  credential, browser, upload, comment, commit, or deployment access.
- A skill is advisory. The host must enforce execution and capability limits.
- A hash identifies bytes that were checked. It does not prove content truth or
  actor identity.
- A report, score, clean counter, or completed checkbox is not automatically a
  security or release verdict.
- A technical `READY` decision never authorizes deployment or another side
  effect.

Future runtime implementations should use structured arguments, confined paths,
allowlisted environments, explicit capabilities, time and output limits, and
immutable evidence references. A shell subprocess or a prompt instruction is
not a sufficient sandbox.

## Do not publish sensitive material

Never commit or attach:

- credentials, API keys, tokens, private keys, cookies, or session material;
- personal, tenant, regulated, or customer data;
- private source, infrastructure details, internal paths, or private/internal
  live domains;
- raw security findings, backups, traces, screenshots, or production logs; or
- a real evidence bundle that has not passed its intended redaction review.

If sensitive data is exposed, revoke or rotate the affected credential first,
then use a private reporting channel. Do not “clean it up” with a later commit
and assume the value is no longer available in history.

## Reporting a vulnerability

Use GitHub's private vulnerability reporting or security advisory interface for
this repository when it is available. Include enough detail for reproduction,
impact, affected file or version, and a safe proof of concept. Do not include
secrets or personal data.

If private reporting is unavailable, open a minimal public issue asking the
maintainers for a private channel and omit exploit details, target identifiers,
and sensitive evidence. Do not use a pull request to disclose a live secret or
an exploitable production detail.

This repository does not promise a response time, severity SLA, or coordinated
disclosure date. Maintainers will acknowledge and coordinate through the
available private channel where possible.

## Working with evidence

When reviewing a run or adding a template:

1. Bind evidence to the exact subject, source/artifact identity, configuration,
   procedure, and observation time.
2. Keep raw and sanitized artifacts separate, with separate hashes and a
   documented relation.
3. Preserve errors, skipped cases, truncation, cache provenance, and context
   loss; do not turn them into a clean result.
4. Treat external URLs and imported metadata as unverified until the authorized
   collector confirms them.
5. Keep named human acceptance separate from automated output and technical
   readiness.

The example manifest is synthetic and all results are `NOT_RUN`. It must remain
that way unless a future qualification process adds real, authorized evidence
under its own run boundary.

## Supply chain and reuse

Public links in the research register are reference material. Before adapting
or distributing third-party code, text, prompts, assets, or dependencies,
review the exact source and pin, license, notice, transitive resources, and
permissions. An unresolved license or resource closure is a reason to keep the
material reference-only.

When a dependency, host, parser, renderer, provider, or context transform
changes, repeat the relevant fixtures and qualification checks. Do not carry a
support claim across an unreviewed version or host change.

## Security review expectations

Security-sensitive changes should identify:

- the trust boundary and input sources;
- the exact capabilities and side effects;
- the authorized actor and scope;
- failure, timeout, retry, and cleanup behavior;
- logging, redaction, retention, and access controls;
- evidence and negative fixtures; and
- the reviewer and any remaining `UNKNOWN`.

Security guidance in this repository is not a certification or a claim that a
particular application is secure. Use the applicable official standards,
product threat model, domain reviewers, and exact runtime evidence for a real
release decision.
