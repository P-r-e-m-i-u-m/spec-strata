# Submitting to arXiv

The paper compiles cleanly from its LaTeX source, so the technical side is easy. The hard part is getting an endorsement.

## 1. Endorsement

arXiv tightened its rules in January 2026. A first-time submitter now gets in one of two ways:

- **Automatically**, if you have an institutional academic or research email *and* you're already a claimed co-author on an accepted arXiv paper in the same area. You don't have the second part yet.
- **By personal endorsement** from an established arXiv author in your subject area, who vouches for you using a code arXiv generates.

So you need a personal endorsement.

Steps:

1. Register at <https://arxiv.org/user/register>.
2. Start a submission and pick `cs.CL` as the main category. Cross-list `cs.AI` and `cs.CY` if you want. arXiv will tell you endorsement is needed and give you a code and link to send to an endorser.
3. Policy details: <https://info.arxiv.org/help/endorsement.html>.

## 2. Who to ask

Start with someone whose work you already cite. **Anna Neumann** is the lead author of [*Prompt Governance? On Governing Technologies Governed by Natural Language*](https://arxiv.org/abs/2606.07539) (FAccT 2026), the closest prior work to yours. Your Related Work section engages with it directly, so this isn't a cold ask.

Find her current email on the paper's first page or her arXiv author page, and check it's current before you send anything. I haven't verified a contact address.

A draft you can change:

> **Subject:** arXiv endorsement for a paper that builds on your FAccT 2026 work
>
> Hi Dr. Neumann,
>
> I'm an independent researcher. I just finished a paper called "Three Kinds of System Prompt," which compares the governance documents Anthropic, OpenAI, Google DeepMind and xAI publish, sorted into training-time, runtime and deployed layers. Your "Prompt Governance?" paper is the closest prior work I found, and my Related Work section is about how the two differ: you look at what researchers and policymakers say about these instructions, and I code what the documents themselves say.
>
> I'd like to post it on arXiv under cs.CL. As a first-time submitter I need an endorsement. Would you be open to reading the abstract, and the paper if it looks useful, and endorsing if you think it belongs there? I can send the PDF. No hard feelings if it's not a fit.
>
> Paper and data: https://github.com/P-r-e-m-i-u-m/spec-strata
>
> Thanks for reading,
> Syed Abdul Aman

If she doesn't answer in about a week, other routes people use:

- Ask on the Hugging Face forums or r/MachineLearning, with your endorsement code. It's common and accepted.
- Ask anyone you know who has published in `cs.CL` or `cs.AI`. A mentor, a course instructor or a professor at LPU works.

## 3. What you upload

arXiv wants the source, not just the PDF:

- `paper/system-prompt-taxonomy-paper.tex`

The bibliography is inline (`thebibliography`), so there's no separate `.bib` file, and there are no figures to include. arXiv recompiles from your source on its own servers. Mine compiles with no errors or warnings over three `pdflatex` passes, so it should go through.

## 4. Submit

1. Go to <https://arxiv.org/submit>.
2. Upload the `.tex` file and let arXiv build it. Check the preview matches your PDF (9 pages).
3. Fill in the title, abstract, author and category. The abstract is in the paper, and `paper/index.html` has a copy.
4. Pick a license. CC BY 4.0 is the common choice if you want people to reuse it freely.
5. Submit. New submitters often wait a day or two before it goes live.

## 5. After it's live

- You'll get an ID like `2610.xxxxx`.
- Add an arXiv badge to the README and put the ID in `CITATION.cff`.
- Link it from your GitHub profile and LinkedIn. A checkable ID is worth more than "I wrote a paper."

## How long it takes

An endorsement can take hours or a few weeks, depending on who answers. After that, submission to live is usually one or two business days. Plan for about a week if you're starting from nothing.
