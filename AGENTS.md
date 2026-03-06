# AI Code Usage Analysis - Agent Guide

Refer to `README.md` and `research/` for project context. This file is only for workflow rules.

If this file conflicts with higher-priority system or developer instructions, follow those instructions first.

## Shared Repo Safety

- Run `git status -sb` before starting work and again before each commit.
- Assume the repo may contain unrelated in-progress work. Pre-existing dirty or untracked files are non-blocking; leave them untouched.
- If a file already has edits you did not make and you need to change that same file, stop and ask before proceeding.
- Never discard or overwrite others' work. Do not use destructive commands like `git restore`, `git checkout --`, `git reset --hard`, `git clean`, or bulk rewrites unless explicitly instructed.
- Keep changes scoped to the current request. Do not "clean up" unrelated files or revert unrelated hunks in touched files.

## Research Hygiene

- Keep claims and conclusions qualified. Separate verified facts, self-reported/vendor claims, and inference when practical.
- Prefer small, traceable additions: focused notes, scripts, data pulls, and methodology updates over broad rewrites.
- When adding derived numbers, charts, or datasets, leave a brief note about source and method in the relevant file.
- Use `WORKLOG.md` as the running handoff and state file for ongoing research.
- Append a short `WORKLOG.md` entry when a session materially changes research direction, adds a new dataset or method, resolves an important question, or establishes clear next steps.
- Keep `WORKLOG.md` concise: date header, current state, notable findings or decisions, and next actions. Do not duplicate full commit-level detail that already lives in git history.

## Claim Tracking

- Use `claims/` for structured claim records and `research/` for narrative notes and synthesis.
- Prefer source-batch claim files during early exploration: one Markdown file per source note or source document.
- Each extracted claim row should include `claim_id`, `added`, `kind`, `status`, `claim`, `best_reference_url`, and `notes`.
- Preserve provenance and avoid premature deduplication. It is acceptable for similar claims to appear in multiple source-batch files when they come from different notes.
- If a claim’s status changes after additional checking, update the existing claim row rather than scattering near-duplicates across the repo.

## Commits

- Commit on completed logical workgroups. Do not commit every file touch, and do not wait until a long session ends if a coherent unit is already done.
- Keep commits atomic: group related changes together and separate unrelated work.
- Stage files explicitly. Never use `git add .`, `git add -A`, or `git commit -a`.
- Review staged files before committing with `git diff --staged --name-only` and `git diff --staged`.
- Leave unrelated worktree changes unstaged.
- Use concise commit messages. Conventional prefixes like `docs:`, `feat:`, `fix:`, `data:`, and `research:` are preferred.
- Do not add bylines, co-author footers, or generated-attribution text.

## Default Working Style

- Be concise in docs and notes. This repo should stay easy to scan.
- Prefer reproducible methods over one-off claims when the extra effort is reasonable.
- If a task grows beyond a small scoped change, add a short note to `README.md` or a research file so the direction is discoverable later.
- Prefer updating `WORKLOG.md` for cross-session context instead of scattering status notes across multiple files.
