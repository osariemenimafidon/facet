# FACET — project register

Program page: https://osariemenimafidon.github.io/facet/ · Repository: https://github.com/osariemenimafidon/facet · DOI: [10.5281/zenodo.22823180](https://doi.org/10.5281/zenodo.22823180)

Status is recorded honestly. A project moves to **Published** only when a DOI resolves.

| Project | Answers | Status | Location | Preprint | DOI |
|---|---|---|---|---|---|
| CIDEX | Evidence base, Q1 + Q2 | **Published** | `~/Documents/cidex` · [GitHub](https://github.com/osariemenimafidon/cidex) | [10.31224/8233](https://doi.org/10.31224/8233) | [10.5281/zenodo.22761791](https://doi.org/10.5281/zenodo.22761791) |
| FUELDIV | Where the certification, federal and commercial fuel envelopes fail to overlap | **Published** | `~/Documents/fueldiv` · [GitHub](https://github.com/osariemenimafidon/fueldiv) | [preprint](https://doi.org/10.5281/zenodo.22822591) | [10.5281/zenodo.22822591](https://doi.org/10.5281/zenodo.22822591) |
| FDA (Fuel Divergence Atlas) | State-level in-service divergence, consumption-weighted | **Published** | `~/Documents/fda` · [GitHub](https://github.com/osariemenimafidon/fda) | [preprint](https://doi.org/10.5281/zenodo.22822535) | [10.5281/zenodo.22822535](https://doi.org/10.5281/zenodo.22822535) |
| ADCVI | Q2 — evidence that exists today | Not started | — | — | — |
| Fuel-Related Failure Corpus | Q1 — does the gap show in service | Not started | — | — | — |
| certdata / enginefamily | Infrastructure | Not started | — | — | — |

## Status vocabulary

- **Not started** — no build spec written
- **Spec'd** — build spec written and approved, no code
- **Draft built** — pipeline runs, outputs exist, integrity checks pass
- **Verified** — investigator has reproduced the pipeline and spot-checked against source
- **Published** — deposited, DOI resolves, entry added to the evidence log

A preprint is not a status. A verified project may carry a manuscript before it carries a
DOI, and a draft project's manuscript carries the same draft stamp its data does.

Nothing skips a step. A project that fails at any step is rescheduled or deleted,
never quietly carried forward.

## Sequence rationale

CIDEX is first because the other four depend on it or on tooling built for it:
the Atlas needs the certified fleet to interpret property divergence against,
ADCVI's rubric is applied to claims about the engines CIDEX describes, the failure
corpus joins to engine families, and `certdata` / `enginefamily` are extracted from
the CIDEX pipeline rather than written separately.
