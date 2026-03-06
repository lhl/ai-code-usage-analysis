# Sources

Local source capture bundles live here.

Use `sources/` for fetched source material, `research/` for analysis notes, and `claims/` for extracted claim records.

## Layout

- `sources/README.md`: workflow and directory conventions
- `sources/TEMPLATE.md`: metadata template for new source captures
- `sources/captured/<source-id>/`: one directory per captured source

## Source ID format

Prefer:

- `publisher-YYYY-MM-DD-slug`

Example:

- `semianalysis-2026-02-05-claude-code-is-the-inflection-point`

## Minimum capture

Each captured source should have:

- `metadata.md`
- at least one raw or semi-raw artifact such as `page.html`, `page.pdf`, or `extract.txt`

When possible, also keep:

- `headers.txt`
- `extract.json`
- `rendered.txt` or `rendered.pdf` if Playwright was required

## Working rules

- Prefer the simplest successful fetch path.
- Save the raw response before doing cleanup or conversion.
- If the accessible view is partial, note that explicitly in `metadata.md`.
- Do not treat rendered or extracted text as more authoritative than the raw capture.
- Use [docs/REFERENCE-webfetch.md](../docs/REFERENCE-webfetch.md) for the fetch order and command examples.

## Follow-on processing

Once a source is captured and worth keeping:

- add or update a note in `research/`
- add a claim batch in `claims/extracted/`
- record major capture/analysis progress in `WORKLOG.md`
