# Web Fetch Reference

Practical fetch playbook for this repo.

The default goal is to capture the strongest accessible local copy of a source with the least effort, while recording any access limits honestly.

## Preferred order of operations

1. **Probe with `curl` first**
   - Check redirects, content type, and whether the page is directly fetchable.
   - Commands:
     - `curl -I -L --max-time 20 "URL"`
     - `curl -L -sS --max-time 20 "URL" -o /tmp/page.html`

2. **Run `rc-html-extract` on the fetched HTML**
   - Fastest way to see whether the raw HTML already contains title, date, and readable article text.
   - Commands:
     - `rc-html-extract /tmp/page.html --format json`
     - `rc-html-extract /tmp/page.html --format text`

3. **Inspect the raw HTML before escalating**
   - Many sites expose the article in embedded JSON, even when the rendered page is noisy.
   - Commands:
     - `rg -n 'article|body_html|__NEXT_DATA__|window\\._preloads|published|paywall' /tmp/page.html`
     - `pandoc -f html -t markdown /tmp/page.html`
   - Use `pandoc` as a cleanup aid, not the first extraction step.

4. **Escalate to `playwright-cli` only when needed**
   - Use Playwright when `curl` returns a JS shell, a partial DOM, or content that appears only after rendering.
   - Tested examples:
     - `playwright-cli open "https://example.com"`
     - `playwright-cli eval '() => document.title'`
     - `playwright-cli eval '() => document.body.innerText'`
     - `playwright-cli snapshot`
     - `playwright-cli pdf`
     - `playwright-cli network`
     - `playwright-cli close`
   - If browsers are missing: `playwright-cli install-browser`

5. **Record access limits instead of bypassing them**
   - If a page is logged-out, paywalled, geoblocked, or truncated, save what was accessible and note the limitation in source metadata.
   - Do not add bypass workflows to repo instructions.

## Save bundle

Save source captures under `sources/captured/<source-id>/`.

Preferred bundle contents:

- `metadata.md`: normalized capture metadata and notes
- `headers.txt`: optional, useful for redirects/cache/access debugging
- `page.html`: preferred raw capture
- `extract.json` or `extract.txt`: output from `rc-html-extract`
- `rendered.txt` or `rendered.pdf`: only if Playwright was needed

## Choosing the simplest successful path

- If `curl` + `rc-html-extract` works, stop there.
- If raw HTML contains embedded structured data, parse that before opening a browser.
- Use Playwright for rendered content, consent flows, or pages where the accessible text only appears post-hydration.
- Keep the capture method reproducible in `metadata.md`.

## Notes

- This repo currently has `curl`, `rc-html-extract`, `pandoc`, and `playwright-cli` available.
- Source analysis should happen after capture: create a note under `research/` and a claim batch under `claims/extracted/` once the source is worth keeping.
