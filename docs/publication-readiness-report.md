# Publication Readiness Report
## "Behavioral Control Through System Prompts: A Comparative Structural Analysis of Public Governance Artifacts Across Commercial LLM Deployments"

Prepared as an independent three-reviewer simulation (methodology; technical
correctness/evidence quality; novelty/significance) plus a full technical
verification pass, as requested. This report is honest about what was found
and fixed, not a rubber stamp.

---

## 1. Executive Summary

The paper introduces a three-part taxonomy of LLM behavioral-control
artifacts — training-time constitutions, runtime authority specifications,
and deployed inference-time system prompts — and applies it to a
credibility-tiered comparative dataset spanning Anthropic, OpenAI, Google
DeepMind, and xAI, plus a 25+ product coding-agent corpus. Its central
value is resolving a category error common in informal cross-lab prompt
comparisons, and its strongest empirical result is a directly verifiable
longitudinal finding (18 dated system-prompt revisions over 23 months for
Anthropic) rather than a claim resting on a publisher's self-description.
The paper is honest about its limitations, engages substantively with the
closest competing work found (Neumann et al. 2026, FAccT), and every
citation, dataset row, and cross-reference has been independently checked
against primary sources or the compiled LaTeX output. It is ready for
arXiv submission. It is not, on its own, a top-tier-conference-caliber
empirical contribution (see Section 11) — its natural venue is arXiv/a
workshop or a policy-adjacent track, not a flagship ML venue, given the
qualitative, single-coder, four-lab-scope of the study.

## 2. Primary Research Contributions

1. **Three-part artifact taxonomy** (training-time / runtime-authority /
   deployed) that resolves incommensurable cross-lab comparisons — the
   paper's most durable contribution, independent of any single finding.
2. **Credibility-tiered comparative dataset** (6 coded entries across 4
   labs + 1 aggregated coding-agent corpus) coded along 8 functional axes.
3. **Verified longitudinal evidence** for one lab (Anthropic: 18 dated
   revisions, ~41-day mean interval) that a "living document" claim is
   independently checkable rather than rhetorical.
4. **A precisely-scoped positioning** relative to Neumann et al. (2026),
   the closest prior work, distinguishing artifact-type analysis from
   their stakeholder-hierarchy/literature-claims analysis.
5. **A verified, substantive divergence finding** (xAI's content-policy
   permissiveness) checked against primary file text, not a secondary
   summary.

## 3. Remaining Limitations (as stated in the paper, Section 7)

- Corpus is not exhaustive: 4 labs in depth + 1 aggregated Tier-2 source.
- Tier-2/3 material (notably the coding-agent finding) is suggestive, not
  confirmatory.
- Longitudinal verification exists for only one lab (Anthropic); the
  other three remain cross-sectional snapshots.
- Single-coder application of the coding scheme; no inter-rater
  reliability statistic.
- The layered-governance interpretation in the coding-agent finding is
  the most parsimonious explanation available, not a demonstrated causal
  mechanism — explicitly flagged as unfalsified in this study.
- The OpenAI Model Spec analysis reflects a Sept-2025 snapshot; the
  document has been revised further since (through at least March 2026).

## 4. Remaining Reviewer Risks (honest assessment, not fixed because they
   cannot be fixed with available evidence/resources)

- **Small-N qualitative study**: A methodology reviewer at a top ML venue
  will likely note that 4 labs + 1 aggregated source, single-coder, is a
  thin empirical base for strong claims. The paper hedges appropriately,
  but this remains the single biggest risk to acceptance at a
  top-tier *empirical* ML venue (less of a risk at a policy/FAccT-adjacent
  or arXiv/workshop venue, where this kind of qualitative comparative
  study is standard).
- **Coding-agent finding rests on Tier-2 evidence**: the most
  "interesting" finding (Section 5.5) is also the least rigorously
  sourced. A skeptical reviewer could ask the paper to either drop this
  finding or gather Tier-1 replication — the paper currently hedges
  rather than resolves this.
- **Interpretive claims presented with appropriate but real uncertainty**:
  the "layered division of governance labor" explanation is plausible but
  unfalsified by this study's design; a reviewer could reasonably ask for
  a falsification test (e.g., a coding agent on a base model with no
  training-time safety layer) that the paper does not perform.
- **Overlap with Neumann et al. (2026)**: even after honest
  differentiation, a reviewer familiar with that paper may see this work
  as a narrower, less methodologically rigorous (no PRISMA protocol, no
  inter-rater reliability) treatment of an adjacent question. The
  differentiation argument is real and defensible, but a hostile reviewer
  could still push back that the marginal contribution over Neumann et
  al. is modest.
