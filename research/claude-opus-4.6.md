https://claude.ai/chat/98d966d6-0ac9-4813-9987-d0c20eb1dc6f

Great question — let's dig into the key claims and see what we can verify. There are a lot of specific numbers here, so let me search for the primary sources.OK, I've done a thorough sweep of the primary sources. Here's my claim-by-claim assessment:

---

**Claims that check out well against primary sources:**

**SemiAnalysis 4% / Claude Code:** Confirmed. The SemiAnalysis report (Feb 5, 2026) does claim 4% of public GitHub commits from Claude Code, with a 20%+ projection by end of 2026. The report was published by Dylan Patel's team and the $2.5B ARR figure comes directly from Anthropic's own Series G announcement. Anthropic confirmed Claude Code's run-rate revenue exceeded $2.5B, more than doubling since the start of 2026, and that weekly active users also doubled since January 1.

**AIDev dataset:** Confirmed. The dataset aggregates 932,791 Agentic-PRs from five agents across 116,211 repositories, used for the MSR 2026 Mining Challenge. It's a real academic dataset on HuggingFace.

**Cursor financials:** Confirmed. CNBC reported Cursor closed a $2.3B round at $29.3B valuation, crossing $1B ARR. Bloomberg/TechCrunch reported Cursor surpassed $2B in annualized revenue as of March 2026, with the run rate doubling in three months.

**Devin/Cognition:** Confirmed. Cognition disclosed Devin's ARR grew from $1M in September 2024 to $73M in June 2025. Windsurf had $82M ARR and 350+ enterprise customers at acquisition, with combined ARR around $150M. The $400M raise at $10.2B valuation was led by Founders Fund.

**NVIDIA / Cursor case study:** Confirmed as a first-party claim from Cursor's blog. Over 30,000 NVIDIA developers use Cursor daily, with a three-fold increase in committed code. However, multiple observers noted this is essentially an unverified marketing claim from Cursor, lacking independent methodology, and the "3x code commits" metric is widely criticized as a poor proxy for productivity.

**OpenAI Codex numbers:** Confirmed. More than a million developers use Codex weekly, with usage up 5x since January, per Gergely Orosz's interview with the Codex team. The 64.9% of agent-authored PRs figure comes from the AIDev dataset distribution. In the curated subset, OpenAI Codex accounts for 21,793 of 33,580 PRs (64.9%).

**Agent fingerprinting:** Confirmed. The paper achieves 97.2% F1-score using 41 features across commit messages, PR structure, and code characteristics to identify which agent authored a PR. (Note: the document says "41 features" but the paper actually extracted 53 features and selected 41 for the classifier — minor discrepancy in the article.)

**Copilot stats:** Confirmed for 20M users, 90% Fortune 100, 1.3M paid subscribers, 46% code completion, and coding agent producing 1.2M PRs/month. These figures come from Microsoft earnings calls and GitHub's own reporting.

---

**Claims that are questionable, misleading, or need caveats:**

**"Near three-way tie: Copilot ~25%, Claude Code ~24%, Cursor ~24%"** — This is the most problematic claim. The sourcing is murky. One AI Expert Magazine article claims this near three-way split, but most other sources still cite Copilot at 42% market share among paid tools, with Cursor at 18-25% depending on the source. Claude Code's "market share" as a comparable number to Copilot is unclear since they measure different things (API consumption vs. paid seats vs. monthly active users). The "three-way tie" claim likely comes from a single analysis that hasn't been independently corroborated and may be measuring a different slice (e.g., developer mind-share surveys vs. paid revenue share).

**"16-23% agent adoption in 129,134 projects"** — I couldn't find the primary source for this specific number. It may come from an MSR 2026 challenge paper, but without the citation it's unverifiable.

**"29.1% security vulnerability rate in generated Python"** — Not verified in this search. This likely comes from a GitClear or academic study, but the document doesn't cite it. Other sources cite varying numbers — "48% of AI-generated code contains security vulnerabilities" from some studies, "40% of generated programs flagged for insecure code" from earlier Copilot research. The specific 29.1% figure needs a source.

**"4x code duplication"** — This comes from GitClear's 2024 report analyzing 153 million lines of code, which did find AI tools linked to 4x more code cloning. Verified but worth noting this is one report's methodology.

