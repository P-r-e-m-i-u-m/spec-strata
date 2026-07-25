# spec-strata

**A comparative structural taxonomy of the documents that govern LLM behavior — from training-time constitutions to runtime authority specs to deployed system prompts.**

## What this is

Commercial LLM providers now publish (or leak) a layered stack of governance artifacts: training-time value specifications, runtime authority hierarchies, and per-product deployed system prompts. Despite huge public interest — prompt-collection repos with tens of thousands of stars, an active prompt-extraction literature — there's been little direct comparative content analysis of what these documents actually say, side by side.

This repo contains a research paper that introduces a three-part taxonomy of these artifacts and applies a credibility-tiered comparative methodology across major providers (Anthropic, OpenAI, Google, xAI, and others) to identify structural patterns, divergences, and open research gaps.

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
└── README.md
```

## Dataset

`data/dataset.csv` codes each governance artifact across:

`entity, product, tier, source_type, url, identity_framing, safety_refusal, tool_governance, tone_persona, output_format, injection_countermeasures, recency_handling, notes`

Sources are tiered by credibility (official publication → verified leak → secondary reporting) — see `docs/methodology.md` for the full scheme.

## Status

Independently reviewed against methodology, technical correctness, and novelty/significance criteria (see `docs/publication-readiness-report.md`). arXiv-ready. Known limitation: single-coder coding scheme, no inter-rater reliability yet — flagged transparently rather than glossed over.

## Author

Syed Abdul Aman — Independent Researcher
`amanbaba9404522@gmail.com`

## License

Code and dataset: MIT (see below). Paper text: see LaTeX source for citation terms.

```
MIT License

Copyright (c) 2026 Syed Abdul Aman

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
