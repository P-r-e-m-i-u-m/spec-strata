# Publication readiness report

**Paper:** *Three Kinds of System Prompt: Comparing What AI Labs Publish About How Their Models Behave*

This is my self-review. Claude played three reviewers (methodology, technical correctness, novelty) in round 3, and I checked the paper, dataset and docs against each other again in round 4. It is not outside review, and nobody independent has read the paper yet. I wrote this to say what's solid and what isn't, not to certify it.

## 1. Summary

The paper argues that the documents AI labs publish about model behavior are three different kinds of thing: training-time constitutions, runtime rulebooks for whose instructions win, and deployed system prompts. Comparisons that mix them up don't hold up. It tests this on Anthropic, OpenAI, Google DeepMind and xAI, plus 25+ coding agents, with sources graded by trust and coded on seven axes. Its strongest result is one lab's public changelog: 18 dated revisions in 23 months, which lets a "living document" claim be checked instead of taken on trust.

My honest view: good for arXiv or a workshop, thin for a top ML venue. It's a small, qualitative, single-coder study.

## 2. What it contributes

1. **The three-way split.** The part most likely to outlast any single finding.
2. **A source-tiered dataset**: 6 rows, coded on seven axes.
3. **A checkable cadence result** for one lab (18 revisions, about 41 days apart on average).
4. **A clear position against Neumann et al. (2026)**, the closest prior work: they study what researchers and policymakers say about these documents, and I code what the documents say.
5. **A primary-source check of xAI's content-policy stance**, from the raw file and not a summary.

## 3. Limitations the paper states

- Four labs in depth plus one aggregation repo. Not exhaustive.
- Tier 2 and 3 material is weaker. The coding-agent result is a lead, not a verdict.
- Mostly snapshots. Only Anthropic has dated revision history.
- One coder, no inter-rater reliability.
- The "safety lives in the model" reading of the coding-agent pattern fits the data but hasn't been tested against a case that could disprove it.
- The OpenAI Model Spec analysis is the 2025-09-12 version, and it has been revised since.

## 4. What a reviewer would still push on

- **Small N.** Four labs and one aggregation source is thin for strong claims. The paper hedges, but this is the biggest risk at an empirical ML venue. Less of one at a policy-adjacent venue or workshop.
- **The most interesting finding has the weakest sourcing.** The coding-agent result is Tier 2. A skeptic could ask me to drop it or replicate it from official sources.
- **No falsification test.** A coding agent on a base model with no training-time safety layer would be one.
- **Overlap with Neumann et al.** I think the distinction holds, but a reviewer who knows that paper could call mine a narrower, less formal treatment of a nearby question. They used a PRISMA protocol and I didn't.
- **No statistics.** Intentional, since it's a qualitative coding study, but I should say so up front if asked.
- **Convenience sample.** Labs were included because they had usable material. The paper doesn't say that in so many words.

## 5. Novelty

The three-way split and the direct, coded comparison of primary documents hold up against the prompt-engineering, prompt-security and governance literatures I checked. The gain over Neumann et al. is narrower than my first draft implied. **Moderate to good, not groundbreaking.**

## 6. Technical correctness

Checked in round 4, on the final files:

- The LaTeX compiles with no errors, warnings or overfull boxes across three passes. 9 pages.
- All 14 `\cite` keys have a `\bibitem`, and all 14 `\bibitem`s are cited.
- All 6 `\label`s are used by a `\ref`, and every `\ref` resolves.
- The dataset has 6 rows and 13 columns in every row, and the paper's Table 1 matches it.
- The paper, `methodology.md` and the README all say seven axes.

Checked in earlier rounds, **not repeated in round 4**: reference metadata against sources, the constitution's word count and license, the Model Spec's license, and the xAI wording against the raw file. The bibliography has 14 entries, but my earlier logs say 12, then 13, were verified, so I can't show that every one of the 14 was checked. Before submitting, spot-check each entry (author list, year, venue, arXiv ID or URL) against its source. If a source has changed since, I haven't re-checked it.

Found and fixed in round 4: the eight-vs-seven axis mismatch, a misplaced cell in the xAI row, and notes that went further than the sources. See the [revision log](revision-log.md).

## 7. Methodological rigor

Reasonable for a qualitative comparative study. The tiering is the most useful method choice, because it keeps official and reconstructed material from being weighed equally. The weak spots are the single coder, the convenience sample, and the lack of any pre-registration. It isn't comparable in rigor to a systematic review, and it isn't trying to be.

## 8. Evidence quality

- **Strongest:** Anthropic's dated changelog (Tier 1, 18 checkable data points) and the OpenAI Model Spec (Tier 1, public, CC0).
- **Weakest:** the coding-agent finding (Tier 2, one source, not checked product by product against official material).
- **Google's gap** is a real finding, but it's an absence, and the paper treats it that way.

## 9. Reproducibility

The tiers and the seven axes are written down in [`methodology.md`](methodology.md) and the data is machine-readable, so someone could re-derive similar codes from the same public sources. They wouldn't get identical ones: coding involves judgment, and with one coder I can't say how much.

## 10. Writing

Rewritten in round 4 in first person with shorter sentences. Claims were kept, not strengthened. Sections 5.1 to 5.6 follow the same pattern (claim, evidence, reading), which helps a reader but may feel repetitive. The paper includes a short note on AI tools used.

## 11. arXiv readiness

Ready to submit. Papers like this are routine in cs.CL, cs.AI and cs.CY, and the closest comparison (Neumann et al.) is itself on arXiv. A peer-reviewed venue (FAccT, AIES, a CSCW or CHI governance track) would want a second coder and Tier 1 backing for the coding-agent result first. The practical blocker is an endorsement: see [`arxiv-submission-guide.md`](arxiv-submission-guide.md).

## 12. What I'd do next

1. Get a second coder and report agreement on the seven axes.
2. Back the coding-agent finding with official sources, or drop it.
3. Re-run the corpus in 12 to 24 months and see whether other labs start publishing dated changelogs.
4. Test the "safety lives in the model" reading with a coding agent on a base model that has no public training-time safety layer.
5. Talk to the Neumann et al. group.

## Checklist

| Check | Status | Notes |
|---|---|---|
| Citations checked against their sources | Partly | Rounds 2 and 3 covered 12 to 13 of the 14 entries; not repeated in round 4. Re-check before submitting |
| Reference metadata complete | Partly | Same: confirm all 14 entries by hand |
| Claims backed by sources | Done, with limits | Tier 2 and 3 material is labeled as weaker in the text |
| Tables, cross-references correct | Checked round 4 | 1 table, 6 labels, 6 refs, no equations |
| Dataset, methodology and paper agree | Checked round 4 | After fixing the axis count and the xAI cell |
| LaTeX compiles clean | Checked round 4 | No errors, warnings or overfull boxes |
| Fabricated citations, results or experiments | None known | No new data was added in round 4 |
| Independent human review | **Not done** | Self-review only |