**"Fastest enterprise software ramp ever"** — The $2.5B ARR claim for Claude Code is real, but calling it "fastest ever" depends on how you define "enterprise software." SaaStr and others do call it unprecedented for B2B software.

**"GitHub processed roughly 1 billion commits in 2025 - about 2.7 million per day"** — I couldn't find the primary GitHub source for this specific number. GitHub's Octoverse reports haven't consistently published raw commit counts. The 135K commits/day for Claude Code (4% of ~3.4M) roughly checks out mathematically, but the total daily commit baseline needs verification.

**OpenAI's "70% more PRs merged weekly"** — Not independently verified in my searches. This is likely from internal OpenAI data shared in a blog post.

---

**Structural observations / what to probe further:**

The document's central framing is sound — there is a massive undercounting problem due to Copilot's invisible autocomplete — but there are a few areas where the analysis mixes apples and oranges. The SemiAnalysis 4% figure measures *git-level attribution* (Co-Authored-By tags), while the AIDev dataset measures *identifiable PRs*, while Copilot's 46% measures *code suggestions accepted by users*. These are fundamentally different metrics being presented side-by-side. The "~5% vs 41% self-reported" gap is directionally correct but the exact multiplier depends heavily on definitions.

If you want to do your own analysis, the AIDev dataset is freely available on HuggingFace (`hao-li/AIDev`) and would be the most tractable starting point. You could independently verify the PR acceptance rates, the agent distribution, and the fingerprinting results. The SemiAnalysis methodology for the 4% figure is less transparent — they likely used GitHub's public event stream to count `Co-Authored-By: Claude` tags, but the exact method is behind their paywall.

Want me to pull down the AIDev dataset and run some independent analysis on it?

> Great, independently, what I'd like to do in our session now that we are very familiar w/ the problem is if we were to do our own analysis, what would be involved. We can see there are some datasets, classifiers available. What would we need to be able to do our own research into the topic?

Great question. Let me think through this systematically — what's actually feasible for a small team (or even solo) to independently verify and extend.

## The Data Sources

**Tier 1: Freely available, ready to analyze**

The **AIDev dataset** on HuggingFace (`hao-li/AIDev`) is the obvious starting point. It's ~933K agent-authored PRs with metadata, diffs, review comments, and task classifications. The curated subset (AIDev-pop, 33.6K PRs from repos with 100+ stars) has richer data including commit-level diffs and timelines. This is parquet files — you can load it with pandas or DuckDB in minutes. The immediate analyses you could run: PR volume over time by agent, acceptance rates by agent and task type, structural characteristics (additions/deletions/files touched), and time-to-merge distributions. This is the lowest-hanging fruit and would let you independently verify the acceptance rate claims (Codex 79.9%, Cursor 80.4% on bug fixes, etc.).

**Tier 2: Available via API, requires collection effort**

The **GitHub Events API** and **GH Archive** (gharchive.org) are where you'd go to replicate the SemiAnalysis 4% methodology. GH Archive stores every public GitHub event as newline-delimited JSON, partitioned by hour. You'd query PushEvents, extract commit messages and author metadata, and look for `Co-Authored-By` trailers mentioning Claude, Copilot, Codex, Devin, or Cursor. You could also look at PR events for bot accounts with known agent patterns (e.g., `devin-ai-integration[bot]`, `copilot` branch prefixes). This is BigQuery-queryable — GitHub maintains a public dataset at `githubarchive.day` on BigQuery. The free tier gives you 1TB/month of queries, which is probably enough for targeted analysis but not enough for a full scan of all 2025-2026 data. At scale you're looking at tens of terabytes.

The **GitHub REST/GraphQL API** lets you do targeted sampling. You could pick a stratified sample of repos (by language, star count, activity level) and pull their full commit and PR histories. Rate limits are 5,000 requests/hour authenticated, which is workable for a sample of a few thousand repos but not for crawling millions.

**Tier 3: Would need to build/run yourself**

The **fingerprinting classifier** from the MSR 2026 paper (arXiv:2601.17406) uses XGBoost on 41 features. The paper should have a replication package — you could retrain it on the AIDev data and then apply it to PRs that *aren't* labeled as agent-authored to estimate the "hidden" AI usage. This is the most interesting original contribution you could make: estimating the true AI PR rate by running the classifier on ostensibly human PRs.

