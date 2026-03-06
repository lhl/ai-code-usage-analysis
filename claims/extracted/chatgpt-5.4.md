---
extracted_from: research/chatgpt-5.4.md
source_note_url: https://chatgpt.com/c/69aa6754-e0ec-83a7-b4b9-75a31e2c271c
extracted_on: 2026-03-07
extraction_type: initial-pass
---

# Claims Extracted From `chatgpt-5.4`

Initial pass focused on verification-heavy claims and corrections surfaced in the note.

| claim_id | added | kind | status | claim | best_reference_url | notes |
|---|---|---|---|---|---|---|
| chatgpt54-001 | 2026-03-07 | fact | verified | AIDev spans 932,791 agent-authored PRs across 116,211 repositories and 72,189 developers. | https://huggingface.co/datasets/hao-li/AIDev | Good baseline public dataset for visible agent PR activity. |
| chatgpt54-002 | 2026-03-07 | fact | verified | GitHub’s 2025 Octoverse reports roughly 986M commits, 630M total projects, and 395M public repositories. | https://github.blog/news-insights/octoverse/octoverse-a-new-developer-joins-github-every-second-as-ai-leads-typescript-to-1/ | Useful denominator correction against overstated “630M repositories” claims. |
| chatgpt54-003 | 2026-03-07 | vendor | vendor-reported | Anthropic said Claude Code exceeded $2.5B in run-rate revenue and more than doubled since January 1, 2026. | https://www.anthropic.com/news/anthropic-raises-30-billion-series-g-funding-380-billion-post-money-valuation | Strong directional adoption signal, but still self-reported. |
| chatgpt54-004 | 2026-03-07 | fact | verified | The fingerprinting paper reported about 97.2% F1 for identifying which agent authored a PR. | https://arxiv.org/abs/2601.17406 | Measurement is on labeled, traceable PRs rather than the full hidden-use universe. |
| chatgpt54-005 | 2026-03-07 | fact | verified | The widely repeated 64.9% Codex share applies to a curated AIDev-pop style subset, not the full AIDev dataset. | https://arxiv.org/abs/2601.17406 | Important scope correction for market-share style summaries. |
| chatgpt54-006 | 2026-03-07 | fact | misleading | The “46% of code, 61% for Java” Copilot figure refers to Copilot users and earlier reporting, not all GitHub code in 2026. | https://chatgpt.com/c/69aa6754-e0ec-83a7-b4b9-75a31e2c271c | Kept as a correction claim until a stronger direct primary URL is attached in a later pass. |
| chatgpt54-007 | 2026-03-07 | inference | open | Public git-attribution studies almost certainly undercount inline autocomplete and attribution-disabled agent use. | https://arxiv.org/abs/2601.18341 | Strong inference, but still an inference rather than a directly measured multiplier. |
| chatgpt54-008 | 2026-03-07 | inference | disputed | “30-40% of all GitHub code is AI-assisted” is plausible as a hypothesis but not established as a verified fact. | https://chatgpt.com/c/69aa6754-e0ec-83a7-b4b9-75a31e2c271c | Useful example of a claim that should stay clearly separated from verified counts. |
