# Getting an ORCID iD and a DOI

Both are free, and neither depends on anyone approving you. Do them alongside the arXiv process, not instead of it.

## 1. ORCID iD (about five minutes)

An ORCID is a permanent ID for you, the way a DOI is for a paper. Applications and grant forms ask for it, and some reviewers look it up.

1. Register at <https://orcid.org/register>.
2. Set your profile to public so people can actually check it.
3. Add the work: **Works → Add works → Add manually**. Use the paper's title, your name, 2026, and the repo link.
4. Once you have the ID, add it to `CITATION.cff` under your name:

   ```yaml
   authors:
     - family-names: Aman
       given-names: "Syed Abdul"
       orcid: "https://orcid.org/YOUR-REAL-ID"
   ```

   Don't commit a made-up one. Zenodo reads that file and would publish it.

5. Put it in your GitHub bio and portfolio too.

## 2. Zenodo DOI (about ten minutes, plus one release)

Zenodo, run by CERN, gives the repo a permanent DOI that keeps working even if the GitHub repo moves. The repo already has the metadata it needs (`CITATION.cff` and `.zenodo.json`).

1. Push your latest changes first. Zenodo snapshots the repo at the moment of the release, so you want the final wording in there.
2. Log in at <https://zenodo.org> with your GitHub account and authorize it.
3. Go to <https://zenodo.org/account/settings/github/>, find `spec-strata`, and switch it on.
4. Cut a release. Zenodo does nothing until there is one:

   ```powershell
   git tag -a v1.0.0 -m "First public release"
   git push origin v1.0.0
   ```

   Then on GitHub: **Releases → Draft a new release**, choose `v1.0.0`, title it "v1.0.0", and publish.
5. A minute or two later Zenodo mints the DOI. Copy the badge from the same Zenodo settings page and swap it in for the "DOI pending" badge at the top of the README.
6. Add the DOI to `CITATION.cff` as well.

The DOI will look like `https://doi.org/10.5281/zenodo.XXXXXXX`.

## Why bother

A DOI and an ORCID make the work citable and the author checkable, and neither needs a stranger to say yes, unlike an arXiv endorsement. They're worth having on a grad application or a program proposal.