## What Analysis Would Actually Be Novel

Here's where I'd focus effort, ranked by feasibility and value:

**1. Time-series decomposition of agent PR growth (easy, high value)**

The AIDev dataset has timestamps. Plot monthly PR counts by agent from May-August 2025 (the dataset window), then use the GitHub API or GH Archive to extend the curve through February 2026. Fit growth models (exponential, logistic, Gompertz) and see which one best describes the data. This directly addresses whether the "doubling monthly" claim is sustainable or whether there's already evidence of a sigmoid approaching saturation. You could have this done in a day.

**2. Independent replication of the 4% figure (medium effort, high value)**

Query GH Archive/BigQuery for PushEvents in January and February 2026. Count commits with Claude Code's `Co-Authored-By` signature vs. total commits. Do the same for other agents. This would be the first independent verification (or refutation) of SemiAnalysis's headline number. The main challenge is BigQuery costs if you need to scan large date ranges — but even a single week's sample would be informative. You could also check whether the denominator (total daily commits) has itself inflated due to AI tools, which would change the interpretation of the percentage.

**3. Hidden AI usage estimation (medium-hard, very high value)**

Train the fingerprinting classifier on AIDev's labeled data, then apply it to the "human" PRs in the dataset. The MSR paper itself flags that these human PRs may be contaminated. If you find that, say, 15-20% of "human" PRs in active repos show agent-like signatures, that's a significant finding about the true adoption rate. You'd need to be careful about false positives — calibrate against a known-clean pre-2024 baseline.

**4. Copilot invisibility estimation (hard, very high value)**

This is the white whale. Copilot autocomplete leaves no git trace, but you could approach it indirectly. Compare coding patterns (commit frequency, code style metrics, duplication rates) in repos where Copilot is known to be active vs. repos where it isn't. The AIDev dataset has repo metadata that might help identify Copilot-heavy repos. Alternatively, survey-based approaches — but that's a different kind of research. Another angle: look at whether repos that show Copilot *agent* activity (which does leave traces) also show statistical shifts in their non-agent commits that suggest heavy autocomplete usage.

**5. Code quality longitudinal analysis (hard, high value)**

Clone a sample of repos with high agent PR activity, run static analysis tools (Bandit for Python security, SonarQube, pylint/eslint), and compare defect density in agent-authored vs. human-authored code within the same repos. This controls for project-level quality culture. The AIDev dataset gives you the PR IDs — you'd need to clone the actual repos to get the full code context.

## The Technical Stack

For all of this, you'd need:

