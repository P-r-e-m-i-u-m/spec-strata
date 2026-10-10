# Revision log

What changed between drafts, and why. Newest round first.

## Round 4: wording pass and consistency fixes (October 2026)

I rewrote the paper, README, site and docs to sound like me instead of like a template, and checked the paper, dataset and docs against each other while I was at it. That turned up real problems, not just wording ones.

**Fixed**

- **Axis count.** The paper said the corpus was coded on eight axes, including length. The dataset has seven axis columns and no length column. The paper, methodology and report now say seven, and length and revision history are described as notes where a source gives them.
- **A misplaced cell.** In the xAI row, `identity_framing` held content-policy text that belongs under safety and refusal. I replaced it with "not coded". I have no verified source for xAI's identity framing, and I'd rather leave it blank than guess. The quoted policy text moved to the notes.
- **Tiers vs layers.** The site and README used "Tier 1/2/3" for the three kinds of document (training-time, runtime, deployed). The paper uses "Tier" for how far a source can be trusted. Same word, two meanings, and the site's lab table got it wrong. The three kinds of document are now called layers everywhere.
- **Overstated review language.** The site said "independently reviewed". What actually happened is three self-review passes with an AI standing in as the reviewers. It now says that.
- **Notes that went further than the sources.** "Rogue employee" became "unauthorized internal change", which is what the paper says. "CC0-adjacent" is gone because I had no source for it. "Often the same model" for coding agents is gone. "Most fragmented of all labs" is gone.
- **A placeholder ORCID** in `CITATION.cff` (all zeros) could have been picked up by Zenodo. Removed.

**Reworded**

- New title: *Three Kinds of System Prompt: Comparing What AI Labs Publish About How Their Models Behave*. The old one was accurate and unreadable. The old title was *Behavioral Control Through System Prompts: A Comparative Structural Analysis of Public Governance Artifacts Across Commercial LLM Deployments*.
- Abstract, introduction, findings, limitations and conclusion rewritten in first person, shorter sentences, same claims.
- Added a short note on AI tools used (Claude helped with sources, drafting and editing).

**Not redone in this round.** I did not re-fetch the sources or re-verify the citations. Rounds 2 and 3 covered 12 to 13 of the 14 entries now in the bibliography (the logs disagree on the count), so check the full list by hand before submitting. If a source has changed since, this log won't know.

## Round 3: three-reviewer simulation

I asked Claude to play three reviewers (methodology, technical correctness, novelty) and re-verify against primary sources instead of trusting the earlier draft. It found two real problems.

**Missing prior work.** A search for competing work turned up Neumann, Sargeant and Singh (2026), "Prompt Governance? On Governing Technologies Governed by Natural Language" (FAccT 2026). It's a 44-page paper with a PRISMA-style review of 287 papers, an eight-category typology of the goals attributed to system-level instructions, and policy case studies on EO 14319 and the EU GPAI Code of Practice. My draft claimed no one had put these documents side by side, and that was wrong. Fixed by:

- adding a full paragraph to Related Work on how the two papers differ (their stakeholder "prompt stack" and literature typology vs. my artifact-type taxonomy and direct coding of the documents)
- softening every absolute novelty claim in the abstract, introduction and conclusion
- citing their paper with checked metadata

**Dataset and paper disagreed.** The Anthropic changelog row that Section 5.6 depends on was never actually in the CSV, because an earlier script silently did nothing. A second row also had unescaped commas that split one field into three. Both fixed, and the CSV is now checked programmatically (6 rows, 13 columns each).

Also done that round:

- Disclosed in a footnote that the Model Spec has been revised since the 2025-09-12 snapshot I analyzed.
- Cross-checked the constitution's word count (about 23,000), CC0 license and priority order against the primary PDF and several other sources.
- Re-checked the xAI content-policy claim against the raw file.
- Fixed an `enumitem` label-width warning.
- Replaced a hardcoded section number with a proper `\ref`.
- Audited citations and labels: every `\cite` key has a `\bibitem`, and every `\ref` has a `\label`.

## Round 2: citations and a stronger data point

**Citations.** Every reference was checked against arXiv pages, publisher pages or official docs. Two mismatched keys (`promptleak2024` and `promptleak2026`) were corrected. Verified entries:

- Karmaker Santu & Feng (2023), TELeR, arXiv:2305.11430, EMNLP 2023 Findings
- Sahoo et al. (2024), arXiv:2402.07927
- Tian et al. (2025), arXiv:2509.14404
- Perez & Ribeiro (2022), arXiv:2211.09527
- Yang et al. (2026), arXiv:2606.18673
- Zhuang et al. (2025), arXiv:2505.11459
- Sahu et al. (2026), arXiv:2604.01039

**Anthropic's changelog.** I found that Anthropic publishes a dated changelog for the deployed claude.ai and mobile prompt (docs.claude.com/en/release-notes/system-prompts). That upgraded one data point from "pending" to Tier 1 and gave the paper its only longitudinal evidence: 18 revisions between July 2024 and June 2026. It became Section 5.6.

**The xAI claim.** I had first sourced it from a secondary summary. I re-checked it against `grok_4_safety_prompt.txt` in xAI's repo and rewrote it to match the actual wording.

**Limitations.** Rewrote them to be specific. The cadence result is strong for Anthropic and unverified for the other three. The coding-agent explanation is flagged as untested.

## Still open

- One coder, no inter-rater reliability.
- The coding-agent result is Tier 2, from a single aggregation repo.
- Most documents are single snapshots. The Model Spec has been revised since the version I read.
- No peer review.
