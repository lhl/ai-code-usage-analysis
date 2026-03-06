# Worklog

Lightweight running log for ongoing research state in this repo.

Use this file to record what changed in the research direction between commits:

- active questions being pursued
- datasets or sources inspected
- methods attempted
- notable findings or dead ends
- immediate next steps

Keep entries short and factual. Git history remains the source of truth for file changes; this file is for research state and handoff context.

## 2026-03-07

### Current state

- Repo initialized with a top-level [README.md](README.md) and four exploratory notes under [research/](research/).
- Current emphasis is framing the measurement problem around visible agent activity, hidden AI usage, and software creation outside GitHub.

### Easy research goals

- Build a ranked backlog of high-value, low-effort analyses from existing public datasets.
- Identify which claims in the current notes are verified, vendor-reported, or inferred.
- Define a minimal reproducible workflow for future dataset pulls and analysis scripts.

### Near-term candidates

- Review AIDev and AIDev-pop as the first structured datasets to analyze.
- Draft a small research backlog covering review burden, maintenance cost, concentration, and hidden-use estimation.
- Decide whether to track work by dated notes in [research/](research/) alone or also maintain a standing methodology/backlog file.

### Workflow changes

- Added a `claims/` workflow with source-batch Markdown files, a schema README, and a template for future extraction passes.
- Claims are now meant to live in `claims/`, while `research/` remains the place for narrative synthesis and longer analysis.

### Extraction pass

- Added initial claim batches for all four current research notes under `claims/extracted/`.
- The first pass favors provenance and scanability over aggressive deduplication; similar claims may appear in more than one batch.
- Some rows currently use the source note itself as the best reference URL when a stronger per-claim primary link has not yet been attached.

### Next actions

- Attach more direct primary URLs to high-value claims that currently point to local notes or chat logs.
- Decide which extracted claims should be normalized or merged into a cross-note synthesis layer.
- Start the first actual data-backed research task, likely with AIDev or AIDev-pop.

### Source capture workflow

- Added `sources/` conventions and a fetch-order reference document under `docs/REFERENCE-webfetch.md`.
- The repo now has an explicit fetch preference order: `curl` -> `rc-html-extract` -> embedded HTML/JSON inspection -> `playwright-cli` when rendering is actually needed.
- The fetch guide reflects tools confirmed on this machine: `curl`, `rc-html-extract`, `pandoc`, and `playwright-cli`.

### SemiAnalysis source pass

- Captured the SemiAnalysis post `Claude Code is the Inflection Point` under `sources/captured/semianalysis-2026-02-05-claude-code-is-the-inflection-point/`.
- The raw HTML exposed embedded metadata and article body HTML, so Playwright was not needed.
- The accessible capture appears partial: metadata reports a 4,988-word paid post, but the embedded accessible body ends at the heading `Anthropic's Funding and Surge: Why is Anthropic Winning?`.
- Added a partial-source analysis note under `research/` and an extracted claim batch under `claims/extracted/`.