- **Compute:** A machine with 32GB+ RAM for the AIDev dataset (it's large parquet files). GPU helpful but not essential — XGBoost training on 33K samples is fast on CPU.
- **BigQuery access** for GH Archive queries. Free tier might suffice for targeted analysis; budget ~$50-100 if you need broader scans.
- **GitHub API token** (free with any GitHub account, 5K requests/hour).
- **Python stack:** pandas/polars, DuckDB, scikit-learn/XGBoost, matplotlib/plotly for visualization. Standard stuff.
- **For code quality analysis:** You'd want Docker to spin up static analysis tools consistently across many repos.

Realistically, the AIDev dataset analysis (#1) and the BigQuery replication (#2) are weekend projects. The fingerprinting work (#3) is maybe a week. The Copilot estimation (#4) and code quality work (#5) are each multi-week efforts.

## What You Can't Easily Do

A few things that would require resources beyond a small team:

- **Full GitHub crawl:** Scanning all public repos is infeasible without significant infrastructure. You'd need to sample.
- **Private repo data:** All of this is public-only. Enterprise adoption patterns are invisible to outside researchers.
- **Revenue verification:** ARR figures come from company announcements and journalist sources. You can't independently audit them.
- **Real-time Copilot telemetry:** Only Microsoft has this data. The 46% figure is their claim and can't be independently verified.

## Where to Start

If I were you, I'd start by pulling the AIDev dataset and running the time-series analysis — it's the fastest path to publishable independent findings. Then queue up a BigQuery query against GH Archive for a recent week to check the 4% number. Those two together would give you an informed, data-grounded view of the landscape that goes beyond just citing other people's reports.

Want me to start pulling the AIDev dataset and writing some analysis code?

> I'm ok w/ vendor/unverified claims - presumably they aren't outright lying or they are giving directionally correct stuff especially for public companies or researchers.  there's probably insightful output that no one else is doing, stuff that would be good to know that simply isn't out there and can be extracted/derived/sampled in a clever way (no need for full crawls if we can do statistically valid samples).  private data probably just adds to things.

You're right — let me reframe around what's genuinely novel and achievable. The interesting stuff nobody's doing falls into a few categories.

## The questions nobody's answering

**Is AI expanding the pie or substituting?** This is the most important question and it's answerable. If a repo adopts an agent and total commits go *up* without the human commit rate dropping, AI is additive. If human commits decline proportionally, it's substitution. If total commits explode but most are trivial, it's inflation. Nobody has published this analysis. The AIDev dataset gives you the repo IDs, and you can pull the full commit history for those repos via the API and look at before/after patterns. You'd want to track: commits per human contributor per month, median PR size, issue close rate, and contributor churn — all relative to the date of first agent PR in each repo.

**What are agents actually writing?** The AIDev dataset has file-level diffs and task type classifications. But nobody's done a proper breakdown by language, file type (test vs. source vs. config vs. docs vs. CI), and code complexity. If agents are mostly writing tests, config files, and boilerplate — that's a very different story than if they're writing core application logic. The diffs are right there in the dataset. You could classify by file path patterns alone (`*_test.py`, `*.yml`, `README*`, `src/core/*`) and get a meaningful decomposition in an afternoon.

**The adoption curve shape matters enormously for projections.** SemiAnalysis extrapolates exponentially from two data points. But adoption curves for developer tools historically follow logistic (S-curve) patterns with early-adopter plateaus. The AIDev dataset spans May-August 2025 with timestamps. GH Archive extends that to present. If you sample even one day per week from GH Archive across 12 months, you can fit competing growth models and see which one the data actually supports. The difference between "exponential through 2026" and "logistic approaching 15% ceiling" is the difference between the hype narrative and reality.

**Concentration effects.** Is AI adoption spread evenly or clustered? My strong prior is that it's extremely concentrated — a small number of repos account for the vast majority of agent PRs, certain languages and project types dominate, and there's probably a power law in developer-level adoption (a few power users generating most of the agent PRs, while most developers still don't use agents at all). The AIDev dataset has developer IDs — you could literally plot the Lorenz curve of agent PR contribution per developer and compute the Gini coefficient. If 5% of developers generate 80% of agent PRs, that completely reframes the "widespread adoption" narrative.

**The review burden.** Agent PRs need human review. If agents are generating 4% of commits but those PRs require disproportionate review effort, the net productivity gain is smaller than the commit count suggests. The AIDev curated subset has review comments, review timelines, and revision counts. Compare review cycles (time, rounds of revision, comment density) for agent vs. human PRs *within the same repos*. Nobody's published this at scale.

**Agent-on-agent dynamics.** Are agents fixing each other's code? In repos with multiple agents active, do you see patterns like Copilot generating code → Codex opening a fix PR → human merging? The AIDev dataset has agent labels and repo IDs, so you can identify multi-agent repos and trace interaction patterns. This is a small but fascinating corner case that's probably growing fast.

## A practical research design

Here's what I'd actually build, in priority order:

**Phase 1: AIDev dataset mining (days 1-3)**

Pull the dataset, load it into DuckDB or polars, and produce:

1. **Temporal decomposition** — monthly PR counts by agent, with growth rates and best-fit curve (exponential vs. logistic vs. Gompertz)
2. **Concentration analysis** — Gini coefficient of agent PRs per developer, per-repo distribution, language/ecosystem breakdown
3. **File type decomposition** — what fraction of agent-authored changes are tests, docs, config, CI, vs. core source code
4. **Review dynamics** — using the curated subset, compare time-to-merge, revision count, review comment density for agent vs. human PRs in the same repos
5. **Task type acceptance rates** — independently verify the per-agent, per-task-type acceptance numbers the article cites

**Phase 2: GH Archive sampling (days 3-5)**

Use BigQuery against the `githubarchive.day` public dataset:

1. **4% replication** — sample one full week from early February 2026, count commits with agent signatures (`Co-Authored-By` containing "Claude", "Copilot", bot account patterns, known branch prefixes like `devin/`, `cursor/`), compute the ratio against total commits. Do the same for one week per month going back to January 2025 to build your own time series.
2. **Denominator tracking** — are total commits per day increasing? Plot the raw daily commit count over time to see if AI is inflating the denominator.
3. **Per-developer commit frequency** — for a sample of developers who start using agents (identified by their first agent-tagged commit), compare their commit frequency before and after adoption. This directly answers expansion vs. substitution.

**Phase 3: Repo-level natural experiment (days 5-10)**

This is the most novel piece. Identify repos in AIDev where you can pinpoint the date of first agent PR. Pull their full commit history via GitHub API (stratified sample — maybe 500-1000 repos across different sizes and languages). For each repo, compute before/after metrics:

- Commits per month (total and human-only)
- Unique contributors per month
- Median PR size (additions + deletions)
- Issue open-to-close time
- Code churn rate (lines changed that get changed again within 30 days)

Use interrupted time series or difference-in-differences if you want to be rigorous. Match agent-adopting repos against similar non-adopting repos as controls.

**Phase 4: Dark matter estimation (days 7-12, can overlap)**

Take the fingerprinting approach from the MSR paper (retrain on AIDev data) and apply it to a sample of "human" PRs from the same repos. Even a rough estimate of false-human rate would be valuable. Alternatively, a simpler heuristic approach: look for statistical anomalies in "human" PRs that correlate with known agent signatures — sudden changes in commit message style, code formatting patterns, or PR structure that coincide with the repo's first visible agent usage. If human PRs start looking more "agent-like" after a repo adopts agents, that's evidence of undisclosed AI usage.

## What you'd actually need

- A machine with 64GB RAM would be comfortable for the AIDev dataset work. Your EPYC/RTX setup is massive overkill for this but obviously works.
- A Google Cloud account for BigQuery (free tier gives 1TB/month of queries; a targeted weekly sample approach stays well within that)
- A GitHub personal access token
- Python: polars or DuckDB for the heavy lifting (pandas will struggle with the full AIDev dataset), XGBoost for the classifier, plotly/matplotlib for viz
- Maybe 50-100 hours of focused work for all four phases, less if you're letting Claude Code do the implementation

The output would be genuinely novel. Nobody has published the concentration analysis, the expansion-vs-substitution natural experiment, or the file-type decomposition. And an independent replication of the 4% figure alone would get attention.

Want me to start building the analysis pipeline? I can start with pulling the AIDev dataset and writing Phase 1.

> actually, we know based on App store submissions, website creation and other software release metrics (maybe you can grab those) charts floating around that a *lot* of new software is actually being created. i'm interested to see, are non-software devs writing a lot more software? but a lot of them probably aren't even checking stuff in or even know what github or scm is.

That's a fantastic reframe. The GitHub-centric view completely misses what might be the bigger story — the explosion of software creation by people who've never used git in their lives. Let me find the data.This is where the story gets really interesting. You're absolutely right — the GitHub-centric analysis is looking at the visible tip of an iceberg. Here's the picture that's emerging:

## The "Dark Matter" of AI-Generated Software

There are now essentially **three tiers** of AI-assisted software creation, and the research community is only measuring the first one:

**Tier 1: Professional devs on GitHub (measured, studied)**
This is what SemiAnalysis, AIDev, and all the MSR papers cover. Claude Code, Codex, Copilot, Cursor, Devin. Maybe 30-40% of code in this tier is AI-assisted, but only ~5% is traceable in git metadata.

**Tier 2: Vibe coding platforms (revenue tracked, output unmeasured)**
This is the layer you're pointing at, and the numbers are staggering. Lovable hit $100M ARR in 8 months. Replit's ARR soared from $2.8M to $150M in less than a year. Lovable doubled to $200M ARR in just four more months. Replit's ARR is now approaching $250M, with 40 million users. Vercel's v0, its AI app builder, is used by over 4 million people. By mid-2025, Lovable alone reached over 750,000 apps built in a single month.

These users are overwhelmingly *not* professional developers. Replit explicitly abandoned professional developers as its core market in January 2025, pivoting to "ordinary people who can't write code." And critically — **almost none of this output touches GitHub**. These platforms have their own hosting, their own databases, their own deployment pipelines. Lovable deploys to Netlify/Vercel, Replit hosts natively, Bolt deploys its own way.

**Tier 3: ChatGPT/Claude/Gemini chat-based coding (completely invisible)**
People pasting code from ChatGPT into their projects, local scripts, Google Sheets macros, WordPress customizations, Shopify themes. Zero telemetry, zero tracking, zero git.

## The App Store Signal

The Appfigures data is a concrete indicator: Apple's App Store got 557K new submissions in 2025, up 24% from 2024 — and the commentary around it is telling. This isn't a wave of groundbreaking ideas; it's a wave of clones. AI can replicate the core functionality of a popular app in a matter of minutes. Meanwhile, App Store review times have deteriorated significantly, with developers complaining about "an influx of low-effort, AI-generated apps overwhelming the review process."

That 24% YoY increase in submissions is probably understating it, because Apple also removed 2.6M outdated apps and their review is filtering more aggressively.

## The YC Signal

The YC data is the most credible single data point for the professional tier: a quarter of the Winter 2025 batch had 95% of their codebases generated by AI, and these were all highly technical founders who were "completely capable of building their own products from scratch." That batch grew 10% per week in aggregate — faster than any previous YC batch.

## What Research Would Actually Be Novel Here

This is where your instinct is exactly right. Nobody is measuring the **total volume of software creation across all three tiers**. Here's what you could actually do:

**Proxy metric 1: Deployment platform activity.** Vercel, Netlify, Cloudflare Pages, and Replit all have public or semi-public signals. Vercel has a public showcase/explore. Replit apps are publicly enumerable. You could sample newly deployed sites and classify them (AI-generated vs. hand-crafted) using structural heuristics — AI-generated React apps from Lovable/Bolt have very distinctive patterns (specific Supabase configurations, shadcn/ui component libraries, specific boilerplate structures). This would give you a *rate* of AI-generated deployments on the hosting platforms that vibe coders use.

**Proxy metric 2: npm/PyPI package download patterns.** If non-developers are building more software, you'd expect to see spikes in downloads of "AI-friendly" packages — the ones that vibe coding tools default to (shadcn/ui, Supabase client, Stripe SDK, etc.). Compare download growth rates for packages that appear in AI-generated boilerplate vs. packages that require manual configuration knowledge. This is queryable via npm's public download API.

**Proxy metric 3: Supabase as canary.** Supabase is the default database for virtually every vibe coding platform (Lovable, Bolt, v0). Their growth in new projects/databases is effectively a proxy for vibe-coded app creation. Supabase has published some growth metrics publicly. Cross-reference their reported database creation rates with Lovable/Bolt/Replit user growth.

**Proxy metric 4: Domain registrations + SSL certificates.** Let's Encrypt and Certificate Transparency logs are public. You could look at the rate of new SSL certificates issued for domains that resolve to known vibe-coding hosting (Vercel, Netlify, Replit). This captures deployed software regardless of whether it was git-committed anywhere.

**Proxy metric 5: App Store metadata analysis.** The Apple App Store and Google Play Store have public APIs. You could scrape recent submissions, look at developer account age (new accounts = likely new/non-traditional developers), app complexity, framework fingerprints in crash reports or binary analysis, and creation-to-submission velocity.

**The big synthesis:** Combine the GitHub data (Tier 1, ~4-5% attributed, ~30-40% actual), the vibe coding platform data (Tier 2, hundreds of thousands of apps per month), and the app store data (Tier 3 proxy, 24% increase in submissions) into a single estimate of total AI-generated software output. Nobody has done this.

## The Core Insight

The framing of the original article — "AI is writing X% of GitHub commits" — is looking at the wrong denominator entirely. The right question might be: **AI has expanded the total population of software creators by Nx, and the new creators don't use GitHub at all.** Replit has 40M users. Lovable has 2.3M users. V0 has 4M users. Most of these people have never heard of `git commit`. They're building apps that get deployed and used by real people, and this entire category of software creation is invisible to every analysis that starts from GitHub.

The Gartner forecast that 60% of all new software code will be AI-generated by the end of 2026 might actually be *conservative* if you include this tier — because it's probably measuring code written by developers, not the explosion of software being created by people who were never counted as developers in the first place.

Want me to start prototyping some of these measurement approaches — say, the npm download analysis or Supabase proxy metric?
