# arXiv Submission Guide — spec-strata

Your readiness report says this is arXiv-ready. Here's the actual submission process.

## 1. Get an arXiv account + endorsement

**⚠️ Policy changed Jan 21, 2026 — read this before assuming the old rules apply.**

arXiv now requires **one of two paths** for first-time submitters to a category:

- **Path A (automatic):** BOTH (1) an institutional academic/research email linked to your account, AND (2) you're already a claimed co-author on an existing accepted arXiv paper in the same endorsement domain (e.g. `cs`). You don't meet this yet — no prior arXiv papers.
- **Path B (personal endorsement):** get vouched for directly by an established arXiv author working in your subject area, who submits an endorsement code on your behalf.

Since you're a first-time independent submitter with no prior arXiv-claimed paper, **you need Path B.**

- Register at https://arxiv.org/user/register
- Start a submission, select category (`cs.CL` or `cs.AI`) — arXiv will tell you endorsement is required and generate an **endorsement code + link** to send to a prospective endorser
- Full policy: https://info.arxiv.org/help/endorsement.html

### Who to ask — a real, specific option

**Anna Neumann** (Research Centre Trust, University of Duisburg-Essen / Cambridge) is lead author of *"Prompt Governance? On Governing Technologies Governed by Natural Language"* (FAccT 2026, also on arXiv as `2606.07539`) — the exact paper your Related Work section already engages with directly. She's an active arXiv author in your subject area, which makes her a legitimate, on-topic endorser candidate — not a cold stranger-beg.

Draft outreach email:

> Subject: arXiv endorsement request — related work to your FAccT 2026 paper
>
> Dear Dr. Neumann,
>
> I'm an independent researcher who recently completed a paper on system prompts as governance artifacts — a comparative structural taxonomy across Anthropic, OpenAI, Google, and xAI's publicly available governance documents. Your FAccT 2026 paper "Prompt Governance?" is directly engaged with in my Related Work section; our studies are complementary (yours examines the stakeholder/policy literature discourse around these instruments, mine directly codes the primary documents' content).
>
> I'd like to submit this to arXiv (cs.CL) but as a first-time submitter I need a personal endorsement under arXiv's current policy. Would you be willing to review the abstract/paper and endorse the submission if it seems like a legitimate, on-topic contribution? Happy to share the full PDF.
>
> Repository: https://github.com/P-r-e-m-i-u-m/spec-strata
> Paper: https://p-r-e-m-i-u-m.github.io/spec-strata/paper/system-prompt-taxonomy-paper.pdf
>
> Thank you for considering — I understand if you're unable to help.
>
> Best,
> Syed Abdul Aman

Find her contact via the FAccT paper's author page (`anna.neumann1@uni-due.de`, per the ACM listing) or her arXiv author page at https://arxiv.org/a/neumann_a — verify the email is current before sending.

**Fallback options if she doesn't respond:**
- Post an endorsement request (with your generated code) to the Hugging Face forums (`discuss.huggingface.co`) or r/MachineLearning — this is common, accepted practice, several examples exist
- Check if any of your certification instructors/mentors (IBM, Databricks, Anthropic, Google, BCG programs) have arXiv-published research staff who might endorse
- LPU faculty, once you're further into your BCA — a professor publishing in `cs.CL`/`cs.AI` at your own institution is a strong, standard option

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
