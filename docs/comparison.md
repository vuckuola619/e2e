# Documentary comparison

Status: `REFERENCE`. This page records a read-only comparison of public,
revision-pinned documentation and repository metadata captured on 2026-09-16.
Every runtime benchmark result is `NOT_RUN`. No upstream repository was
installed, executed, security-tested, or compared for effectiveness.

The machine-readable companion is
[`research/comparison-2026-09-16.json`](../research/comparison-2026-09-16.json).
It retains the complete metadata snapshot, source hashes, release endpoint
results, capability observations, and limitations.

## Scope and method

The source set combines high-star workflow repositories with two public
readiness references and the pre-lifecycle `e2e` baseline. The review read each
commit-pinned README and selected first-party documentation linked by the
research notes. It did not inspect every extension, plugin, release artifact,
or source file.

`NOT_EVIDENCED_IN_REVIEWED_SCOPE` means that the capability was not documented
in the specific first-party pages reviewed. It does not mean the repository,
an extension, or a custom workflow lacks that capability. `PARTIAL` describes
an optional path or a documented sub-scope. `OUT_OF_SCOPE` describes a stated
boundary or a redirect record. `EXPLICIT` describes a capability documented in
the inspected material.

Stars, forks, push times, and release metadata are dated observations. Stars
are a popularity signal only. They are not a quality, safety, maturity,
effectiveness, or support score. “No release returned” is the captured
latest-release API result; it is not an inactivity conclusion.

## Frozen metadata snapshot (2026-09-16 04:06–04:08 UTC)

This compact table records the requested source, its canonical repository,
exact star count, a short link to the observed default-branch HEAD, the HEAD
commit date, the captured latest-release result, and archive state. Every
repository has `runtime_benchmark_status: NOT_RUN`. The JSON dataset retains
forks, full SHAs, precise observation timestamps, README blob/hash values,
metadata endpoints, push times, and release endpoint details.

