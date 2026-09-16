# Public standards and practice baselines

| Field | Value |
| --- | --- |
| `as_of` | 2026-09-16 research access date |
| Scope | Public references for planning end-to-end quality, security, reliability, accessibility, AI, and release reviews |
| Source revision | UNKNOWN; this document is not tied to a mutable upstream snapshot |
| Candidate or deployed artifact | NOT_APPLICABLE; no runtime artifact is assessed here |
| Environment | Public reference documentation |
| Owner | UNKNOWN |
| Reviewer | UNKNOWN |
| Status | DRAFT |

These links are reference points for choosing controls and questions. They do not certify a product, establish conformance, or prove that a mutable source had a particular state on the access date. Pin the exact document or revision when a control is adopted into a policy, and record the selected scope and interpretation in the assessment packet.

## Engineering and operational practice

- [Google SRE: evolving the SRE engagement model](https://sre.google/sre-book/evolving-sre-engagement-model/) — useful prompts for service ownership, operational load, and engagement decisions. Apply it as guidance; local SLO and escalation decisions still need named owners.
- [DORA metrics guide](https://dora.dev/guides/dora-metrics/) — defines measurement questions and cautions around delivery metrics. Record dataset definitions, time window, population, and limitations before comparing teams or releases.
- [Diátaxis](https://diataxis.fr/) — separates tutorials, how-to guides, reference, and explanation. Use it to organize assessment instructions and generated report views, not as runtime evidence.

## Security and supply chain

- [OWASP Application Security Verification Standard](https://owasp.org/projects/asvs) — a source for application verification topics and requirement language. Select applicable controls and version them in policy; a checklist or sampled review is not a full certification.
- [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) — prompts for secure development, provenance, vulnerability response, and release practice. Map only the practices relevant to the subject and record evidence method.
- [SLSA specification](https://slsa.dev/spec/v1.2/) — supply-chain provenance and build requirements. A reference to the specification is not a SLSA level claim; verify the exact source, builder, artifact, and provenance evidence required by policy.
- [Open Source Project Security (OSPS) Baseline](https://baseline.openssf.org/) — public baseline questions for open-source project hygiene. Treat a badge, file, or declared policy as an input to review rather than proof of effective control.

## Accessibility and inclusive UI

- [W3C Web Content Accessibility Guidelines 2.2](https://www.w3.org/TR/WCAG22/) — reference for perceivable, operable, understandable, and robust web content. Record applicable success criteria, user journey, environment, and manual review; automated scans cover only a subset.

## AI risk and evaluation

- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — vocabulary for governing, mapping, measuring, and managing AI risks. It is a risk-management reference, not a runtime pass/fail test.
- [NIST AI RMF resources](https://www.nist.gov/itl/ai-risk-management-framework/ai-risk-management-framework-resources) — supporting profiles and playbooks that may inform an assessment. Record which resource was used and avoid implying that a profile is a certification.
- [OWASP GenAI and LLM resources](https://genai.owasp.org/) — threat and control prompts for model-backed applications. Taxonomies help choose adversarial cases; they do not establish that a product is secure.
- [OWASP Agentic Skills project](https://owasp.github.io/www-project-agentic-skills-top-10/) — evolving prompts for skill provenance, access, and untrusted instructions. Treat the project as provisional until a selected revision is pinned and reviewed.
- [MITRE ATLAS](https://atlas.mitre.org/) — living knowledge base for AI-enabled system threats. Use a specific technique entry and identity when it matters; do not turn a taxonomy label into a reproduced finding.

## Applying a baseline

Use the following sequence for any reference:

1. Identify the subject, journey, data, actor, environment, artifact, and owner.
2. Select the relevant standard topics and record the version or URL used.
3. Translate selected topics into requirements, checklist rows, tasks, gates, and evidence targets.
4. Choose an observation procedure that can prove the control for this subject. A document, checkbox, score, or parser result alone is guidance or an observation, not a final decision.
5. Preserve raw evidence, identity, timing, limitations, and human acceptance separately from the decision.

## Maintenance trigger

Revisit this page and every affected requirement when a linked normative source changes, a selected version is withdrawn, a model or protocol profile changes, the subject adds a new data or tool boundary, or an owner changes the acceptance rule. Re-run relevant fixtures and qualification checks after updating a source pin, resource hash, license or notice, host capability, context transform, graph provider, or producer schema. Keep prior observations as historical records and do not silently regenerate them with a new baseline.
