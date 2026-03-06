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
