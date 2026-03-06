---
source_id: semianalysis-2026-02-05-claude-code-is-the-inflection-point
url: https://newsletter.semianalysis.com/p/claude-code-is-the-inflection-point
captured_at: 2026-03-06T16:46:49Z
capture_method: mixed
access_note: partial
status: captured
---

# Source Capture

SemiAnalysis / Substack post capture for later review and claim processing.

## Files

- `page.html`: raw HTML fetched with `curl`
- `headers.txt`: response headers from `curl -I -L`
- `extract.json`: `rc-html-extract` output from the raw HTML
- `extract.txt`: plain-text extraction from the raw HTML
- `embedded-post.json`: metadata parsed from `window._preloads`
- `embedded-body.html`: article body HTML parsed from the embedded page payload
- `embedded-body.txt`: text extracted from `embedded-body.html`

## Notes

- Fetch order used the repo default: `curl` -> `rc-html-extract` -> embedded JSON inspection.
- No Playwright step was needed because the raw HTML already exposed embedded metadata and article body HTML.
- The page is a paid Substack post and the embedded metadata marks it `hidden: true`.
- The accessible embedded body appears partial rather than complete.
- `embedded-post.json` reports `wordcount: 4988`, but `embedded-body.txt` contains about 3,107 words and stops at the heading `Anthropic's Funding and Surge: Why is Anthropic Winning?`.
- `extract.txt` continues into the subscriber prompt after that heading, which is consistent with a partial paywalled capture rather than a full article body.
