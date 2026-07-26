# arXiv Submission Guide — spec-strata

Your readiness report says this is arXiv-ready. Here's the actual submission process.

## 1. Get an arXiv account + endorsement

- Register at https://arxiv.org/user/register (use a real academic-adjacent email if you have one — Gmail is fine but an institutional email speeds up trust)
- arXiv requires **endorsement** for your first submission in a category (e.g. `cs.CL` — Computation and Language, or `cs.AI`). As an independent researcher with no prior arXiv papers, you likely need an endorser: someone who has already published in that category.
  - Check endorsement requirements: https://arxiv.org/help/endorsement
  - If you don't know anyone, arXiv sometimes auto-qualifies you based on email domain or history — try starting a submission first; it'll tell you if endorsement is needed and give you a code to send a potential endorser.

## 2. Pick the right category

Given the paper's content (system prompts, LLM governance, comparative analysis):
- Primary: **cs.CL** (Computation and Language) or **cs.AI** (Artificial Intelligence)
- Cross-list secondary: **cs.CY** (Computers and Society) — since it touches AI governance/policy

## 3. Prepare your submission package

arXiv wants the **source**, not just a PDF — so your `.tex` file plus any assets:
```
system-prompt-taxonomy-paper.tex
(any .bib file if you use one separately, or check if refs are inline)
```
- Double-check your `.tex` compiles with a clean `pdflatex` run with **no manual intervention** — arXiv recompiles your source on their servers, it doesn't just accept your PDF.
- Remove any absolute file paths, personal comments, or draft artifacts from the `.tex` file.

## 4. Submit

1. Go to https://arxiv.org/submit
2. Upload your `.tex` source (and any figures/bib files if separate)
3. arXiv auto-compiles it — check the preview PDF matches what you expect
4. Fill in: title, abstract, authors, category, comments (optional — e.g. "9 pages")
5. Add a license — CC BY 4.0 is the most common choice for maximum shareability (arXiv itself doesn't require CC0 like your repo's code)
6. Submit — there's a **review delay** (usually next business day, sometimes longer for first-time submitters) before it goes live

## 5. After it's live

- You'll get an arXiv ID like `2607.xxxxx`
- Update `spec-strata`'s README badge:
  ```markdown
  [![arXiv](https://img.shields.io/badge/arXiv-2607.xxxxx-b31b1b.svg)](https://arxiv.org/abs/2607.xxxxx)
  ```
- Update `CITATION.cff` with the arXiv identifier
- Post it — LinkedIn, your GitHub profile pin, wherever you're building visibility. An arXiv ID is a concrete, checkable credential in a way "I wrote a paper" isn't.

## Timeline expectation

- Endorsement (if needed): hours to a few days depending on who you reach
- Submission → live: usually 1–2 business days
- Total: budget about a week end-to-end if you need an endorser from scratch
