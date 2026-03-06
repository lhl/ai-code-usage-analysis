# AI Code Usage Analysis

This repository is for ongoing research and analysis on AI coding adoption trends.

The core question is simple: how much software is now being created with AI, by whom, through which workflows, and with what downstream effects on review, quality, and maintenance?

The hard part is measurement. Public GitHub activity captures only a narrow slice of AI-assisted software creation. A large share of AI use is invisible in git metadata, and another large share may be happening outside traditional software development workflows entirely.

## Scope

This repo currently focuses on three overlapping layers:

- **GitHub-visible agent activity**: PRs, commits, bot accounts, branch patterns, and other traces left by tools like Codex, Claude Code, Copilot, Cursor, and Devin.
- **Hidden or weakly visible AI usage**: autocomplete, copied chat output, attribution-disabled agents, and behavior that must be inferred rather than directly observed.
- **Software creation outside GitHub**: app builders, vibe-coding tools, hosted platforms, and non-traditional developers who may never use source control at all.

## Current Working View

Based on the research notes in this repo, a few themes already look durable:

- Public GitHub traces almost certainly undercount real AI coding adoption.
- The headline number depends heavily on the denominator: commit share, PR share, accepted suggestions, developer self-report, or deployed software volume.
- Vendor growth signals are useful, but they are not the same thing as independently measured output.
- The most interesting unanswered questions are about expansion of total software creation, review burden, quality, durability, and the rise of non-traditional software creators.

## Research Questions

- Is AI expanding the total amount of software being created, or mostly substituting for existing developer work?
- What share of AI-assisted coding is directly observable in public GitHub data?
- How much "dark matter" sits outside git-based measurement?
- What kinds of changes are agents actually making: core logic, tests, docs, configuration, refactors, or maintenance work?
- Do AI-assisted changes increase review load, code churn, or long-term maintenance cost?
- Are non-software developers now creating materially more apps, sites, and automations because AI tools lowered the barrier?

## Current Contents

The repo is early and currently contains exploratory research notes under [`research/`](research/):

- [`research/chatgpt-pro-deepresearch.md`](research/chatgpt-pro-deepresearch.md): detailed synthesis of public GitHub agent activity, professional adoption signals, and measurement caveats.
- [`research/chatgpt-5.4.md`](research/chatgpt-5.4.md): critical review of common claims and a prioritization of the most promising original studies.
- [`research/claude-opus-4.6-deepresearch.md`](research/claude-opus-4.6-deepresearch.md): claim-by-claim landscape review with emphasis on what is verified, overstated, or still unknown.
- [`research/claude-opus-4.6.md`](research/claude-opus-4.6.md): practical research design notes, including possible data sources, sampling strategies, and non-GitHub measurement ideas.
- [`research/semianalysis-claude-code-is-the-inflection-point.md`](research/semianalysis-claude-code-is-the-inflection-point.md): partial-source review of the SemiAnalysis post that popularized the 4% Claude Code GitHub-commit claim.
- [`claims/`](claims/): structured claim extraction batches intended to stay easy to diff now and easy to ingest into a database later.
- [`sources/`](sources/): local source capture bundles with raw fetches, extracted text, and metadata.
- [`docs/REFERENCE-webfetch.md`](docs/REFERENCE-webfetch.md): local fetch playbook covering `curl`, `rc-html-extract`, `pandoc`, and `playwright-cli`.
- [`WORKLOG.md`](WORKLOG.md): short cross-session handoff file tracking current focus, findings, and near-term next steps.

## Planned Work

Near-term directions for this repo:

1. Mine public datasets such as AIDev for agent PR growth, concentration, task mix, and review dynamics.
2. Sample GH Archive and GitHub APIs to estimate visible agent activity over time.
3. Build inference-oriented methods for hidden AI usage rather than assuming unlabeled work is human-only.
4. Track software creation outside GitHub using proxy signals such as app-store submissions, hosting/deployment platforms, and ecosystem package usage.
5. Separate verified claims from vendor claims and keep methods reproducible wherever possible.

## Repository Principles

- Prefer primary sources and reproducible analysis over viral summary stats.
- Keep verified, self-reported, and inferred claims clearly separated.
- Treat vendor metrics as directional unless independently replicated.
- Favor careful sampling and bounded estimates over false precision.
- Document caveats aggressively. This topic has denominator problems everywhere.

## Repo Status

This is a new working repo. At the moment it is primarily a place to collect research, sharpen questions, and turn those questions into reproducible analysis over time.
