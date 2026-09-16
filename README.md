# FACET

**Fuel-Adaptive Control Evidence & Transferability**

An independent research program on fuel-property-adaptive fuel injection control for
heavy-duty and off-highway diesel engines, and on the verification evidence and
cross-program applicability criteria that allow such control to reach production.

Founded September 2026 · Osariemen Imafidon, sole investigator
[ORCID 0009-0006-3069-4674](https://orcid.org/0009-0006-3069-4674) · Independent Researcher

Built entirely from openly available federal data. Self-funded. Published openly.

**Program page: https://osariemenimafidon.github.io/facet/**

---

## The thesis in one fact

A compression-ignition engine is certified on one fuel and then operated, for thousands of
hours, on whatever the market supplies.

| Specification | Covers | Density at 15 °C |
|---|---|---|
| EN 590 (temperate) | petroleum automotive diesel | **820–845 kg/m³** |
| EN 15940 | paraffinic / renewable diesel | **765–800 kg/m³** |

These ranges do not overlap. A fuel that is legally and commercially "diesel" can arrive at
the injector 5–9% less dense than the fuel the engine was calibrated and certified on — and
injection systems meter volume, so delivered mass scales with density.

## The two questions

- **Q1 — Technical.** Can injection control adapt to actual fuel properties closely enough
  to close the certified-to-in-service gap, and what must it sense to do so?
- **Q2 — Methodological.** What verification evidence would allow such control to reach
  production, and under what criteria can evidence generated for one engine program be
  legitimately reused for another?

Q2 is the program's centre of gravity. See [`PROGRAM.md`](PROGRAM.md) for the full agenda,
method commitments, and the conditions under which this program would be wrong.

## Projects

See [`PORTFOLIO.md`](PORTFOLIO.md). Status vocabulary, in order, with no step skipped:

`Not started` → `Spec'd` → `Draft built` → `Verified` → `Published (DOI resolves)`

Two projects are at `Verified`: **CIDEX**, whose pipeline has been reproduced and whose
spot-checks were confirmed against EPA's own certificate tool, and **FUELDIV**, whose
commercial standard values were confirmed against the standards themselves. Both are
public on GitHub and both carry a technical preprint. The **Fuel Divergence Atlas** is at
`Draft built`: its pipeline runs and its integrity checks pass, but its component property
envelopes have not been checked against their governing specifications, so its publication
gate blocks and every document in it carries a draft stamp.

**Nothing in this program has a DOI yet, and no manuscript has been submitted.** Neither
is an oversight: a DOI requires a deposit and a submission is a personal attestation. Both
are the investigator's to make.

## Licence

Content and documentation: [CC BY 4.0](LICENSE). Code in project repositories: MIT.