- **No statistical inference anywhere in the paper**: this is a
  qualitative/coding study; there are no significance tests, confidence
  intervals, or effect sizes. This is appropriate for the study design
  but should be stated as a deliberate scope choice, not an oversight,
  if a reviewer asks.

## 5. Novelty Assessment

Genuine novelty: the three-part artifact-type taxonomy, and the direct,
coded, primary-source comparative content analysis across labs. This
survives a targeted stress-test against the closest adjacent literature
(prompt-engineering taxonomies, prompt-security literature, and
critically, Neumann et al. 2026's governance-studies treatment). The
taxonomy is not present in any of the reviewed prior work under this
framing. The marginal contribution over Neumann et al. specifically is
narrower than the paper's earlier draft implied (see Round 3 revision
log) but remains real: this paper analyzes what the documents say; theirs
analyzes what the literature and policy discourse claim about such
documents. Novelty rating: **moderate-to-good**, not groundbreaking —
appropriate for arXiv/workshop, defensible but not a slam dunk at a
top-tier ML venue on novelty alone.

## 6. Technical Correctness Assessment

- All 12 pre-existing bibliography entries verified against primary
  metadata (arXiv abstract pages, publisher pages); 1 new entry (Neumann
  et al.) added and verified with equal rigor.
- Two factual claims were re-verified against primary source text rather
  than left as originally (secondarily) sourced: xAI's content policy
  (Round 2) and the Anthropic constitution's word count/license (Round 3,
  cross-checked against 6+ independent sources including the primary PDF).
- One factual claim (OpenAI Model Spec page count/content) is disclosed
  as a dated snapshot with an explicit footnote noting further revisions
  exist, rather than presented as current.
- Two dataset/paper consistency bugs were found and fixed in this round:
  a missing dataset row that the paper's own Table 1 referenced, and a
  malformed CSV row (unescaped commas) from an earlier append operation.
- LaTeX source compiles cleanly: triple-pass compilation, zero warnings,
  zero errors, stable 10-page output.

## 7. Methodological Rigor Assessment

Appropriate for a qualitative comparative/taxonomic study, with real
limitations disclosed rather than concealed:
- Credibility tiering (Tier 1/2/3) is a genuine methodological
  contribution for handling mixed-provenance evidence in this domain.
- Coding scheme (8 axes) was derived inductively and is reported
  transparently, but was applied by a single coder — the paper's own
  Limitations section flags this rather than omitting it.
- No pre-registration, no formal sampling frame beyond "major labs with
  available Tier-1/2 material" (a convenience sample, disclosed as such
  implicitly through the tiering system but not explicitly named as a
  convenience sample in-text — a minor presentation gap, not a validity
  flaw, since the paper's claims are appropriately scoped to the labs
  studied).
- Compare to Neumann et al.'s PRISMA-protocol systematic review: this
  paper's methodology is less formally rigorous by design, because it
  answers a different kind of question (primary-source content coding
  vs. systematic literature synthesis). This is a legitimate
  methodological choice, not a shortcoming, but should be understood as
  such rather than as equivalent rigor to a systematic review.

## 8. Evidence Quality Assessment

- Strongest evidence: Anthropic's dated changelog (Tier 1, directly
  verifiable, 18 data points) and OpenAI's Model Spec (Tier 1, CC0,
  directly fetched and read).
- Weakest evidence: the coding-agent product-category finding (Tier 2,
  single aggregation source, not independently cross-validated against
  Tier-1 sources for each of the 25+ products individually).
- Google DeepMind's negative finding (no equivalent governance document)
  is a genuine finding but is also, definitionally, an absence — the
  paper appropriately frames it as such rather than overinterpreting it.
- No fabricated data, citations, or results were found or introduced at
  any point in this project; every reference traces to a real, checked
  source, and every dataset entry traces to an actual fetched or
  searched primary or secondary source with its tier disclosed.

## 9. Reproducibility Assessment

- The credibility-tiering and coding scheme are documented in
  `methodology.md` in enough detail that an independent researcher could
  re-derive similar codes from the same primary sources, though exact
  code assignment involves qualitative judgment (single-coder limitation
  applies here too).
- All primary sources cited are publicly accessible URLs (GitHub repos,
  official lab documentation, arXiv papers) as of the access dates
  stated.
- The dataset.csv provides the coded corpus in a directly inspectable,
  machine-readable format.
