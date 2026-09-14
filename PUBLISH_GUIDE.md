# Publishing FACET to GitHub

The repository is committed and ready. Only authentication is missing.

Commit `044c963` on branch `main`, 7 files tracked, working tree clean.

## Step 1 — create the empty repository

Go to **https://github.com/new**

- Repository name: `facet`
- Description: `FACET — Fuel-Adaptive Control Evidence & Transferability. An independent research program.`
- **Public**
- **Do not** add a README, .gitignore, or licence — this repo already has them, and adding
  any of the three creates a conflicting first commit you would then have to merge.

Click **Create repository**, then stop. Ignore the setup instructions GitHub shows next.

## Step 2 — push

Open Terminal (Applications → Utilities → Terminal) and paste these three lines,
replacing `YOUR-USERNAME`:

```bash
cd ~/Documents/facet
git remote add origin https://github.com/YOUR-USERNAME/facet.git
git push -u origin main
```

When git asks for credentials:

- **Username**: your GitHub username
- **Password**: your personal access token — *not* your GitHub password, which will be
  rejected. Create one at https://github.com/settings/personal-access-tokens/new with
  **Only select repositories → facet**, and permissions **Contents: Read and write** plus
  **Metadata: Read**. Set expiration to 7 days.

macOS will offer to save it in the keychain. Accept, and you will not be asked again.

## Step 3 — turn on GitHub Pages

In the new repository: **Settings → Pages**

- Source: **Deploy from a branch**
- Branch: **main**, folder: **/ (root)**
- Save

The site appears at `https://YOUR-USERNAME.github.io/facet/` within a minute or two. It
serves `index.html`, which is the program page.

## Step 4 — tell me the URL

Paste it back and I will update `PROGRAM.md`, the portfolio register, and the canonical
link in `index.html` to point at the real address.

---

## What is being published

| File | What it is |
|---|---|
| `README.md` | Repository front page — the thesis, the two questions, project status |
| `PROGRAM.md` | Full research agenda, method commitments, falsification conditions |
| `PORTFOLIO.md` | Project register and status vocabulary |
| `index.html` | The public program page served by GitHub Pages |
| `docs/EVIDENCE_LOG.csv` | Empty log, ready for the first real publication entry |
| `LICENSE` | CC BY 4.0 |

Nothing here claims a DOI, a submission, or a completed project. CIDEX is stated as
`Draft built`, unverified. The CIDEX dataset itself is **not** in this repository and is
not being published by these steps.
