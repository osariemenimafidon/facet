# Minting DOIs for FACET, CIDEX and FUELDIV

Written 2026-09-16. Everything that could be automated has been; what remains needs your
Zenodo account and takes about fifteen minutes in one sitting.

## Why this is not automated

zenodo.org is refused by the network policy on this machine and in the cloud sandbox at
the CONNECT stage — before TLS, before any credential is offered. A Zenodo API token
therefore cannot help: the request never reaches Zenodo to be authenticated.

The route that works sends nothing to Zenodo from here. You link Zenodo to GitHub once,
GitHub notifies Zenodo when you publish a release, and Zenodo pulls the archive from
GitHub's servers and mints the DOI there.

**Order matters.** Zenodo only archives releases published *after* the repository switch
is turned on. A release cut first is invisible to it and has to be deleted and redone.

---

## Step 1 — Link Zenodo to GitHub

1. Go to **https://zenodo.org** and sign in. Use *Log in with GitHub* if you have not made
   a Zenodo account before; it creates one and links it in the same action.
2. Go to **https://zenodo.org/account/settings/github/**
3. If it shows no repositories, click **Sync now** and wait a few seconds.
4. Turn the switch **ON** for all three:
   - `osariemenimafidon/facet`
   - `osariemenimafidon/cidex`
   - `osariemenimafidon/fueldiv`

Leave this tab open. You will come back to it.

## Step 2 — Push the three commits

Two are unpushed. In Terminal:

```bash
cd ~/Documents/facet   && git push origin main
cd ~/Documents/fueldiv && git push origin main
cd ~/Documents/cidex   && git status   # already pushed; should say up to date
```

If git asks for a password, it wants a personal access token, not your GitHub password.

## Step 3 — Cut one release per repository

For each repository, go to its **Releases** page and click **Draft a new release**:

- https://github.com/osariemenimafidon/facet/releases/new
- https://github.com/osariemenimafidon/cidex/releases/new
- https://github.com/osariemenimafidon/fueldiv/releases/new

For each one:

| Field | Value |
|---|---|
| Choose a tag | type `v1.0.0`, then click **Create new tag: v1.0.0 on publish** |
| Target | `main` |
| Release title | see below |
| Description | see below |
| Set as the latest release | checked |
| Set as a pre-release | **un**checked — a pre-release is still archived, but it reads as provisional |

Then **Publish release**.

> **CIDEX already has a tag `v1.0`** pointing at an older commit, from before the technical
> report and the preprint existed. Do not reuse it. Create `v1.0.0` as above; it will point
> at the current commit, which is the one you want archived.

### Titles and descriptions

**facet — `v1.0.0`**

> Title: `FACET v1.0.0 — program statement, portfolio and evidence log`
>
> Description:
> First tagged version of the FACET research program: the program statement and method
> commitments, the project register, the evidence log, and the program page as published.
> At this version two constituent projects are verified and public (CIDEX and FUELDIV) and
> one is built but unverified; no constituent project holds a DOI.

**cidex — `v1.0.0`**

> Title: `CIDEX v1.0.0 — harmonized EPA compression-ignition certification panel`
>
> Description:
> 8,627 engine families, 9,794 configurations and 94,869 emission records from 108
> manufacturers, model years 2011–2027, harmonized from EPA's two structurally
> incompatible source workbooks into a single schema, with 2,541 resolved certification
> lineages. Verification gate signed. Includes the full pipeline, a technical report, a
> data-paper preprint, a codebook and a provenance log. Units are preserved as certified
> and never silently converted; read LIMITATIONS.md before use.

**fueldiv — `v1.0.0`**

> Title: `FUELDIV v1.0.0 — specification divergence register`
>
> Description:
> Ten injection-relevant diesel fuel properties, each with its 40 CFR 1065.703
> certification envelope, its 40 CFR 1090 in-market envelope, a section-level citation for
> both, a stated physical mechanism and a gap class. Four properties are constrained by
> neither regulation; none of the ten is measured in service by any federal programme.
> Includes envelope overlap arithmetic over 24 property-standard pairs — among them an
> exactly zero overlap between the certification fuel's density envelope and EN 15940's —
> and an exposure join to 8,354 certified engine families. Verification gate signed.

## Step 4 — Collect the DOIs

Return to **https://zenodo.org/account/settings/github/**. Each enabled repository now
shows a DOI badge. Within a minute or two of publishing each release you will have three
DOIs of the form `10.5281/zenodo.XXXXXXX`.

Note that Zenodo issues **two** DOIs per repository: a *concept* DOI that always resolves
to the newest version, and a *version* DOI fixed to v1.0.0. Cite the concept DOI when you
mean the project, the version DOI when you mean exactly what you deposited.

## Step 5 — Bring the DOIs back

Send me the three DOIs and I will:

- record each in `PORTFOLIO.md` and move the project's status from `Verified` to
  `Published`, which the status vocabulary says happens only when a DOI resolves;
- add a row per deposit to `docs/EVIDENCE_LOG.csv` with date, identifier, URL and venue;
- add the DOI to each project's `CITATION.cff` and to its README badge;
- write the dataset DOI into each preprint's data-availability section, which currently
  says the DOI is not yet assigned — that sentence is generated, so it rewrites itself
  once `docs/DOI.txt` exists in the project.

## What is already done

- `.zenodo.json` in all three repositories, so the deposit carries a proper title,
  your ORCID, keywords, licence and related identifiers rather than the repository name
  and nothing else. Every figure in those descriptions is checked against the pipelines'
  own outputs.
- `CITATION.cff` in all three.
- All three working trees clean and committed.
- FDA is deliberately excluded. It is unverified, every document in it carries a draft
  stamp, and its publication gate blocks. It should not be deposited until you have
  checked its component property envelopes against their governing specifications.