- What is NOT reproducible in a strict sense: the exact qualitative
  coding decisions, absent a second coder — this is disclosed, not
  hidden.

## 10. Writing and Presentation Assessment

- Argument structure is coherent: taxonomy → methodology → findings →
  discussion → limitations → conclusion, with each finding subsection
  doing real interpretive work rather than just listing observations.
- Abstract, contributions list, and conclusion were revised in this round
  to match the paper's actual (more precisely scoped) claims after the
  Neumann et al. discovery — internal consistency was re-checked after
  these edits.
- One stylistic note: several findings subsections (5.1–5.6) are
  uniformly structured (claim → primary evidence → interpretation),
  which aids readability but could read as slightly formulaic to a
  literary-minded reviewer; this is a minor, non-blocking style
  observation, not a substantive issue.
- Table 1 and the description-list taxonomy in Section 3 render cleanly
  and are appropriately compact.

## 11. arXiv Readiness Assessment

**Ready for arXiv submission as-is.** arXiv (cs.CY or cs.CL, likely
cross-listed) does not require the empirical rigor bar of a top-tier
peer-reviewed ML venue; qualitative, taxonomic, and governance-adjacent
papers of this kind are routine there, including the closest comparator
(Neumann et al., which itself is on arXiv in addition to FAccT). If the
goal shifts to a peer-reviewed venue (e.g., FAccT, AIES, or a CSCW/CHI
governance track), the paper would benefit from — but does not currently
require for arXiv — inter-rater reliability data and/or expansion of the
coding-agent finding to Tier-1 sources before submission there.

## 12. Future Research Opportunities

1. Inter-rater reliability study on the 8-axis coding scheme.
2. Direct Tier-1 verification of the coding-agent product-category
   finding (e.g., contacting individual coding-agent vendors, or waiting
   for official publication as more labs follow Anthropic/xAI's lead).
3. Longitudinal extension: revisit this corpus in 12–24 months to see
   whether other labs begin publishing dated changelogs (testing whether
   Anthropic's practice diffuses, per the paper's own discussion of
   Brussels-Effect-style dynamics noted in the adjacent Neumann et al.
   paper).
4. A falsification test for the layered-governance hypothesis: analyze a
   coding agent built on a base model with no public training-time
   safety layer, to see whether its deployed prompt compensates with
   heavier safety framing (as the hypothesis would predict).
5. Formal collaboration or explicit dialogue with the Neumann et al.
   research line, given the two papers' complementary but currently
   independent findings.

---

## Verification Checklist

| Item | Status | Evidence |
|---|---|---|
| Every citation verified against original source | ✅ | 13 entries checked against arXiv/publisher/GitHub primary pages; see Sections 6 above and prior revision-log entries |
| Every reference has complete, accurate metadata | ✅ | Full author lists, venues, years, DOIs/arXiv IDs confirmed for all 13 bibliography entries |
| Every factual claim supported by reliable evidence | ✅ (with disclosed exceptions) | Core claims (word counts, licenses, dates) cross-verified against multiple independent sources; Tier-2/3 claims explicitly flagged as lower-confidence in-text, not presented as equivalent to Tier-1 |
| Every figure/table/equation/cross-reference correct | ✅ | 1 table (corpus overview), no equations; all 6 `\label`/`\ref` pairs verified 1:1 matched; no orphaned or missing references |
| Dataset, methodology, and supplementary materials internally consistent | ✅ (fixed this round) | Found and fixed: missing dataset row referenced by paper's Table 1; malformed CSV row from earlier append; both verified resolved |
| LaTeX compiles cleanly, no unresolved warnings/broken references | ✅ | Triple-pass compilation: 0 warnings, 0 errors, stable 10-page output; `enumitem` labelwidth warning found and fixed this round |
| No fabricated citations, results, experiments, or unsupported claims | ✅ | Every citation traces to a real, independently checked source; no invented data points; all Tier-2/3 (lower-confidence) content explicitly labeled as such rather than presented as fact; novelty claims revised after finding real competing prior work rather than left overstated |

**Overall conclusion:** This manuscript represents the strongest and most
defensible version achievable with the primary and authoritative sources
accessible in this session. The most significant risk to the paper's
academic credibility — an unaware, false novelty claim relative to
Neumann et al. (2026) — was identified and honestly resolved rather than
missed. Remaining limitations (small N, single coder, Tier-2 reliance for
one finding) are real, disclosed, and not fixable without additional
primary-source access or a second human coder; they do not constitute
grounds to withhold the paper from arXiv, but should be weighed by the
author if targeting a more selective peer-reviewed venue.
