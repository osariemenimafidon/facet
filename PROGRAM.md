# FACET

**Fuel-Adaptive Control Evidence & Transferability**

An independent research program. Founded September 2026.
Osariemen Imafidon, sole investigator · ORCID 0009-0006-3069-4674 · Independent Researcher

Built entirely from openly available federal data. Self-funded. Published openly.

---

## 1. The problem

**The fuel and the calibration are drifting apart.**

A compression-ignition engine is certified on one certification fuel and then
operated, for a useful life measured in thousands of hours, on whatever the market
supplies. That was a tolerable approximation while diesel was a narrow commodity.
It is becoming less tolerable, because the fuels now sold into the same tank no
longer share a property envelope.

The specifications make this concrete. EN 590 sets automotive diesel density at
**820–845 kg/m³** (temperate grades) with a minimum cetane number of 51. EN 15940,
which covers the paraffinic fuels sold as renewable diesel, sets **765–800 kg/m³**.
These ranges do **not overlap**. A fuel that is legally and commercially "diesel"
can arrive at the injector 5–9% less dense than the fuel the engine was calibrated
and certified on — and US renewable diesel production capacity has been climbing,
with EIA revising its 2026 production forecast upward.

Three fuel properties then propagate straight into the combustion event:

| Property | Mechanism | Consequence |
|---|---|---|
| **Density** | injection systems meter *volume*; delivered mass scales with density | fuelling error, torque and emissions shift |
| **Bulk modulus** | governs pressure-wave propagation in line and rail | injection timing shifts; the effect is documented for biodiesel in pump-line-nozzle systems |
| **Cetane number** | sets ignition delay | premixed/diffusion burn fraction changes; NOx and PM move in opposition |

Measured ignition-delay differences between B7 and neat HVO are on the order of
**2.5 ms at 550 °C**, narrowing to **0.7 ms at 650 °C** — temperature-dependent, so
the error is not a constant the calibrator can simply subtract.

**Meanwhile the margin for error is closing.** CARB's draft Tier 5 off-road
proposal, released February 2026, would cut NOx by up to **90%** and PM by up to
**75%** against current EPA Tier 4 final, phasing in **2031–2036**. Standards that
aggressive leave very little headroom for an uncompensated fuel-property shift.

## 2. The two questions

**Q1 — Technical.** Can fuel injection control adapt to actual fuel properties
closely enough to close the certified-to-in-service gap, and what must it sense to
do so — direct property measurement, inference from combustion feedback, or a
declared-blend input?

**Q2 — Methodological.** What verification evidence would allow such control to
reach production, and under what criteria can evidence generated for one engine
program be legitimately reused for another?

**Q2 is the program's centre of gravity.** Adaptive-control concepts are not scarce
in the literature; what is scarce is an accepted account of what evidence is
*sufficient*, and of when cross-program reuse is defensible rather than convenient.
The barrier between a working concept and a production calibration is the cost and
structure of verification evidence, not the novelty of the control law. That is a
validation question, and it is the question this program is built to answer.

## 3. Method commitments

These are constraints the program accepts in advance, not aspirations.

1. **Open federal data only.** Every result must be reproducible by someone with no
   access to proprietary engine data, test cells, or manufacturer cooperation.
2. **Provenance at every fetch.** Source URL, retrieval date, byte count and
   SHA-256 are logged before a file is used.
3. **No number is typed by hand.** Every figure in every document is interpolated
   from a statistics file the pipeline writes, so prose cannot drift from data.
4. **A verification gate precedes publication.** Nothing is published until the
   investigator has personally reproduced the pipeline and spot-checked outputs
   against the primary source.
5. **Findings are published whether or not they are favourable**, including
   negative results and defects found in public data.
6. **Self-funded, no sponsor.** There is no party whose interests a result could
   be shaped to serve.

## 4. What would make the program wrong

Stated in advance, so the program can fail honestly:

- If in-service fuel property variation proves **small** relative to existing
  calibration tolerance, the motivating premise collapses and the program should
  say so.
- If adaptive control turns out to be **routinely deployed already** and simply
  undocumented in public sources, the contribution reduces to documentation.
- If cross-program evidence reuse is found to be **unformalisable** — every engine
  program genuinely a special case — then Q2 has a negative answer, which is itself
  worth publishing.

## 5. Project portfolio

Status is stated honestly. Nothing below has a DOI yet.

| Project | What it is | Answers | Status |
|---|---|---|---|
| **CIDEX** | Harmonized engine-family-level panel of EPA compression-ignition certification data | Evidence base for Q1 and Q2 | **Draft built, unverified** |
| **Fuel Divergence Atlas** | State-level estimates of in-service fuel property divergence | Sizes the problem in §1 | Not started |
| **ADCVI** | Evidence map of adaptive/learning-based diesel control, scored on a validation-maturity rubric | Q2 — what evidence exists today | Not started |
| **Fuel-Related Failure Corpus** | Labelled corpus of fuel-related failure modes from open defect records | Q1 — does the gap show up in service | Not started |
| **certdata / enginefamily** | Open tooling for EPA certification records and family-name decoding | Infrastructure | Not started |

## 6. Current state — September 2026

The program is newly founded. CIDEX v1.0 is built and passes its integrity checks
but has **not** completed the verification gate and is **not** published. No DOI has
been minted. No manuscript has been submitted. This document describes a research
agenda and a first dataset in draft, and claims nothing further.
