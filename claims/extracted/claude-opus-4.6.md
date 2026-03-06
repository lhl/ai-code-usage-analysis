---
extracted_from: research/claude-opus-4.6.md
source_note_url: https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f
extracted_on: 2026-03-07
extraction_type: initial-pass
---

# Claims Extracted From `claude-opus-4.6`

Initial pass focused on research design proposals and measurement ideas rather than narrow factual verification.

| claim_id | added | kind | status | claim | best_reference_url | notes |
|---|---|---|---|---|---|---|
| claude46-001 | 2026-03-07 | proposal | open | AIDev and AIDev-pop are the best first public datasets for an independent study of visible coding-agent PR activity. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Strong candidate for the repo’s first actual data pull. |
| claude46-002 | 2026-03-07 | proposal | open | GH Archive plus the GitHub Events API is the most practical route for independently estimating traceable agent commit share at platform scale. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Makes later replication of SemiAnalysis-style estimates tractable. |
| claude46-003 | 2026-03-07 | proposal | open | A retrained fingerprinting classifier could be applied conservatively to unlabeled PRs to estimate a lower bound on hidden agent use. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | One of the more novel public-data angles in the note. |
| claude46-004 | 2026-03-07 | proposal | open | Review tax and human oversight burden are likely among the highest-value low-effort studies available from existing public datasets. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Good fit for AIDev-pop timelines and review metadata. |
| claude46-005 | 2026-03-07 | proposal | open | Post-merge maintenance tax should be studied through follow-up edits, reverts, fix PRs, and reopened issues rather than merge rate alone. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | More decision-relevant than raw acceptance percentages. |
| claude46-006 | 2026-03-07 | proposal | open | Concentration analysis should measure how agent PR activity clusters by repo, developer, language, and task type rather than assuming even adoption. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Could produce unusually informative distribution results quickly. |
| claude46-007 | 2026-03-07 | inference | open | Public GitHub data cannot directly observe most private-repo telemetry and inline autocomplete activity. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Core limit that should shape every claim in this repo. |
| claude46-008 | 2026-03-07 | proposal | open | Non-GitHub “dark matter” can be explored using proxy signals such as app-store submissions, website creation, and hosted-platform release activity. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Important expansion beyond git-centric measurement. |
| claude46-009 | 2026-03-07 | proposal | open | Volunteer panels or enterprise telemetry are the cleanest route to line-level attribution, but they are much harder to obtain than public-data studies. | https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f | Good long-range path if public-data work proves promising. |
