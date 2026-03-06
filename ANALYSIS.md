# AI Code Usage Analysis: Current Status

Last updated: 2026-03-07

This file is the repo's current top-level status report. It combines the existing notes in [`research/`](research/), the extracted claim batches in [`claims/extracted/`](claims/extracted/), and the current handoff context in [`WORKLOG.md`](WORKLOG.md). It should be read as a calibrated synthesis of what this repo can defend today, not as a finished measurement study.

## At A Glance

- Current phase: early synthesis and claim cleanup, not original quantitative analysis yet.
- Evidence base in repo: 5 research notes, 5 extracted claim batches, and 43 tracked claims.
- Current claim mix: 11 verified, 3 vendor-reported, 1 partially-verified, 20 open, 4 unverified, 2 misleading, and 2 disputed.
- Source quality is still uneven: 23 of 43 current claims still use a local note or chat transcript as the best reference URL and need stronger direct source attachment.

## Current Best Take

The strongest current conclusion is that AI-assisted coding is already materially affecting software creation, but the best public measurements still capture only a narrow slice of that activity. Public GitHub traces now show visible, non-trivial agent use, yet those traces are not the same thing as total AI-assisted code production.

For the visible GitHub layer, the most solid public anchors are GitHub's own platform denominators and the AIDev research line. GitHub reported about 986 million commits in 2025 and roughly 43.2 million merged pull requests per month. AIDev reports about 932,791 attributable agent-authored PRs across 116,211 repositories and 72,189 developers through 2025-08-01. That is enough to say visible agent activity is real and already large in absolute terms, but not enough to support loose claims that AI already dominates public GitHub output. Relevant notes: [`research/chatgpt-pro-deepresearch.md`](research/chatgpt-pro-deepresearch.md), [`research/chatgpt-5.4.md`](research/chatgpt-5.4.md).

The second strong conclusion is that public git-visible measurement structurally undercounts total AI use. Inline autocomplete, pasted chat output, local agent loops, and configurable or removed attribution all weaken provenance-based counting. The fingerprinting work is important here: it suggests hidden agent use may be inferable from PR behavior, but it does not yet turn hidden use into a clean platform-wide estimate. Current repo view: public GitHub data is a lower bound on AI involvement, not a full accounting. Relevant notes: [`research/chatgpt-pro-deepresearch.md`](research/chatgpt-pro-deepresearch.md), [`research/claude-opus-4.6.md`](research/claude-opus-4.6.md).

The third conclusion is that widely repeated headline numbers still need careful handling. The SemiAnalysis claim that Claude Code accounts for 4% of all public GitHub commits is plausible enough to matter, but it is not independently reproduced in this repo and the accessible source capture is partial. Likewise, broad statements such as "30-40% of all GitHub code is AI-assisted" remain hypotheses or extrapolations, not verified facts. Current repo view: separate verified denominators, vendor disclosures, and inference instead of collapsing them into one number. Relevant note: [`research/semianalysis-claude-code-is-the-inflection-point.md`](research/semianalysis-claude-code-is-the-inflection-point.md).

The fourth conclusion is that private and non-GitHub software creation may be the largest blind spot. Internal disclosures from Google and Microsoft suggest substantial AI-assisted coding inside large engineering organizations, but those figures are not directly comparable to public GitHub traces. Outside GitHub, the repo has a credible hypothesis that AI is expanding software creation by non-traditional developers and by users on hosted app-building platforms, but that part of the evidence base is still mostly research design and proxy ideas rather than measured results. Relevant note: [`research/claude-opus-4.6.md`](research/claude-opus-4.6.md).

## What Looks Solid Right Now

- GitHub-wide denominators such as commit and PR volume are better grounded than most viral "share of code" claims.
- AIDev and related MSR 2026 work are currently the best public foundation for visible agent PR analysis.
- Publicly attributable agent activity is still small relative to GitHub-wide throughput, even if the raw counts are already meaningful.
- Public measurements almost certainly undercount actual AI assistance because the highest-volume assistive modes leave weak or no git traces.
- Review burden, maintenance durability, and output quality look more decision-relevant than raw generation volume alone.

## What Is Still Weak Or Unsettled

- The repo does not yet contain an independent replication of the "4% of public GitHub commits" claim.
- Many current claims still need direct primary URLs rather than local notes, chat transcripts, or secondary synthesis.
- The repo has no original estimate yet for the hidden-use multiplier between visible agent traces and total AI-assisted coding.
- Evidence about software creation outside GitHub is still mostly hypothesis and proxy design, not validated measurement.
- Revenue and growth figures from vendors are useful directional signals, but they should not be treated as audited output metrics.

## Practical Status Report

If someone asks what this repo currently believes, the shortest defensible answer is:

1. AI-assisted coding is already mainstream enough to matter, but the most reliable public measurements still cover only the visible agentic slice.
2. GitHub-visible agent activity is growing fast and is no longer niche, but the exact share of all public commits attributable to AI remains unsettled.
3. The repo should treat public git-level metrics as lower bounds, not as total AI-code share.
4. The biggest unanswered questions are about hidden use, review tax, maintenance tax, and software creation by people who never show up in GitHub data at all.

## Best Next Research Moves

1. Reproduce a visible-agent baseline with public data after the AIDev cutoff, including a careful attempt to bound or replicate the 4% claim.
2. Measure review tax and human oversight burden using existing public PR datasets before chasing another market-share summary.
3. Study maintenance tax after merge: reverts, fix PRs, follow-up churn, and reopened issues.
4. Build proxy-based measurement for non-GitHub software creation, especially hosted app builders, deployment platforms, and app-store style release surfaces.
5. Upgrade the claim base by replacing weak local/chat references with direct primary URLs for the highest-value claims.

## Primary In-Repo Inputs

- [`README.md`](README.md)
- [`WORKLOG.md`](WORKLOG.md)
- [`research/chatgpt-pro-deepresearch.md`](research/chatgpt-pro-deepresearch.md)
- [`research/chatgpt-5.4.md`](research/chatgpt-5.4.md)
- [`research/claude-opus-4.6-deepresearch.md`](research/claude-opus-4.6-deepresearch.md)
- [`research/claude-opus-4.6.md`](research/claude-opus-4.6.md)
- [`research/semianalysis-claude-code-is-the-inflection-point.md`](research/semianalysis-claude-code-is-the-inflection-point.md)
- [`claims/extracted/`](claims/extracted/)
