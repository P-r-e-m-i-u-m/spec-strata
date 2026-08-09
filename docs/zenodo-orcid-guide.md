# Getting a DOI (Zenodo) and an ORCID iD

Both of these are free, don't depend on arXiv's endorsement bottleneck, and are things grad admissions / GSoC reviewers specifically check for. Do these in parallel with the arXiv process, not instead of it.

---

## Part 1 — ORCID iD (do this first, takes 5 minutes)

ORCID is a permanent, unique researcher ID (like a DOI, but for *you* instead of a paper). It's free, standard in every field, and every future paper/grant/application will ask for it.

1. Go to https://orcid.org/register
2. Fill in name, email, create password
3. Set your visibility settings to **public** (so it's actually checkable)
4. Once registered, you get an ID like `0000-0000-0000-0000`
5. Add your `spec-strata` work to your ORCID record manually: **Works → Add works → Add manually** — fill in the title, your name, 2026, and link to `https://github.com/P-r-e-m-i-u-m/spec-strata`

**Then:**
- Add your ORCID iD to `CITATION.cff` (I've already added the field below — just fill in your real ID once you have it)
- Add it to your GitHub profile bio and portfolio site

---

## Part 2 — Zenodo DOI (do this after ORCID, takes ~10 minutes + 1 GitHub release)

Zenodo (run by CERN/OpenAIRE) gives your repository a permanent, citable DOI — independent of GitHub staying online, independent of arXiv accepting you. This repo already has the metadata files Zenodo needs (`CITATION.cff` and `.zenodo.json`).

### Steps

1. Go to https://zenodo.org and log in **with your GitHub account** (top right → Log in → GitHub)
2. Authorize Zenodo to access your GitHub account when prompted
3. Go to https://zenodo.org/account/settings/github/
4. Find `spec-strata` in your repo list and toggle it **ON**
5. Back in your local repo, create an actual GitHub Release (this is what triggers the DOI — Zenodo does nothing until you cut a release):
   ```powershell
   git tag -a v1.0.0 -m "Initial public release"
   git push origin v1.0.0
   ```
   Then on GitHub: **Releases → Draft a new release** → choose tag `v1.0.0` → title "v1.0.0 — Initial release" → **Publish release**
6. Within a minute or two, Zenodo mints a DOI automatically using your `.zenodo.json` metadata
7. Find it at https://zenodo.org/account/settings/github/ → click your repo → copy the DOI badge markdown
8. Add that badge to the top of your README, right next to the license badge

### After you have the DOI

- Update `CITATION.cff` with the DOI
- Cite it properly going forward: `https://doi.org/10.5281/zenodo.XXXXXXX` — this is now a permanent link that resolves even if GitHub disappears

---

## Why both matter for your goals specifically

- **Grad admissions (Fall 2028 target):** A DOI + ORCID signal "this person operates like a real researcher," independent of whether arXiv's endorsement process succeeds quickly. Admissions readers check ORCID profiles.
- **GSoC 2027:** Project proposals that link to a DOI'd, citable prior work are stronger than ones linking to just a GitHub repo.
- **Zero dependency on anyone else.** Unlike the arXiv endorsement (which needs a stranger's approval), both of these are 100% in your control today.
