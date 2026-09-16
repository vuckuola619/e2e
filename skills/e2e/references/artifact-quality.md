# Artifact quality review

Use this reference only when the authorized subject includes user-facing copy
or a frontend or visual artifact. It is a conditional review lens that
complements the existing e2e controls. It does not add an assessment mode,
lifecycle phase, control domain, or canonical check.

## Scope and non-claims

This review detects observable risks; it does not detect authorship or
guarantee taste.

User direction, brand constraints, accessibility, truthfulness, and product
purpose govern choices. A positive product brief or a short design direction
states what the artifact is for. This reference filters decisions; it does not
provide a visual preset or universal ban list.

A technique is not a failure by itself. Treat it as a finding only when it
breaks evidence, function, accessibility, an explicit requirement, or a stated
purpose. A cluster of familiar patterns is a prompt to ask what each serves.
An explicit user or brand choice overrides a generic pattern heuristic; record
the rationale.

Never report `PASS` for a check that was not run. Do not guess AI authorship,
assign an AI percentage, or use a numeric self taste score.

## Routing

Load only the sections that match the artifact:

- User-facing prose that is created or edited loads the **copy lane**.
- A frontend or visual artifact being created, redesigned, or reviewed loads
  the **copy**, **rendered visual**, and **runtime interaction** lanes.
- A backend, data, API, or command-only change with no user-facing artifact
  does not require this reference. Use the applicable existing controls.
- `PLAN_ONLY` records the route, design direction, preservation contract, and
  evidence targets; it does not turn planned work into a result.
- `READ_ONLY_AUDIT` reports numbered findings with exact locations and
  proposed corrections. It leaves the target unchanged.
- `IMPLEMENT_AND_VERIFY` and `RELEASE_REVIEW` use the companion
  [artifact review matrix](../assets/artifact-review.md) and attach evidence
  for every attempted lane. A matrix does not promote readiness automatically.

For a new artifact, state the page or artifact kind, audience, primary task,
content proof, constraints, and a short design direction before implementation.
For a redesign, state a preservation contract for content, information
architecture, brand, behavior, or the parts intentionally changed. For a
reference study, record observable structure, typography roles, color anchors,
density, and interaction patterns without copying identity or unsupported
content.

Do not silently rewrite quoted or authoritative legal text, log output, or
immutable evidence. An explicitly requested edited draft is a separate
artifact that preserves original provenance; raw evidence remains immutable.
Report a separate finding when preserved content creates a risk.

## Three review lanes

### Copy lane

Inspect visible strings and their source locations. Ask whether the wording is
specific to the product and its task, names a mechanism or consequence, has
source support or an explicit synthetic label, and preserves the author's
useful voice. Look for formulaic repetition, puffery, throat clearing, fake
insight, synonym cycling, and an unearned closing. Check that CTA labels match
the action and its state. Name the exact string and make the minimum effective
edit; a finding must not silently rewrite the source.

### Rendered visual lane

Inspect an actual render at representative viewports and states. Check that
composition follows the page job and audience, hierarchy reflects a real
workflow or decision, and empty space and density have an explained purpose.
Review clusters of cards, pills, gradients, shadows, motion, or other familiar
patterns by asking what each serves. Check typography, color, radius, spacing,
and icon consistency, plus desktop and mobile wrapping and overflow. Record
the reduced-motion result when motion exists.

Source validity is not a visual `PASS`. If no screenshot or equivalent render
observation exists, the rendered visual lane is `NOT_RUN`, even when source
inspection passes.

### Runtime interaction lane

Run authorized interaction checks against the identified artifact and
environment. Check semantic landmarks and heading order; labels, keyboard
path, visible focus, target size, and control state; overflow, wrapping,
zoom/reflow, and representative viewport behavior; contrast and non-color
status cues; asset availability and offline behavior; and demo labels, links,
errors, empty states, and progressive enhancement.

Static source review does not pass an interaction check. If the interaction
run did not happen or its identity is insufficient, use `NOT_RUN` or
`UNKNOWN` with the reason and next task.

## Evidence and status

Keep source, rendered visual, and runtime evidence identifiers separate. A row
in the matrix records its lane, prompt, status, evidence location, finding,
and correction. Use the existing e2e status semantics:

| Status | Meaning |
| --- | --- |
| `PASS` | The defined check ran with valid, relevant evidence and met its expected result. |
| `FAIL` | The defined check ran with valid evidence and did not meet its expected result. |
| `NOT_RUN` | The check was not attempted, including when a render, interaction, tool, or authorization was unavailable. |
| `UNKNOWN` | Identity, coverage, provenance, freshness, or decision information is insufficient. |
| `N/A` | The lane or prompt is outside scope and the applicability reason and reassessment trigger are recorded. |

Link a finding to an existing applicable e2e control when useful; do not create
a second control register. A positive artifact review is an observation about
the reviewed scope. It cannot establish product usefulness, accessibility
conformance, release readiness, or human acceptance by itself.

## Small routing examples

- A backend-only fix with no user-facing copy or UI skips this review; it does
  not inherit a visual obligation.
- If the user explicitly chooses a gradient or a dense layout and it serves the
  brief, retain it and record the purpose instead of treating the pattern name
  as a failure.
- A parser or source inspection can pass its own source check while the
  rendered visual lane remains `NOT_RUN` without a screenshot or render.
- A quoted contract, authoritative legal notice, or raw log remains unchanged
  unless the user explicitly requests an edited draft; preserve the original
  provenance and locate any concern separately.
- The reviewer describes observable text and behavior. It never infers who or
  what authored them.

This is an original e2e synthesis. The documentary sources that informed it
are attribution only; no upstream package, CLI, rule set, or runtime is
required. Reusing external text or code must respect its applicable license and
notice requirements within the authorized scope.

Pinned primary source notes: [no-ai-slop](https://github.com/petergyang/no-ai-slop/tree/000650b156983f5159695b441477f4e63b25dc85),
[taste-skill](https://github.com/Leonxlnx/taste-skill/tree/ccbc15639c97057cbfcf32ecebc38ef716e4bb37),
[hallmark](https://github.com/Nutlope/hallmark/tree/13ac0ec7e148655948100b6396439e481361d690),
and [anti-slop](https://github.com/miqdadbadjuber/anti-slop/tree/743735248fbaefd76bb56619615687dfa8b3bc1e).
