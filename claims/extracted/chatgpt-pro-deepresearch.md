---
extracted_from: research/chatgpt-pro-deepresearch.md
source_note_url: https://chatgpt.com/c/69aa68be-7358-83a7-947e-8db0f11c8347
extracted_on: 2026-03-07
extraction_type: initial-pass
---

# Claims Extracted From `chatgpt-pro-deepresearch`

Initial pass focused on denominator claims, measurement caveats, and the strongest directly reusable summary claims.

| claim_id | added | kind | status | claim | best_reference_url | notes |
|---|---|---|---|---|---|---|
| chatgptpro-001 | 2026-03-07 | fact | verified | GitHub reported roughly 986M commits in 2025, up about 25.1% year over year. | https://github.blog/news-insights/octoverse/octoverse-a-new-developer-joins-github-every-second-as-ai-leads-typescript-to-1/ | Clean platform-level denominator. |
| chatgptpro-002 | 2026-03-07 | fact | verified | GitHub reported roughly 43.2M pull requests merged per month in 2025, up about 23% year over year. | https://github.blog/news-insights/octoverse/octoverse-a-new-developer-joins-github-every-second-as-ai-leads-typescript-to-1/ | Useful PR-based denominator for agentic activity. |
| chatgptpro-003 | 2026-03-07 | fact | verified | AIDev captures about 932,791 attributable agentic PRs across 116,211 repositories through August 1, 2025. | https://huggingface.co/datasets/hao-li/AIDev | Measures visible agentic PRs, not all AI-assisted work. |
| chatgptpro-004 | 2026-03-07 | inference | open | Publicly attributed agent activity on GitHub is still small relative to GitHub-wide denominators, even though the absolute volume is already large. | https://chatgpt.com/c/69aa68be-7358-83a7-947e-8db0f11c8347 | Good framing claim for synthesis, not a single-source fact. |
| chatgptpro-005 | 2026-03-07 | inference | open | Inline assistant/autocomplete use and disabled attribution create a structural undercount in public git-level AI measurement. | https://chatgpt.com/c/69aa68be-7358-83a7-947e-8db0f11c8347 | Candidate core thesis for repo-level synthesis. |
| chatgptpro-006 | 2026-03-07 | fact | verified | Behavioral fingerprinting work suggests hidden agentic contributions may be partially inferable, with about 97% F1 on labeled PRs. | https://arxiv.org/abs/2601.17406 | Strong but still limited to the observable training surface. |
| chatgptpro-007 | 2026-03-07 | vendor | vendor-reported | Large internal engineering org disclosures place AI-generated new code in roughly the 25-30% range for some teams and repos. | https://chatgpt.com/c/69aa68be-7358-83a7-947e-8db0f11c8347 | Needs a later pass attaching direct Google and Microsoft URLs claim-by-claim. |
| chatgptpro-008 | 2026-03-07 | inference | open | End-2026 projections are fragile because AI can change commit and PR granularity as well as total shipped output. | https://chatgpt.com/c/69aa68be-7358-83a7-947e-8db0f11c8347 | Good warning against naive extrapolation from short windows. |
