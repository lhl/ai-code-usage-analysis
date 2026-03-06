# Claims

Structured claim tracking for this repo.

Use `research/` for narrative notes and synthesis. Use `claims/` for concise, traceable claim records that can later be ingested into a database if needed.

## Current format

This repo currently uses **source-batch Markdown files** for claim extraction:

- one claim file per source note or source document
- YAML frontmatter for batch metadata
- one table row per claim

This keeps the early-stage workflow easy to read and diff while preserving enough structure for later migration to DuckDB, SQLite, or another store.

## Layout

- `claims/README.md`: workflow and schema
- `claims/TEMPLATE.md`: template for new extraction batches
- `claims/extracted/`: extracted claim batches keyed to source notes

## Current batches

- `claims/extracted/chatgpt-5.4.md`
- `claims/extracted/chatgpt-pro-deepresearch.md`
- `claims/extracted/claude-opus-4.6-deepresearch.md`
- `claims/extracted/claude-opus-4.6.md`
- `claims/extracted/semianalysis-claude-code-is-the-inflection-point.md`

## File naming

- Match the source note stem where practical.
- Example: `research/chatgpt-pro-deepresearch.md` -> `claims/extracted/chatgpt-pro-deepresearch.md`

## Batch frontmatter

Required fields:

- `extracted_from`
- `source_note_url`
- `extracted_on`
- `extraction_type`

If a local note has no stable upstream URL recorded, use `local-note-only` for `source_note_url` and upgrade it later if a better provenance link becomes available.

## Claim table schema

Each batch file should contain a table with these columns:

- `claim_id`: stable local identifier within this repo
- `added`: date added to the claim registry
- `kind`: one of `fact`, `vendor`, `inference`, `proposal`
- `status`: one of `verified`, `partially-verified`, `vendor-reported`, `unverified`, `misleading`, `disputed`, `open`
- `claim`: concise statement of the claim
- `best_reference_url`: best available URL for the claim right now
- `notes`: short caveat, scope note, or extraction comment

If a claim currently only traces to a local note, `best_reference_url` may also be `local-note-only` during early extraction.

## Working rules

- Preserve provenance. Early on, it is acceptable for similar claims to appear in more than one source-batch file.
- Keep claims short enough to scan and stable enough to query later.
- Prefer the strongest directly relevant URL available; if the best current provenance is the source note itself, use that and mark the note accordingly.
- Update an existing claim row when its status changes rather than rephrasing the same claim in multiple places.
- Use `WORKLOG.md` to record major extraction passes, new source classes, or changes to the schema.

## Migration threshold

Move to a database when one or more of these becomes true:

- filtering across claim files becomes tedious
- we need systematic deduplication or joins
- verification state changes need audit trails
- we want programmatic ranking, tagging, or retrieval across hundreds of claims
