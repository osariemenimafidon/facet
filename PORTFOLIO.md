# FACET — project register

Program page: https://osariemenimafidon.github.io/facet/ · Repository: https://github.com/osariemenimafidon/facet

Status is recorded honestly. A project moves to **Published** only when a DOI resolves.

| Project | Answers | Status | Location | DOI |
|---|---|---|---|---|
| CIDEX | Evidence base, Q1 + Q2 | Draft built, unverified | `~/Documents/cidex` | — |
| Fuel Divergence Atlas | Sizes the problem | Not started | — | — |
| ADCVI | Q2 — evidence that exists today | Not started | — | — |
| Fuel-Related Failure Corpus | Q1 — does the gap show in service | Not started | — | — |
| certdata / enginefamily | Infrastructure | Not started | — | — |

## Status vocabulary

- **Not started** — no build spec written
- **Spec'd** — build spec written and approved, no code
- **Draft built** — pipeline runs, outputs exist, integrity checks pass
- **Verified** — investigator has reproduced the pipeline and spot-checked against source
- **Published** — deposited, DOI resolves, entry added to the evidence log

Nothing skips a step. A project that fails at any step is rescheduled or deleted,
never quietly carried forward.

## Sequence rationale

CIDEX is first because the other four depend on it or on tooling built for it:
the Atlas needs the certified fleet to interpret property divergence against,
ADCVI's rubric is applied to claims about the engines CIDEX describes, the failure
corpus joins to engine families, and `certdata` / `enginefamily` are extracted from
the CIDEX pipeline rather than written separately.
