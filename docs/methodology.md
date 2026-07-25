# Methodology — Behavioral Control Through System Prompts

## Research Question
How do system prompts across commercial and open-source LLM products encode
behavioral control, and what structural patterns, divergences, and gaps exist
across labs and product types?

## Sub-questions
1. What functional categories of instruction recur across labs (safety, tone,
   tool-use, formatting, identity)?
2. Do consumer chat assistants, coding agents, and enterprise/API-default
   prompts differ systematically in structure or length?
3. Has system prompt complexity (length, number of distinct instruction
   categories) increased over time, where version history is available?
4. What's absent — categories present in some labs' prompts but not others,
   and what does that suggest about differing design philosophies?

## Source Tiers (credibility-graded, this matters for reviewers)
- **Tier 1 — Official/primary**: Content labs have published themselves
  (e.g. Anthropic's public system prompt releases, OpenAI's Model Spec,
  xAI's published Grok prompt, official docs describing system prompt
  structure).
- **Tier 2 — Reconstructed/leaked, high-consensus**: Prompts appearing
  consistently across multiple independent extraction attempts, hosted in
  long-running, widely-cited public repos (used as secondary evidence,
  flagged as such, never treated as ground truth).
- **Tier 3 — Single-source leaks**: Lower confidence, used only to note
  existence of a pattern, not as a primary data point, always caveated.

Every entry in the dataset is tagged with its tier. The paper's limitations
section will explicitly discuss the epistemic status of Tier 2/3 data —
this is a strength if handled honestly, a fatal flaw if glossed over.

## Coding Scheme (applied to each system prompt in the corpus)
Each prompt is tagged along these axes:

| Axis | What we're coding |
|---|---|
| Identity framing | Does it name the assistant, company, model version? |
| Safety/refusal instructions | Presence, specificity, category coverage (violence, CBRN, CSAM, self-harm, etc.) |
| Tool-use governance | Rules for when/how to call tools, confirmation requirements |
| Tone/persona control | Style, formatting, verbosity constraints |
| Output format constraints | Markdown rules, citation rules, structured output |
| Jailbreak/injection countermeasures | Explicit anti-manipulation instructions |
| Knowledge cutoff / recency handling | Instructions for search vs. memory |
| Length | Word/token count |
| Update cadence | If version history available |

## Unit of Analysis
One system prompt (or officially documented prompt family) per product per
snapshot in time = one row in the dataset.

## Copyright / Reproduction Policy
No system prompt text is reproduced verbatim beyond short (<15 word) quoted
fragments where exact wording is analytically necessary (e.g. comparing two
labs' exact refusal phrasing). All classification is done via paraphrase and
structural coding, not reproduction. This is both a legal requirement and
good practice — a table of category-tags is more useful to readers than a
copy-pasted prompt dump anyway.

## Planned Comparative Set (final, as used in the paper)
- Anthropic (Claude family) — Tier 1: training-time constitution (CC0,
  anthropic.com/constitution) AND Tier 1: officially published, versioned
  changelog of the deployed claude.ai/mobile system prompt
  (docs.claude.com/en/release-notes/system-prompts), covering 18 dated
  revisions from July 2024 to June 2026 — the only lab in the corpus with
  verifiable longitudinal deployed-prompt data
- OpenAI (ChatGPT, Model Spec) — Tier 1 (Model Spec, CC0, 128pp)
- Google (Gemini) — Tier 3 only; no equivalent governance document publicly
  available as of July 2026 (developer-facing prompting guides only)
- xAI (Grok) — Tier 1 (raw deployed prompts, github.com/xai-org/grok-prompts);
  publication was reactive (May 2025 incident response), not proactive
- Coding agents: Cursor, Claude Code, GitHub Copilot, Devin, Windsurf,
  Replit, v0, and 20+ others — Tier 2 (x1xhlol/system-prompts-and-models-of-ai-tools,
  141k+ GitHub stars, 501 commits at time of access)
- Open-source/self-hosted defaults — considered but no Tier-1 material
  of comparable depth found; omitted from final analysis rather than
  padded with Tier-3 material

## Note on the author's own repository
The author's "LLM System Prompt Intelligence Repository" was evaluated for
inclusion and ultimately excluded from the final analysis: it did not add
comparative value beyond what the Tier-1/Tier-2 sources above already
provide, and including it without that added value would have weakened
rather than strengthened the paper's evidentiary basis. Per instruction,
personal-repository inclusion is conditional on genuine contribution, not
automatic.
