# Anti-slop adoption note

Status: `REFERENCE` for the e2e skill. This note records a focused, read-only
review of selected first-party files from four public repositories observed on
2026-09-16. It explains gaps in the previous e2e guidance and the small set of
ideas adapted into the current skill. No upstream repository was installed,
executed, or vendored. The review does not claim to cover every file in any
repository, and it does not produce a runtime benchmark or a quality score.

The exact reviewed paths, full commit pins, blob identities, SHA-256 hashes,
license observations, and retrieval times are in the separate
[anti-slop research snapshot](../research/anti-slop-2026-09-16.json). The
source links below are pinned to those same commits.

## petergyang/no-ai-slop

Primary pinned sources: [README](https://github.com/petergyang/no-ai-slop/blob/000650b156983f5159695b441477f4e63b25dc85/README.md),
[skill](https://github.com/petergyang/no-ai-slop/blob/000650b156983f5159695b441477f4e63b25dc85/skills/no-ai-slop/SKILL.md),
[evaluation notes](https://github.com/petergyang/no-ai-slop/blob/000650b156983f5159695b441477f4e63b25dc85/skills/no-ai-slop/eval.md),
and [LICENSE](https://github.com/petergyang/no-ai-slop/blob/000650b156983f5159695b441477f4e63b25dc85/LICENSE).

**Gap in previous e2e guidance.** Evidence rules caught fabricated claims,
but a true sentence could still be vague, padded, repetitive, or portable to
another product without a product-specific copy pass.

**Adopted.** The copy lane separates finding detection from editing. It names
the exact string and location, asks whether the wording could move unchanged to
another product, prefers mechanisms and consequences, requires support or a
synthetic label, and favors the minimum effective edit that preserves useful
voice.

**Rejected or narrowed.** e2e does not infer authorship, assign an AI
percentage, impose a universal banned-word list, force a single paragraph
shape, or copy a wholesale rule table.

## Leonxlnx/taste-skill

Primary pinned sources: [README](https://github.com/Leonxlnx/taste-skill/blob/ccbc15639c97057cbfcf32ecebc38ef716e4bb37/README.md),
[taste skill](https://github.com/Leonxlnx/taste-skill/blob/ccbc15639c97057cbfcf32ecebc38ef716e4bb37/skills/taste-skill/SKILL.md),
[redesign skill](https://github.com/Leonxlnx/taste-skill/blob/ccbc15639c97057cbfcf32ecebc38ef716e4bb37/skills/redesign-skill/SKILL.md),
and [LICENSE](https://github.com/Leonxlnx/taste-skill/blob/ccbc15639c97057cbfcf32ecebc38ef716e4bb37/LICENSE).

**Gap in previous e2e guidance.** The workflow had UI and accessibility
controls but no small pre-build design read or rendered pre-flight tied to page
kind, audience, task, and constraints. A generic composition could pass the
general workflow without explaining its product purpose.

**Adopted.** The conditional review records page kind, audience, primary task,
brand or reference signals, constraints, design direction, and a redesign
preservation contract. It asks what a card, pill, gradient, shadow, motion, or
asymmetry serves, then checks CTA intent, responsive renders, wrapping,
overflow, focus, contrast, and reduced motion.

**Rejected or narrowed.** e2e does not require a framework, font, icon or
animation library, package installation, fixed taste dials, numeric self
ratings, universal color or layout bans, guessed performance targets, or
unrecorded audience approval. The route applies to relevant UI artifacts, not
every product or response.

## Nutlope/hallmark

Primary pinned sources: [README](https://github.com/Nutlope/hallmark/blob/13ac0ec7e148655948100b6396439e481361d690/README.md),
[skill](https://github.com/Nutlope/hallmark/blob/13ac0ec7e148655948100b6396439e481361d690/skills/hallmark/SKILL.md),
and [LICENSE](https://github.com/Nutlope/hallmark/blob/13ac0ec7e148655948100b6396439e481361d690/LICENSE).

**Gap in previous e2e guidance.** The existing workflow already separated
assessment modes and authorization, but visual work had no artifact-specific
checklist for create, audit without edits, redesign with preservation choices,
and reference study. It also did not ask the reviewer to record what a
redesign preserves.

**Adopted.** The route records the intent, states what a redesign preserves,
and describes observable macrostructure, typography roles, color anchors,
density, and interaction patterns for a reference study. Read-only audits use
numbered findings with exact locations and observable symptoms.

**Rejected or narrowed.** e2e does not expose a Hallmark CLI, invent a score,
call a result benchmarked or superior without matched trials, use fingerprint
language to justify imitation, or infer quality from popularity or examples.

## miqdadbadjuber/anti-slop

Primary pinned sources: [README](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/README.md),
[core skill](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/skills/antislop/SKILL.md),
[UI skill](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/skills/antislop-ui/SKILL.md),
[copy skill](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/skills/antislop-copywriting/SKILL.md),
[code comments skill](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/skills/antislop-code/SKILL.md),
[mobile skill](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/skills/antislop-layoutmobile/SKILL.md),
and [LICENSE](https://github.com/miqdadbadjuber/anti-slop/blob/743735248fbaefd76bb56619615687dfa8b3bc1e/LICENSE).

**Gap in previous e2e guidance.** e2e already had truthfulness, evidence, and
accessibility rules, but did not translate them into a concrete copy and visual
review route with hard function gates, contextual purpose questions,
consistency checks, a design direction, and synthetic-content labeling.

**Adopted.** The artifact reference says it is a filter rather than a style
guide, separates the three review lanes, starts from a positive product brief
or design direction, treats familiar pattern clusters as diagnostic prompts,
requires synthetic labels for demo claims, and gives audits exact numbered
findings.

**Rejected or narrowed.** e2e keeps its four assessment modes rather than
adding During/After modes, does not add a second approval gate, ban punctuation
or aesthetics universally, turn energy or rhythm dials into proof, require a
fixed report for every artifact, or claim that removing named patterns makes a
design good. The related `antislop-code` material is about comments only; it is
not a code-quality or security engine.

## e2e status after adoption

Before this note, e2e already covered evidence identity, authorization,
provenance, accessibility, validation, and truthful readiness, and its
ecosystem register mentioned taste-skill and Hallmark. The missing layer was a
conditional route from artifact type to a product-specific copy review and
separate rendered and interaction evidence.

| e2e material | Current status |
| --- | --- |
| `skills/e2e/references/artifact-quality.md` | `AVAILABLE_GUIDANCE`, loaded only for relevant copy or UI artifacts |
| `skills/e2e/assets/artifact-review.md` | `TEMPLATE`, with copy, rendered visual, and runtime rows |
| Rendering and interaction execution | Host-dependent; `NOT_RUN` unless the host actually observes or runs it |
| Canonical modes, lifecycle phases, domains, and checks | Unchanged: 4 modes, 10 phases, 16 domains, 80 baseline checks |

This adoption adds a focused review lens. It does not claim a result is
“slop-free,” award a taste verdict, or promote a release decision. External
licenses remain scoped to the inspected files; the four source packages were
not copied into e2e.
