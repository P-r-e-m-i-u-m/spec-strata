# Revision Log — Behavioral Control Through System Prompts

## Draft 1 → Final: What Changed and Why

### Citation verification (every reference checked against primary metadata)
All 12 references were checked against arXiv abstract pages, publisher
pages, or official documentation rather than left as placeholder
author lists. Two citation-key mismatches (`promptleak2024` vs.
`promptleak2026`) found during compilation were corrected. Final
verified authorship:

- Karmaker Santu & Feng (2023) — TELeR, arXiv:2305.11430, EMNLP 2023 Findings
- Sahoo, Singh, Saha, Jain, Mondal, Chadha (2024) — arXiv:2402.07927
- Tian, Wang, Yang, Zhang, Liu (2025) — arXiv:2509.14404
- Perez & Ribeiro (2022) — arXiv:2211.09527, NeurIPS 2022 ML Safety Workshop
- Yang, Fu, Zhang, Zeng, Li, Du, Wang, Ji, Chen (2026) — arXiv:2606.18673
- Zhuang, Nicolae, Wang, Fritz (2025) — arXiv:2505.11459
- Sahu, Samanta, Soosahabi (2026) — arXiv:2604.01039

### Tier-1 dataset expansion
Discovered and added Anthropic's official, versioned changelog of the
*deployed* claude.ai/mobile system prompt
(docs.claude.com/en/release-notes/system-prompts), upgrading that data
point from "pending" to Tier 1. This is the strongest addition in the
revision pass: it gave the paper genuine longitudinal evidence (18 dated
revisions, July 2024–June 2026) where the first draft had only
cross-sectional snapshots, directly strengthening a limitation flagged
in the first draft. New Section 5.6 and updated Table 1 reflect this.

### Fact verification against primary sources
The claim about xAI's content-policy permissiveness was originally
sourced through a tertiary summary (Grokipedia). Re-verified directly
against the primary repository file (`grok_4_safety_prompt.txt`) and
rewritten to match the verified primary wording exactly, with a more
precise and defensible claim as a result (Section 5.4).

### Analytical strengthening
- New Section 5.6 (publication cadence) added as a genuinely new
  finding, not just a rewritten limitation.
- Limitations section rewritten to be asymmetric and specific rather
  than uniformly hedged — the cadence finding is now flagged as
  strong evidence for Anthropic specifically, while the same claim
  remains unverified for the other three labs.
- Added an explicit, falsifiability-aware caveat on the coding-agent
  layered-governance interpretation (Limitations, point 5) rather than
  presenting it as demonstrated.
- Abstract, contributions list, and conclusion updated to reflect the
  cadence finding so the paper's headline claims match its strongest
  evidence.

### Author's own repository
Per instruction, the author's "LLM System Prompt Intelligence
Repository" was evaluated for inclusion and excluded from the final
analysis on the grounds that it did not add comparative value beyond
the Tier-1/Tier-2 sources already in the corpus. This is noted
explicitly in METHODOLOGY.md rather than silently omitted, so the
decision is auditable.

### Technical QA
- LaTeX compiled cleanly (two-pass pdflatex) with zero undefined
  citations and zero LaTeX errors in the final build.
- Full text extracted via `pdftotext` and read end-to-end to confirm
  all cross-references (Section/Table numbers) resolve correctly and
  no garbled text or broken macros survived compilation.
- All internal `\ref`/`\label` pairs checked; one hardcoded section
  number (referring to the cadence subsection from Limitations) was
  found and replaced with a proper `\ref` to avoid drift if section
  numbering changes.

## Independent Three-Reviewer Validation Pass (Round 3)

This round simulated three independent reviewers (methodology; technical
correctness/evidence quality; novelty/significance) and re-verified the
entire project against primary sources rather than trusting the prior
draft's claims. Two substantive issues were found and fixed; both are
exactly the kind of issue a real reviewer would flag.

### Critical: missing prior work found and integrated
A targeted search for competing/adjacent work surfaced Neumann, Sargeant
& Singh (2026), "Prompt Governance? On Governing Technologies Governed by
Natural Language," published at FAccT 2026 — a large (44-page), rigorous,
directly adjacent paper (PRISMA review of 287 papers, an 8-category
typology of instruction *goals*, and policy-document case studies on
EO 14319 and the EU GPAI Code of Practice). This is the single most
important omission in the prior draft: the paper's original novelty
claim ("no prior work places these documents side by side") was false.
Fixed by:
- Adding a full, honest paragraph in Related Work distinguishing the two
  papers' axes of analysis (their stakeholder "prompt stack" + literature-claims
  typology vs. this paper's artifact-type taxonomy + direct primary-source
  content coding)
- Softening every overclaiming novelty statement in the abstract,
  introduction, and conclusion to be precise rather than absolute
- Verifying and citing Neumann et al. with full, correct metadata (arXiv,
  FAccT proceedings, DOI)

This is a strengthening revision, not a retreat: the paper now positions
itself accurately relative to the closest real competitor, which is far
more defensible under review than an unaware absolute claim.

### Technical: dataset/paper inconsistency found and fixed
Cross-checking the dataset.csv against the paper's own Table 1 revealed
the Anthropic deployed-system-prompt-changelog row (Section 5.6's evidentiary
basis) had never actually been written to the CSV due to a silent
no-op in an earlier update script — the paper referenced data that
wasn't actually in the supplementary dataset. Fixed by adding the row
directly and validating the CSV's structural integrity (row length vs.
header) programmatically. A second, unrelated CSV malformation (unescaped
commas in the coding-agent row splitting one field into three) was found
by the same validation pass and fixed.

### Additional verification performed this round
- Re-verified OpenAI Model Spec's CC0 license and disclosed that a newer
  revision exists beyond the 2025-09-12 snapshot analyzed (added an
  explicit footnote rather than silently leaving this stale)
- Cross-verified Anthropic constitution's word count (23,000), CC0 license,
  and priority order against 6+ independent sources including the primary
  PDF
- Re-verified xAI's content-policy claim against the actual primary file
  text rather than a tertiary summary (done in Round 2, reconfirmed here)
- Fixed a LaTeX `enumitem` negative-labelwidth warning (cosmetic but a
  real compiler warning a careful reviewer's build process could flag)
- Replaced remaining hardcoded section-number cross-references with
  proper `\ref`/`\label` pairs to prevent drift
- Full citation-key audit: verified 1:1 correspondence between every
  `\cite` key used in-text and every `\bibitem` defined (14 keys, no
  orphans in either direction)
- Full label/ref audit: verified 1:1 correspondence between every `\ref`
  and every `\label` (6 labels, 6 refs, exact match)
- Triple-pass LaTeX compilation confirmed stable at 10 pages with zero
  warnings and zero errors

## Known residual limitations (see paper Section 7 for full discussion)
- Corpus covers 4 labs in depth + 1 aggregated coding-agent source;
  not exhaustive of the deployed-LLM landscape.
- Coding scheme applied by a single coder; no inter-rater reliability
  statistic available.
- Tier-2/3 material (notably the coding-agent product-category
  finding) is suggestive, not confirmatory, pending replication
  against official sources as/if labs publish them.
- The OpenAI Model Spec analysis reflects the 2025-09-12 snapshot; the
  document has been revised further since (through at least March 2026)
  and findings may not hold for the current version without re-analysis.
