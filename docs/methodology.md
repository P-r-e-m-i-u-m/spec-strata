# Methodology

How I chose sources, graded them, and coded them. If you want to check my work or redo it, start here.

## The question

How do labs encode behavioral control in the documents they publish, and what patterns, differences and gaps show up across labs and product types?

## Sub-questions, and where the paper lands

1. **What kinds of instruction recur across labs** (safety, tone, tools, formatting, identity)? Coded on seven axes, below.
2. **Do consumer chat assistants, coding agents and API defaults differ in structure?** Partly. The paper compares coding agents with consumer chat. It doesn't cover API defaults, because I found no Tier 1 material of comparable depth.
3. **Where there's version history, how often does the document change?** Only Anthropic's claude.ai changelog has one. I report revision cadence. I did not measure whether prompts grew longer or more complex over time.
4. **What's missing from some labs' documents that others include?** Google's gap is the clearest case. xAI's permissive content defaults are the clearest difference in substance.

## Source tiers

The tiers grade how far a source can be trusted. They are separate from the three layers (training-time, runtime rulebook, deployed prompt) the paper proposes. Every row in the dataset carries one.

- **Tier 1: official.** The lab published it itself. Examples: Anthropic's constitution and its claude.ai changelog, OpenAI's Model Spec, xAI's raw prompts on GitHub.
- **Tier 2: reconstructed, high consensus.** Prompts that turn up consistently across independent extraction attempts and live in long-running, widely cited public repos. Used as supporting evidence and always labeled that way.
- **Tier 3: single-source.** Low confidence. Used only to say a pattern might exist, never as a main data point.

Tier 2 and 3 material is weaker by construction. The paper says so wherever it leans on it, because a reviewer will ask.

## Coding scheme

Each entry is coded on seven axes:

| Axis | What I looked for |
|---|---|
| Identity framing | Does it name the assistant, the company, the model version? |
| Safety and refusal | Is it present, how specific is it, which categories does it cover (violence, CBRN, child safety, self-harm, and so on)? |
| Tool-use governance | Rules for when and how to call tools, and when to confirm first |
| Tone and persona | Style, formatting and verbosity constraints |
| Output format | Markdown rules, citation rules, structured output |
| Injection countermeasures | Explicit instructions against manipulation |
| Recency handling | Instructions for when to search and when to rely on memory |

Document length and revision history aren't axes. When a source gives them, they go in the `notes` column. I built the scheme from a first pass over the corpus, not in advance.

One person applied it. There's no second coder and no inter-rater number.

## Unit of analysis

One row is one document, or one officially documented family of prompts, for one product at one point in time.

## Quoting policy

I don't reproduce system prompt text beyond short fragments (under 15 words) where the exact wording matters. Everything else is paraphrase and structural coding.

## What's in the corpus

- **Anthropic.** Tier 1. The training-time constitution (CC0), and the public, dated changelog of the claude.ai and mobile prompt: 18 revisions from July 2024 to June 2026. This is the only lab with that kind of record.
- **OpenAI.** Tier 1. The Model Spec (CC0, 128 pages), 2025-09-12 revision.
- **Google DeepMind.** Tier 3. No governance document exists publicly as of July 2026. What I found is prompting advice for developers.
- **xAI.** Tier 1. Raw deployed prompts at github.com/xai-org/grok-prompts. Publication followed the May 2025 incident.
- **Coding agents.** Tier 2. Cursor, Claude Code, GitHub Copilot, Devin, Windsurf, Replit, v0 and 20+ others, all from x1xhlol/system-prompts-and-models-of-ai-tools (141k+ stars, 501 commits when I looked).
- **Open-source and self-hosted defaults.** Considered and left out. I found nothing at Tier 1 with comparable depth, and padding with Tier 3 would have weakened the rest.

## About my own repo

I also have a repo of system prompts I collected. I looked at it and left it out. It didn't add anything the Tier 1 and Tier 2 sources didn't already cover, and including it just to include it would have made the evidence look better than it is.