| Requested source → canonical repository | Stars | HEAD (branch) | Commit date | Latest release result | Archived |
| --- | ---: | --- | --- | --- | :---: |
| `obra/superpowers` → [obra/superpowers](https://github.com/obra/superpowers) | 287,238 | [`b36e082`](https://github.com/obra/superpowers/commit/b36e0829c6d0140e93cfef2ca599b1b07d4a7797) (`main`) | 2026-08-12 | `PUBLISHED` [`v6.3.0`](https://github.com/obra/superpowers/releases/tag/v6.3.0) | No |
| `github/spec-kit` → [github/spec-kit](https://github.com/github/spec-kit) | 137,097 | [`1d5106f`](https://github.com/github/spec-kit/commit/1d5106f59e1b148ee23ab136638932dd790ff1b6) (`main`) | 2026-09-15 | `PUBLISHED` [`v1.0.7`](https://github.com/github/spec-kit/releases/tag/v1.0.7) | No |
| `Fission-AI/OpenSpec` → [Fission-AI/OpenSpec](https://github.com/Fission-AI/OpenSpec) | 68,411 | [`9d4e597`](https://github.com/Fission-AI/OpenSpec/commit/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461) (`main`) | 2026-09-09 | `PUBLISHED` [`v1.13.0`](https://github.com/Fission-AI/OpenSpec/releases/tag/v1.13.0) | No |
| `bmad-code-org/BMAD-METHOD` → [bmad-code-org/BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD) | 53,067 | [`0a00053`](https://github.com/bmad-code-org/BMAD-METHOD/commit/0a00053409731db811f2595ceb521dff9dde9a19) (`main`) | 2026-09-15 | `PUBLISHED` [`v6.12.0`](https://github.com/bmad-code-org/BMAD-METHOD/releases/tag/v6.12.0) | No |
| `affaan-m/ecc` → [affaan-m/ECC](https://github.com/affaan-m/ECC) | 259,437 | [`8321021`](https://github.com/affaan-m/ECC/commit/8321021c54d670126ce3b2969d5deb880b4b0c2a) (`main`) | 2026-09-12 | `PUBLISHED` [`v2.2.1`](https://github.com/affaan-m/ECC/releases/tag/v2.2.1) | No |
| `garrytan/gstack` → [garrytan/gstack](https://github.com/garrytan/gstack) | 133,255 | [`85b8c03`](https://github.com/garrytan/gstack/commit/85b8c038fc0002a1549789ea018e924c1d335de4) (`main`) | 2026-09-15 | `NONE_RETURNED` (HTTP 404) | No |
| `sickn33/antigravity-awesome-skills` → [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills) | 46,472 | [`69906dd`](https://github.com/sickn33/agentic-awesome-skills/commit/69906dde999aaa0f3d173f0e3d5bcdb84c87a294) (`main`) | 2026-09-15 | `PUBLISHED` [`v17.3.0`](https://github.com/sickn33/agentic-awesome-skills/releases/tag/v17.3.0) | No |
| `gsd-build/get-shit-done` → [gsd-build/get-shit-done](https://github.com/gsd-build/get-shit-done) | 64,529 | [`bdcaab2`](https://github.com/gsd-build/get-shit-done/commit/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815) (`main`) | 2026-05-31 | `PUBLISHED` historical [`v1.42.3`](https://github.com/gsd-build/get-shit-done/releases/tag/v1.42.3) | Yes |
| `Taimoorkhan1122/prod-readiness` → [Taimoorkhan1122/prod-readiness](https://github.com/Taimoorkhan1122/prod-readiness) | 28 | [`7a27828`](https://github.com/Taimoorkhan1122/prod-readiness/commit/7a2782890753d941a09bcdedae4c51c24c5482ed) (`main`) | 2026-09-11 | `NONE_RETURNED` (HTTP 404) | No |
| `mercari/production-readiness-checklist` → [mercari/production-readiness-checklist](https://github.com/mercari/production-readiness-checklist) | 944 | [`5834a23`](https://github.com/mercari/production-readiness-checklist/commit/5834a23b508335d49d94e4dd8055ed1c58236b8e) (`master`) | 2021-05-17 | `NONE_RETURNED` (HTTP 404) | No |
| `vuckuola619/e2e` → [vuckuola619/e2e](https://github.com/vuckuola619/e2e) | 0 | [`08e6e66`](https://github.com/vuckuola619/e2e/commit/08e6e66dfe93c18a7be81b1943916903f7c030b9) (`main`) | 2026-09-16 | `NONE_RETURNED` (HTTP 404) | No |
| `open-gsd/gsd-core` → [open-gsd/gsd-core](https://github.com/open-gsd/gsd-core) | 9,493 | [`092d925`](https://github.com/open-gsd/gsd-core/commit/092d9256b89c9f6055928f3fd21b633036704dbc) (`next`) | 2026-09-16 | `PUBLISHED` [`v1.14.0`](https://github.com/open-gsd/gsd-core/releases/tag/v1.14.0) | No |

## Product-type grouping

The sources are different kinds of products. Comparing unlike boundaries as a
single score would be misleading.

| Product type | Sources in this snapshot | What the group supplies |
| --- | --- | --- |
| Delivery orchestrator | Spec Kit, OpenSpec, BMAD Method, Superpowers, ECC, gstack, GSD Core | Product or engineering workflow, planning artifacts, implementation/review steps, or delivery automation. |
| Skill selection/distribution | Agentic Awesome Skills (requested as Antigravity Awesome Skills) | Catalog, selection, packaging, and optional workflow playbooks. |
| Readiness audit | prod-readiness, `e2e` baseline | Read-only evidence review or readiness guidance with explicit limitations. |
| Readiness checklist | Mercari production-readiness checklist | Static, human-reviewed technical readiness criteria. |
| Archived redirect | archived GSD predecessor | A migration pointer; current behavior belongs to GSD Core. |

## Capability matrix

The matrix describes documentation observed in the reviewed sources. It is not
a runtime benchmark, quality ranking, or global absence claim. Every cell links
to a commit-pinned primary source; the per-source notes below add selected
first-party links where they clarify scope.

Legend: `E` = `EXPLICIT`, `P` = `PARTIAL`, `N` =
`NOT_EVIDENCED_IN_REVIEWED_SCOPE`, and `O` = `OUT_OF_SCOPE`.

| Source | Discovery / definition | Plan / spec | Build / execute | Review | Verification / readiness | Release / operations | Install / runtime |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Spec Kit | [E](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) | [E](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) | [E](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) | [E](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) | [E](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) | [N](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) | [E](https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md) |
| OpenSpec | [P](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/README.md) | [E](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/README.md) | [E](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/README.md) | [E](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/docs/reviewing-changes.md) | [E](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/docs/commands.md) | [N](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/README.md) | [E](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/README.md) |
| BMAD Method | [E](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) | [E](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) | [E](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) | [E](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) | [E](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) | [P](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) | [E](https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md) |
| Superpowers | [P](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) | [E](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) | [E](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) | [E](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) | [E](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) | [N](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) | [E](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md) |
| ECC | [P](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) | [E](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) | [E](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) | [E](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) | [E](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) | [P](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) | [E](https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md) |
| gstack | [E](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md) | [E](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md) | [P](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md) | [E](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/docs/skills.md) | [E](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md) | [E](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md) | [E](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md) |
| Agentic Awesome Skills | [P](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/README.md) | [E](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/docs/users/workflows.md) | [E](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/docs/users/workflows.md) | [E](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/README.md) | [P](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/docs/users/aas-core.md) | [P](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/docs/users/workflows.md) | [E](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/README.md) |
| Archived GSD predecessor | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) | [O](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md) |
| prod-readiness | [O](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) | [O](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) | [O](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) | [E](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) | [E](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) | [P](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) | [E](https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md) |
| Mercari checklist | [N](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) | [P](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) | [O](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) | [E](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) | [E](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) | [E](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) | [O](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md) |
| e2e pre-lifecycle baseline | [N](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) | [E](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) | [P](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) | [E](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) | [E](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) | [P](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) | [N](https://github.com/vuckuola619/e2e/blob/08e6e66dfe93c18a7be81b1943916903f7c030b9/README.md) |
| GSD Core | [E](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) | [E](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) | [E](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) | [P](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) | [E](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) | [P](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) | [E](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md) |

## Source notes

The notes below summarize documented focus, product-lifecycle strengths, and
integration limits. They are deliberately short; the dataset records the
structured observations and source links.

### GitHub Spec Kit

Spec Kit documents separate idea-assessment, spec-driven, and bug-fixing paths.
The idea path frames a problem through research and shaping before a decision;
the spec path carries requirements through planning, tasks, implementation, and
convergence. Persistent Markdown artifacts and valid negative outcomes are
useful models for lifecycle handoffs. The reviewed material centers on product
definition through implementation and convergence. Dedicated release,
steady-state operations, and outcome measurement were
`NOT_EVIDENCED_IN_REVIEWED_SCOPE`. For `e2e`, import its artifacts as proposed
intent or observations and still apply subject identity and proof-set rules.

Sources: [pinned README][sk], [assessment guide](https://github.github.io/spec-kit/guides/assessment.html), [agentic SDD reference](https://github.github.io/spec-kit/reference/agentic-sdd.html), and [workflow reference](https://github.github.io/spec-kit/reference/workflows.html).

### Fission-AI OpenSpec

OpenSpec documents an optional exploration path and a change-local set of
proposal, requirements/scenarios, design, and task artifacts. Apply, verify,
sync, update, and archive support fluid revision without making every phase a
rigid gate. This is useful for preserving current specifications separately
from in-flight changes. The reviewed core material focuses on change shaping,
implementation, verification, and archive; structured product discovery,
steady-state operations, and post-launch measurement were
`NOT_EVIDENCED_IN_REVIEWED_SCOPE`. Imported task completion remains work
tracking until the `e2e` evidence policy evaluates it.

Sources: [pinned README][os], [reviewing changes](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/docs/reviewing-changes.md), and [commands](https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/docs/commands.md).

### BMAD Method

BMAD documents a right-sized planning path from idea framing and research to
brief/PRD, UX, architecture, stories, build, verification, and learn/adjust.
Its product, design, engineering, and retrospective perspectives are useful
inputs for the lifecycle axis. The reviewed pages do not establish that each
listed module is installed or executed in one host, and their product outcome
signals are guidance rather than observed demand. `e2e` can adapt its
progressive planning depth while keeping evidence identity, named human
acceptance, and release authorization separate.

Source: [pinned README][bmad]. The public planning guide is [Choose a Planning Path](https://docs.bmad-method.org/plan/choose-a-planning-path/).

### obra/superpowers

Superpowers documents brainstorming with human intent approval, file-specific
planning, isolated implementation, TDD, fresh-context review, and verification
before completion. Small task units and independent review are useful lifecycle
handoffs for an implementation phase. The reviewed path is software-development
centered; structured market/user research, product-outcome planning, production
operations, and post-release measurement were
`NOT_EVIDENCED_IN_REVIEWED_SCOPE`. `e2e` should preserve the human gate and
fresh verification while keeping its technical decision distinct from release
authorization.

Sources: [pinned README][sp], [writing plans](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/skills/writing-plans/SKILL.md), [subagent development](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/skills/subagent-driven-development/SKILL.md), and [verification](https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/skills/verification-before-completion/SKILL.md).

### affaan-m ECC

ECC documents a plan, test, implement, review, verify, remember, and improve
trail, with separate skills, agents, rules, hooks, and context-management
choices. Packaging, host adapters, dry-run, doctor, repair, uninstall, and
hook consent are relevant to a future e2e package contract. Its reviewed
primary flow contains feature planning and research but a required problem-
discovery stage was `NOT_EVIDENCED_IN_REVIEWED_SCOPE`; operations material is
also partial. `e2e` can adopt small default profiles and explicit host
capabilities without treating package installation as proof of product quality.

Source: [pinned README][ecc]. README-described counts and production-use
claims were not independently validated.

### garrytan gstack

gstack documents problem interrogation, role-specific planning, a sprint from
thinking through reflection, browser QA, code/design/DX/security review, ship,
deployment, canary, and monitoring. Its artifact flow is a useful example of
linking product framing to implementation and operational feedback. Its
installation, uninstall path, and browser runtime are explicitly documented;
the setup follows a moving branch and the latest-release endpoint returned no
release. These are packaging observations, not an inactivity claim. Host
qualification and execution remain `NOT_RUN`. `e2e` can adapt the explicit
product-intake and browser evidence ideas while keeping browser availability
and operational claims inside their declared scope.

Sources: [pinned README][gst] and [pinned skill docs](https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/docs/skills.md). No runtime or productivity result was reproduced.

### Agentic Awesome Skills

The requested Antigravity name resolves to Agentic Awesome Skills. Its Core
focuses on catalog inspection, agent-selected skills, pinned stack identity,
structural validation, and installation planning. Workflow playbooks add
planning, implementation, QA, security, deployment, and rollback guidance, but
Core does not itself certify semantic completeness or operate as one product
executor. `e2e` can use a small, selected module set and resource-closure
metadata while retaining one canonical router and evaluator.

Sources: [pinned README][aas], [Core guide](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/docs/users/aas-core.md), and [workflow guide](https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/docs/users/workflows.md).

### GSD migration warning: archived predecessor and active Core

The archived `gsd-build/get-shit-done` repository is a migration pointer. Do
not treat its star count, historical release, or README as current behavior.
Current comparison uses the separate `open-gsd/gsd-core` record, whose captured
default branch is `next` and whose latest published release is v1.14.0. The two
records remain separate in the dataset, with `redirects_to` on the archived
record.

GSD Core documents project intake, research, requirements, atomic plans,
dependency waves, fresh-context execution, verification, UAT, summaries, and a
ship step that opens a pull request. It provides a concrete lifecycle spine for
future e2e runtime work. The inspected core loop did not evidence a first-class
steady-state production operations stage. A pinned install guide and tutorial
also describe different Node prerequisites; the discrepancy remains recorded.

Sources: [archived README][gsd-old], [active Core README][gsd-core], [first-project tutorial](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/docs/tutorials/your-first-project.md), [phase loop](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/docs/explanation/the-phase-loop.md), and [install guide](https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/docs/how-to/install-on-your-runtime.md).

### Taimoorkhan1122 prod-readiness

prod-readiness is a read-only repository audit with specialist lenses, an
absence ledger, finding validation, a resumable trail, and a go/no-go report.
Its distinction between confirmed, not found, and unverified observations is a
useful model for e2e evidence. It deliberately stops before implementation,
remediation, and deployment; its product discovery and implementation planning
are `OUT_OF_SCOPE`. The documented native plugin and manual-copy paths are an
explicit install/runtime surface, but require host-specific qualification,
which remains `NOT_RUN`. `e2e` can adapt the evidence ledger and read-only
boundary without treating source silence as proof about live systems.

Source: [pinned README][prod]. The repository had no published release returned
by the captured endpoint; this does not establish inactivity.

### Mercari production-readiness checklist

The Mercari public checklist places review at design and pre-production points,
uses service criticality/SLO levels, asks teams to attach evidence or justify
N/A, and covers build/deploy, rollback, observability, on-call, capacity,
recovery, and data stores. It is a static, human-reviewed reference rather
than an executable engine. Product discovery and implementation are outside
the reviewed repository scope. `e2e` can adapt policy profiles and re-check
design controls at release while retaining portable identity and evidence
semantics.

Sources: [README][merc], [design checklist](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/docs/references/design-checklist.md), [pre-production checklist](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/docs/references/pre-production-checklist.md), and [review guide](https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/docs/guides/check-production-readiness.md).

### e2e pre-lifecycle baseline

The self record is the README at `08e6e66`, captured before lifecycle edits.
That baseline documents readiness planning, 16 assurance domains, evidence
identity, freshness, proof sets, four readiness decisions, and the boundary
between technical readiness and authorization. It also documents a host-led
`IMPLEMENT_AND_VERIFY` path, so build/execute is `PARTIAL`: no bundled executor,
package, or qualified host adapter was evidenced. It does not document product
discovery. This revision adds lifecycle guidance after the captured baseline;
that guidance belongs to the current working tree and must not be attributed to
this historical self baseline.

## Prioritized direction for e2e

The comparison suggests a bounded sequence of design work:

1. Keep a first-class product-intake artifact for problem, affected users or
   operators, alternatives, outcome, constraints, and rejected assumptions.
2. Add typed lifecycle handoffs to the existing assurance chain without making
   all ten phases mandatory for a small, clear change.
3. Build evidence and state identity before broad producer adapters: immutable
   attempts, subject matching, freshness, status preservation, checkpoints,
   proof selection, and deterministic decisions.
4. Keep one router and one evaluator. Treat skill catalogs, browser checks,
   scanners, graphs, and context transforms as scoped inputs.
5. Qualify an exact package and host before making installation or compatibility
   claims; preserve dry-run, resource closure, permissions, and uninstall
   boundaries.
6. Add release and post-release signals incrementally, with artifact identity,
   rollout, monitoring, rollback, recovery, and iteration links.
7. Run the controlled protocol in [`docs/benchmark-protocol.md`](benchmark-protocol.md)
   before making quality, time, cost, token, or cross-host claims.

## Limits and related material

This is documentary comparison, not a winner declaration. No quality score is
derived from stars, documentation breadth, release count, or the matrix. The
prior 36-source ecosystem research and one synthetic case were not a
head-to-head benchmark. Native installation and guidance-only review are
different experimental tracks.

Use these related records:

- [comparison dataset](../research/comparison-2026-09-16.json), including all
  12 frozen metadata records;
- [36-source ecosystem register](../research/upstreams.json);
- [ecosystem curation notes](ecosystem.md);
- [lifecycle guide](../skills/e2e/references/lifecycle.md); and
- [benchmark protocol](benchmark-protocol.md).

The companion protocol remains `PROPOSED` and `NOT_RUN`. Until it is executed,
runtime behavior, effectiveness, installation success, time savings, cost,
token savings, cross-host equivalence, and release quality remain unknown.

[sp]: https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/README.md
[sk]: https://github.com/github/spec-kit/blob/1d5106f59e1b148ee23ab136638932dd790ff1b6/README.md
[os]: https://github.com/Fission-AI/OpenSpec/blob/9d4e5974e5c0d9a09b9c6c1e1eb0975e80ec4461/README.md
[bmad]: https://github.com/bmad-code-org/BMAD-METHOD/blob/0a00053409731db811f2595ceb521dff9dde9a19/README.md
[ecc]: https://github.com/affaan-m/ECC/blob/8321021c54d670126ce3b2969d5deb880b4b0c2a/README.md
[gst]: https://github.com/garrytan/gstack/blob/85b8c038fc0002a1549789ea018e924c1d335de4/README.md
[aas]: https://github.com/sickn33/agentic-awesome-skills/blob/69906dde999aaa0f3d173f0e3d5bcdb84c87a294/README.md
[gsd-old]: https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/README.md
[gsd-core]: https://github.com/open-gsd/gsd-core/blob/092d9256b89c9f6055928f3fd21b633036704dbc/README.md
[prod]: https://github.com/Taimoorkhan1122/prod-readiness/blob/7a2782890753d941a09bcdedae4c51c24c5482ed/README.md
[merc]: https://github.com/mercari/production-readiness-checklist/blob/5834a23b508335d49d94e4dd8055ed1c58236b8e/README.md
