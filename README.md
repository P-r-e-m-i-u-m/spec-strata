<div align="center">

# spec-strata

**A comparative structural taxonomy of the documents that govern LLM behavior**
*Training-time constitutions → runtime authority specs → deployed system prompts*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-arXiv--ready-brightgreen)](docs/publication-readiness-report.md)
[![Paper](https://img.shields.io/badge/paper-PDF-red)](paper/system-prompt-taxonomy-paper.pdf)
[![DOI](https://img.shields.io/badge/DOI-pending-lightgrey)](docs/zenodo-orcid-guide.md)

**[→ Live site](https://p-r-e-m-i-u-m.github.io/spec-strata/)**

</div>

---

## What this is

Commercial LLM providers now publish (or leak) a layered stack of governance artifacts: training-time value specifications, runtime authority hierarchies, and per-product deployed system prompts. Despite huge public interest — prompt-collection repos with tens of thousands of stars, an active prompt-extraction literature — there's been little direct comparative content analysis of what these documents actually *say*, side by side.

This repo introduces a three-part taxonomy of these artifacts and applies a credibility-tiered comparative methodology across major providers (Anthropic, OpenAI, Google, xAI, and others) to surface structural patterns, divergences, and open research gaps.

## The taxonomy

```
┌─────────────────────────────────────────────────────────────────┐
│  TIER 1 — Training-time Constitution                            │
│  Baked into the model's weights. Not injected at runtime.       │
│  e.g. Anthropic's Constitution                                  │
└───────────────────────────┬───────────────────────────────────┘
                             │
┌───────────────────────────▼───────────────────────────────────┐
│  TIER 2 — Runtime Authority Specification                       │
│  A framework for arbitrating provider / operator / user intent  │
│  e.g. OpenAI's Model Spec                                       │
└───────────────────────────┬───────────────────────────────────┘
                             │
┌───────────────────────────▼───────────────────────────────────┐
│  TIER 3 — Deployed System Prompt                                │
│  Product-specific instructions injected at inference time       │
│  e.g. Grok's public raw prompts, Claude.ai's changelog'd prompt  │
└─────────────────────────────────────────────────────────────────┘
```

Most public "system prompt comparisons" quietly compare across these tiers as if they were the same kind of artifact. They aren't — and that mismatch is itself a finding.

## Key findings

- **Labs diverge in artifact *type*, not just content.** Anthropic's primary public artifact sits at Tier 1, OpenAI's at Tier 2, xAI's at Tier 3 — and Google has published no artifact in any tier about Gemini's own governance. A naive "Lab A's prompt vs. Lab B's prompt" comparison is often comparing two absences and two different artifact types.
- **Convergent structure, divergent philosophy.** Anthropic and OpenAI both use a ranked authority hierarchy — but OpenAI frames it as steerability/developer control (a programming-language analogy), while Anthropic frames its equivalent as reasoning the model should internalize, explicitly preferring reason-based over rule-based specification.
- **Transparency can be reactive, not just proactive.** xAI's public-prompt-publishing commitment was a direct response to a 2025 incident, not a proactive stance — a materially different category from Anthropic's and OpenAI's framing, with different implications for how representative the publication is.
- **Product category predicts instruction emphasis.** Coding-agent products (Cursor, Claude Code, Copilot, Devin, 20+ others) emphasize tool-orchestration governance over general content-safety — consistent with safety already living in a training-time layer, leaving the deployed prompt to govern only what's task-specific.
- **"Living document" claims are usually rhetorical — but not always unverifiable.** Anthropic's deployed Claude.ai/mobile system prompt has a public, dated changelog: 18 revisions over ~23 months, a mean interval of ~41 days — turning a limitation ("we only have snapshots") into a verifiable existence proof for at least one lab.

Full findings, methodology, and evidence tiering: see the [paper](paper/system-prompt-taxonomy-paper.pdf) and [methodology.md](docs/methodology.md).

## Structure

```
spec-strata/
├── paper/
│   ├── system-prompt-taxonomy-paper.pdf   # compiled paper
│   └── system-prompt-taxonomy-paper.tex   # LaTeX source
├── data/
│   └── dataset.csv                        # coded corpus (entity, tier, source_type, coding axes)
├── docs/
│   ├── methodology.md                     # tiering system + coding scheme
│   ├── revision-log.md                    # full audit trail of revisions
│   └── publication-readiness-report.md    # independent 3-reviewer validation report
├── CITATION.cff
└── README.md
```

## Dataset

`data/dataset.csv` codes each governance artifact across:

`entity, product, tier, source_type, url, identity_framing, safety_refusal, tool_governance, tone_persona, output_format, injection_countermeasures, recency_handling, notes`

Sources are tiered by credibility (official publication → verified leak → secondary reporting) — see [`docs/methodology.md`](docs/methodology.md) for the full scheme.

## Status

Independently reviewed against methodology, technical correctness, and novelty/significance criteria — see [`docs/publication-readiness-report.md`](docs/publication-readiness-report.md). arXiv-ready.

**Known limitation:** single-coder coding scheme, no inter-rater reliability yet — flagged transparently rather than glossed over.

## Citing this work

See [`CITATION.cff`](CITATION.cff), or:

```bibtex
@misc{aman2026specstrata,
  author = {Aman, Syed Abdul},
  title  = {Behavioral Control Through System Prompts: A Comparative Structural Analysis of Public Governance Artifacts Across Commercial LLM Deployments},
  year   = {2026},
  howpublished = {\url{https://github.com/P-r-e-m-i-u-m/spec-strata}}
}
```

## Author

**Syed Abdul Aman** — Independent Researcher
`amanbaba9404522@gmail.com`

## License

Code and dataset: MIT (see [LICENSE](LICENSE)). Paper text: see LaTeX source for citation terms.
