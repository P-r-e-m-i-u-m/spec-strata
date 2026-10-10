<div align="center">

# spec-strata

**Three kinds of system prompt, and why comparing them head to head goes wrong.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-preprint%20%C2%B7%20not%20peer%20reviewed-lightgrey)](docs/publication-readiness-report.md)
[![Paper](https://img.shields.io/badge/paper-PDF-red)](paper/system-prompt-taxonomy-paper.pdf)
[![DOI](https://img.shields.io/badge/DOI-pending-lightgrey)](docs/zenodo-orcid-guide.md)

[Live site](https://p-r-e-m-i-u-m.github.io/spec-strata/) · [Paper](paper/system-prompt-taxonomy-paper.pdf) · [Data](data/dataset.csv)

</div>

---

## The short version

"Compare Claude's system prompt with ChatGPT's" sounds like one question. It's usually three.

Some of what AI labs publish is built into the model during training. Some is a rulebook for whose instructions win when they clash. Some is the literal text a product sends at the start of every chat. Line one of these up against another and you're comparing things that were never the same kind of document.

This repo holds the paper that sorts them into layers, plus the data and notes behind it. I read what Anthropic, OpenAI, Google DeepMind and xAI have published, added system prompts from 25+ coding agents, graded each source by how far it can be trusted, and coded them side by side.

## The three layers

| Layer | What it is | Example |
|---|---|---|
| **Training time** | Shapes the model's weights. Never sent at runtime. | Anthropic's constitution |
| **Runtime rulebook** | Says whose instructions win. Not a prompt itself. | OpenAI's Model Spec |
| **Deployed prompt** | The text a product sends with each conversation. | Grok's public prompts, Anthropic's claude.ai changelog |

Don't mix these up with the **source tiers** in the paper. Tier 1, 2 and 3 grade how far to trust a source (Tier 1 means the lab published it itself). The layers describe what kind of document it is.

## What I found

- **Labs publish different kinds of document.** Anthropic's main public document is a training-time one. OpenAI's is a runtime rulebook. xAI publishes the deployed prompts. Google DeepMind hasn't published anything about Gemini's own rules, only prompting advice for developers. A "Lab A vs Lab B" comparison often lines up two real things and two gaps.
- **Same structure, different reasons.** Anthropic and OpenAI both rank whose instructions come first. OpenAI frames that as developer control. Anthropic frames it as judgment the model should absorb, and says it would rather explain than hand over a rule list.
- **Transparency can be a reaction.** xAI committed to publishing Grok's prompts after a May 2025 incident, as a way to rebuild trust. That's a different story from publishing on principle, and it may deserve a different level of trust.
- **Product type shapes the prompt.** Coding agents (Cursor, Claude Code, Copilot, Devin and 20+ more) lean on tool rules and say comparatively little about content safety. My reading is that safety already lives in the model. That's an interpretation I haven't tested.
- **"Living document" can be checked, at least once.** Anthropic keeps a dated changelog for its claude.ai prompt: 18 revisions in about 23 months, roughly one every six weeks. For the other labs there's nothing to check against.

The full argument, with sources, is in the [paper](paper/system-prompt-taxonomy-paper.pdf).

## What's in here

```
spec-strata/
├── paper/
│   ├── system-prompt-taxonomy-paper.pdf   the paper
│   └── system-prompt-taxonomy-paper.tex   LaTeX source
├── data/
│   └── dataset.csv                        the coded corpus
├── docs/
│   ├── methodology.md                     how I picked, graded and coded sources
│   ├── revision-log.md                    what changed between drafts, and why
│   ├── publication-readiness-report.md    my self-review, including what's still weak
│   ├── arxiv-submission-guide.md
│   └── zenodo-orcid-guide.md
├── CITATION.cff
└── README.md
```

## The data

`data/dataset.csv` has 6 rows and 13 columns: entity, product, tier, source type, url, seven coded axes, and a notes column.

The seven axes are identity framing, safety and refusal, tool governance, tone and persona, output format, injection countermeasures, and recency handling. Length and revision history aren't axes. When a source gives them (the Model Spec's page count, the constitution's word count, the changelog dates), they're in the notes. Details are in [`docs/methodology.md`](docs/methodology.md).

## Where it's weak

- **One person coded everything.** No second coder, so no reliability number. This is the biggest gap.
- **The coding-agent result rests on one aggregation repo** (Tier 2). Treat it as a lead, not a verdict.
- **Most documents are single snapshots.** Only Anthropic has a dated revision record. The OpenAI Model Spec I analyzed is the September 2025 version, and it has been revised since.
- **It's not peer reviewed.** I ran three self-review passes with Claude playing the reviewers ([report](docs/publication-readiness-report.md)). That catches mistakes. It isn't outside review.

## Cite it

See [`CITATION.cff`](CITATION.cff), or:

```bibtex
@misc{aman2026threekinds,
  author = {Aman, Syed Abdul},
  title  = {Three Kinds of System Prompt: Comparing What AI Labs Publish
            About How Their Models Behave},
  year   = {2026},
  howpublished = {\url{https://github.com/P-r-e-m-i-u-m/spec-strata}}
}
```

## Author

Syed Abdul Aman, independent researcher. `amanbaba9404522@gmail.com`

## License

MIT. See [LICENSE](LICENSE).
