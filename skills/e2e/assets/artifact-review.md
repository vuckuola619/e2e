# Artifact review matrix

Copy this template into an authorized run directory when a user-facing copy
or frontend or visual artifact is in scope. Replace placeholders only with
observed facts or an explicit applicability decision. This matrix is a review
aid, not a new control register or a readiness score.

## Context

```yaml
artifact: UNKNOWN
revision: UNKNOWN
assessment_mode: UNKNOWN
page_kind: UNKNOWN
audience: UNKNOWN
primary_task: UNKNOWN
design_direction: UNKNOWN
preservation_contract: UNKNOWN
```

## Evidence identities

```yaml
source_evidence: []
render_evidence: []
runtime_evidence: []
source_observed_at: UNKNOWN
render_observed_at: UNKNOWN
runtime_observed_at: UNKNOWN
```

Keep source, render, and runtime identities separate. Add a reviewer and review
time only when they were observed; otherwise leave them `UNKNOWN`.

## Review rows

| Lane | Review prompt | Status | Evidence location | Finding | Correction |
| --- | --- | --- | --- | --- | --- |
| copy | Is the wording specific to this product and task rather than portable boilerplate? | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| copy | Does it name a concrete mechanism or consequence? | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| copy | Does each factual claim have source support, and is synthetic content labeled? | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| copy | Does the edit preserve useful voice, uncertainty, humor, and edge? | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| copy | Were repetition, puffery, throat clearing, fake insight, synonym cycling, or an unearned closing located and resolved or justified? | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| copy | Do CTA labels match the action and current state? | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Does composition follow the page job and audience? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Does hierarchy reflect a real workflow or decision? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Does each cluster of familiar patterns have a recorded purpose? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Are typography, color, radius, spacing, and icons consistent with the direction? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Were desktop and mobile screenshots or equivalent renders inspected? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Does density and empty space serve the task? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| rendered visual | Does motion have a purpose, and was reduced motion inspected? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| runtime | Are landmarks and heading order semantic? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| runtime | Do labels, keyboard path, visible focus, target size, and control states work? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| runtime | Do overflow, wrapping, zoom, reflow, and representative viewports work? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| runtime | Do contrast and non-color status cues remain usable? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| runtime | Are assets available under the authorized offline or network boundary? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |
| runtime | Do demo labels, links, errors, empty states, and progressive enhancement behave honestly? | NOT_RUN | UNKNOWN | UNKNOWN | UNKNOWN |

## Unresolved items and decision impact

```yaml
unresolved_unknowns: []
unrun_checks: []
reviewer: UNKNOWN
reviewed_at: UNKNOWN
decision_impact: UNKNOWN
```

`PASS` requires a defined check, valid relevant evidence, matching identity,
and the expected result. `NOT_RUN` remains `NOT_RUN` when execution did not
happen. `UNKNOWN` records insufficient identity, coverage, provenance,
freshness, or owner information. `N/A` needs an applicability reason and a
reassessment trigger. The matrix does not automatically change a readiness
decision or grant authorization.
