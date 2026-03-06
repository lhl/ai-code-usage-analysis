https://chatgpt.com/c/69aa6754-e0ec-83a7-b4b9-75a31e2c271c

> Can we verify or do our own analysis/review of the landscape? ```Agent Commit Analysis: Who's Actually Writing Github's Code?
GitHub processed roughly 1 billion commits in 2025 - about 2.7 million per day across 630 million repositories and 180 million developers. AI agents now author a measurable and rapidly growing share of that output. SemiAnalysis estimates 4% of all public commits come from Claude Code alone - roughly 135,000 commits per day - and that number doubled in a single month. The AIDev dataset cataloged 932,791 agent-authored PRs across 116,211 repos. A study of 129,134 projects found 16-23% agent adoption. Here is the current breakdown by agent, what the research papers say, and what the numbers miss. 
Image
Five agents reshaping github
Five tools now account for effectively all identifiable agent activity on GitHub: Claude Code, OpenAI Codex, GitHub Copilot, Devin, and Cursor. Each has a different model - terminal agent, cloud sandbox, IDE autocomplete, autonomous engineer, AI-native editor - and each leaves a different footprint in git history.
Image
Claude code: 4% and doubling monthly
The headline number from SemiAnalysis (Feb 5, 2026): Claude Code now authors 4% of all public GitHub commits - roughly 135,000 per day. That doubled from ~2% in January. At current trajectory, SemiAnalysis projects 20%+ of daily commits by end of 2026. Weekly active users doubled since Jan 1. Business subscriptions quadrupled.
Anthropic's Claude Code ARR hit $2.5B - the fastest enterprise software ramp ever. Boris Cherny, head of Claude Code, stated his team now uses Claude Code 100% to write code and no longer manually performs even small edits. Accenture signed a deal to train 30,000 professionals on Claude, the largest deployment to date.
Image
Openai codex: most agent PRs, newest models
OpenAI Codex dominates the AIDev dataset with 64.9% of agent-authored PRs and the highest acceptance rate (79.9%). Over 1 million developers use it weekly, with usage up 5x since January 2026. Internally at OpenAI, nearly all engineers use Codex, resulting in 70% more PRs merged weekly. Codex writes 90%+ of its own app's code.
The model lineage moved fast: codex-1 (May 2025) to GPT-5-Codex to GPT-5.2-Codex (Dec 2025) to GPT-5.3-Codex (Feb 5, 2026), plus GPT-5.3-Codex-Spark on Cerebras hardware one week later. The macOS desktop app launched Feb 2, 2026. Sam Altman called it "the most loved internal product we've ever had."
Github copilot: 20M users, invisible in git
Copilot is the most widely adopted AI coding tool by far - 20M+ users, 90% of Fortune 100, 1.3M paid subscribers, 50K+ enterprise organizations. Its coding agent (GA since Sep 2025) generates 1.2 million PRs per month. It now supports multi-model selection: GPT-4o, GPT-5.1-Codex-Max, Claude Opus 4.5, and Gemini 2.0 Flash.
But here is the paradox: Copilot contributes an average of 46% of all code written by active users (61% for Java), yet its inline autocomplete mode leaves zero traces in git metadata. No Co-Authored-By tag, no bot account, no branch prefix. The coding agent does co-author commits, but the vast majority of Copilot usage is the invisible autocomplete. This makes Copilot simultaneously the largest AI code generator and the least traceable.
Devin: the autonomous engineer
Cognition's Devin is the most autonomous agent - it boots a full VM, clones repos, and works independently on 4-8 hour junior engineer tasks. It pushed about 1/3 of commits on Cognition's own web app and has merged hundreds of thousands of PRs across thousands of companies including Goldman Sachs, Santander, and Nubank.
The numbers: ARR grew from ~$1M (Sep 2024) to ~$73M (Jun 2025). After the Windsurf acquisition (~$82M ARR, 350+ enterprise customers), combined ARR hit ~$150M. Cognition raised ~$400M at a $10.2B valuation (Sep 2025). Devin's PR merge rate improved from 34% to 67% year-over-year. It is 4x faster at problem solving and 2x more efficient in resource consumption than a year ago. One banking customer renewed at 10x their $1.5M/yr contract.
Cursor: fastest-growing saas ever
Cursor went from $100M ARR (2024) to $500M ARR (May 2025) to $1B+ annualized in under 24 months - the fastest SaaS growth in history. Valuation: $29.3B after a $2.3B raise in Nov 2025. 1M users, 360K paying, achieved almost entirely through word of mouth.
The NVIDIA case study is the standout data point: 30,000 developers using Cursor daily achieved 3x code commit volume with bug rates staying flat. "Cursor is used in pretty much all product areas and in all aspects of software development" - NVIDIA. Cursor leads in bug fix PR acceptance rate (80.4%) in the AIDev dataset.
PR acceptance rates by agent
Not all agent PRs are equal. The AIDev dataset reveals that no single agent dominates across all task types. Codex wins overall, Claude Code leads documentation (92.3%) and features (72.6%), Cursor leads bug fixes (80.4%).
Image
Full competitive landscape (feb 2026)
Image
Market share is fragmenting fast. Earlier estimates had Copilot at 42% of paid tools market. More recent 2026 data shows a near three-way tie: Copilot ~25%, Claude Code ~24%, Cursor ~24%. The $7B AI coding market is projected to hit $30B by 2032. Copilot now includes Claude and Gemini models alongside GPT, blurring the boundaries further.
Agent fingerprints: 97.2% classification accuracy
Researchers at MSR '26 built an XGBoost classifier using 41 features that identifies which agent authored a PR with 97.2% F1-score. Each agent leaves a distinctive signature in commit messages, PR structure, and code patterns.
Image
What the numbers miss
These statistics dramatically undercount actual AI usage. The AIDev dataset and SemiAnalysis numbers only capture commits and PRs where the agent is identifiable - through Co-Authored-By tags, bot accounts, or branch naming conventions. The vast majority of AI-assisted code ships under the developer's name.
Image
The gap between ~5% (git attribution) and 41% (self-reported AI generation) is roughly 8x. Claude Code is the most visible agent because of its Co-Authored-By convention - which paradoxically makes it look like the dominant one, when Copilot's 20M users generating 46% of their code leave zero traces in commit metadata.
Copilot's 20M users are invisible in git history. Copilot operates primarily as inline autocomplete - it generates code suggestions that developers accept, but the resulting commits are authored entirely by the developer. The coding agent does co-author, but most usage is the invisible autocomplete. Copilot likely generates more total code than any other tool but has the smallest footprint in commit metadata.
The 4% number is simultaneously surprising and understated. Surprising because one tool leaving a traceable signature in 4% of all public commits within months is unprecedented. Understated because the actual percentage of AI-assisted code on GitHub is likely 30-40% and climbing. GitHub Copilot makes "writing code cheaper but owning code more expensive" - larger PRs, higher review costs, 29.1% security vulnerability rate in generated Python, 4x code duplication. Git was built for a world where humans write code. That world is ending faster than the metadata can track.````

Yes — after checking the major claims against GitHub, Microsoft, OpenAI, Anthropic, Cognition, Cursor, and the recent MSR/arXiv papers, my verdict is: the post is broadly right that agentic coding has become measurable and fast-growing on GitHub, but it mixes solid research, company-reported metrics, and a few stale or overstated numbers. The biggest problem is denominator drift: “share of all public commits,” “share of traceable agent PRs,” and “share of code written for Copilot users” are three different things. ([The GitHub Blog][1])

The strongest part of the post is the research layer. AIDev really is a 932,791-agentic-PR dataset spanning 116,211 repositories and 72,189 developers, with data through August 1, 2025. The adoption paper really does study 129,134 projects and estimates coding-agent adoption at 15.85%–22.60%. The fingerprinting paper really does report 97.2% F1 using 41 features. And the task-stratified comparison paper really does find that task type matters a lot: documentation PRs are accepted far more often than new features, with Claude Code leading docs/features and Cursor leading fixes. ([arXiv][2])

A lot of the vendor-scale claims are also real, but often only as company-reported numbers. Anthropic says Claude Code reached general availability in May 2025, has more than $2.5B in run-rate revenue, more than doubled since the start of 2026, and doubled weekly active users since January 1; Accenture separately says it will train about 30,000 professionals and make Claude Code available to tens of thousands of developers. OpenAI says weekly Codex users reached 1.6M by February 27, 2026 and more than tripled year-to-date, and says nearly all OpenAI engineers now use Codex, merging 70% more PRs per week. GitHub and Microsoft say Copilot has 20M+ users, its coding agent contributes about 1.2M PRs per month, and 90% of the Fortune 100 use it. Cognition says Devin grew from $1M to $73M ARR before Windsurf, that Windsurf more than doubled ARR, and that Devin has merged hundreds of thousands of PRs; Cursor says it was above $500M ARR in June 2025, crossed $1B annualized by November 2025, and raised at a $29.3B post-money valuation. ([Anthropic][3])

The first correction I’d make is right at the top: GitHub’s own 2025 Octoverse says **630 million total projects**, not 630 million repositories; it separately reports **395 million public repositories**. And if you combine GitHub’s roughly 1 billion public-commit figure with SemiAnalysis’s 4% Claude Code estimate, that works out to roughly **40 million commits per year** or about **110,000 per day**, not 135,000 per day. So the article’s arithmetic does not match the denominator it cites. ([The GitHub Blog][1])

The Codex section also overstates what the papers show. I could verify the **64.9%** figure only in the **33,580-PR AIDev-pop / fingerprinting subset** after filtering for complete commit metadata, not in the full 932,791-PR AIDev dataset. Likewise, I could verify the **79.9%** figure as Codex’s acceptance rate in an **aligned 11-week sensitivity window** in the task-stratified paper, not as a universal all-time acceptance rate across every slice of the data. Those are meaningful results, but they are narrower than the post implies. ([arXiv][2])

The Copilot section mixes good facts with stale ones. The famous “46% of code, 61% for Java” number is real, but it comes from GitHub’s February 2023 blog and refers to code produced by **Copilot users**, not all GitHub code or a 2026 platform-wide measurement. The subscriber and enterprise counts in the post also look outdated: Microsoft’s 2024 annual report said Copilot had **more than 1.8M paid subscribers** and **over 77,000 enterprise customers**, and by July 2025 Microsoft was saying GitHub Copilot had **20M users** and **90% of the Fortune 100**. ([The GitHub Blog][4])

I would also tighten the model-lineup claim. For the **Copilot coding agent** specifically, GitHub’s February 19, 2026 changelog lists Claude Opus/Sonnet 4.5/4.6 plus GPT-5.1/5.2/5.3-Codex models in the picker. Gemini 2.0 Flash was added to Copilot more broadly earlier, but it is not in that coding-agent picker list, so the post blurs together different Copilot surfaces. ([The GitHub Blog][5])

A few claims I would not repeat as written. I could not verify a primary source for “Codex writes 90%+ of its own app’s code,” for the three-way market-share tie chart, or for “30–40% of all GitHub code is AI-assisted.” The security stat is also slightly off: the accepted empirical paper I found reports security weaknesses in **29.5% of Python** and **24.2% of JavaScript** Copilot-generated snippets, not 29.1%. And the “4x duplication” claim comes from GitClear’s own report; that may be useful evidence, but it is not the same thing as a peer-reviewed study. ([arXiv][6])

My read of the actual landscape is that GitHub now has a clearly measurable **agentic** layer sitting on top of a much larger, harder-to-measure **assistive** layer. The adoption paper explicitly contrasts coding agents that leave traces in commits/PRs with traditional code-completion tools like Copilot, and the fingerprinting paper shows that some hidden agent use can sometimes be inferred from PR behavior. So commit- and PR-based studies almost certainly **undercount** AI usage, especially inline autocomplete, but that does not license jumping from “traceable agent activity is 4–5% of public commits” to “30–40% of all GitHub code is AI-authored.” That leap is plausible as a hypothesis, not established as a fact. ([arXiv][7])

I’d also separate **volume** from **productivity**. Cursor’s NVIDIA case study says 30,000 developers using Cursor commit 3x more code with bug rates staying flat, but METR’s randomized study found that early-2025 AI tools made experienced open-source developers **19% slower** on familiar repositories. Those can both be true because the setting matters: routine, well-scoped tasks and explicit agent workflows seem to benefit first, while context-heavy work on familiar, complex codebases still pays a substantial review and supervision tax. ([Cursor][8])

So the cleaned-up thesis I’d stand behind is: traceable AI agent activity on GitHub is no longer niche; Claude Code’s 4% figure is a serious third-party estimate but not a GitHub-verified fact; Copilot probably has the biggest overall assistance footprint but is much less visible in git metadata; and the most important result from the current literature is not “one agent won,” but that measurement depends massively on which surface you observe. ([SemiAnalysis][9])

A source-backed rewrite of the original post would mostly be about separating verified facts, company-reported claims, and inference.

[1]: https://github.blog/news-insights/octoverse/octoverse-a-new-developer-joins-github-every-second-as-ai-leads-typescript-to-1/ "https://github.blog/news-insights/octoverse/octoverse-a-new-developer-joins-github-every-second-as-ai-leads-typescript-to-1/"
[2]: https://www.arxiv.org/pdf/2602.09185 "https://www.arxiv.org/pdf/2602.09185"
[3]: https://www.anthropic.com/news/anthropic-raises-30-billion-series-g-funding-380-billion-post-money-valuation "https://www.anthropic.com/news/anthropic-raises-30-billion-series-g-funding-380-billion-post-money-valuation"
[4]: https://github.blog/ai-and-ml/github-copilot/github-copilot-now-has-a-better-ai-model-and-new-capabilities/ "GitHub Copilot now has a better AI model and new capabilities - The GitHub Blog"
[5]: https://github.blog/changelog/2026-02-19-model-picker-for-copilot-coding-agent-for-copilot-business-and-enterprise-users/ "https://github.blog/changelog/2026-02-19-model-picker-for-copilot-coding-agent-for-copilot-business-and-enterprise-users/"
[6]: https://arxiv.org/abs/2310.02059 "https://arxiv.org/abs/2310.02059"
[7]: https://arxiv.org/abs/2601.18341 "[2601.18341] Agentic Much? Adoption of Coding Agents on GitHub"
[8]: https://cursor.com/blog/nvidia "https://cursor.com/blog/nvidia"
[9]: https://newsletter.semianalysis.com/p/claude-code-is-the-inflection-point "https://newsletter.semianalysis.com/p/claude-code-is-the-inflection-point"

> Great, independently, what I'd like to do in our session now that we are very familiar w/ the problem is if we were to do our own analysis, what would be involved. We can see there are some datasets, classifiers available. What would we need to be able to do our own research into the topic? Let's rank what we can do by difficulty/value (eg insightful output that no one else is doing, stuff that would be good to know that simply isn't out there and can be extracted/derived/sampled). I'm ok w/ vendor/unverified claims - presumably they aren't outright lying or they are giving directionally correct stuff especially for public companies or researchers, but there's probably a lot of interesting stuff that isn't being tracked at all that *could* be relatively easily.   junior

Yes. I’d frame it as **three separate measurement problems**, because each one needs a different method and has different ceilings on what we can know:

1. **Explicit agent activity**: PRs/commits where the tool is visible in metadata, branch names, bot accounts, trailers, or PR text. This is the easiest layer and already has solid public building blocks: AIDev, AIDev-pop, the human-PR comparison sample, and the fingerprinting replication package. ([arXiv][1])
2. **Inferred hidden AI use**: unlabeled PRs that “look like” agent work but do not declare it. The MSR fingerprinting work gives a real starting point here, but this requires conservative thresholds and manual validation. ([arXiv][2])
3. **Private telemetry / invisible assistance**: Copilot-style completion/chat/agent usage that public Git data will only weakly reflect. GitHub now exposes Copilot usage metrics and code-generation dashboards at org, enterprise, and even user-report levels, but only if you control the org or enterprise. ([GitHub Docs][3])

The minimum viable stack for doing serious work is pretty clear now. You’d want AIDev as the seed label set; AIDev-pop for reviews, timelines, commits, diffs, and linked issues; the human-PR sample for comparison; GH Archive / BigQuery for discovery and trend monitoring; GitHub REST/GraphQL for hydration; and selective repo cloning for anything code-level like static analysis, reverts, or test diffs. One practical caveat: AIDev-pop includes patch data, but large patches are missing because GitHub’s API does not return them, so any quality/security study will need some repo re-fetching. ([Hugging Face][4])

The other thing we’d need is a **time-versioned footprint registry**, not a single detector. GitHub’s event payloads were trimmed starting October 7, 2025, so GH Archive is still great for finding candidates, but not enough by itself for rich post-2025 analysis; you now need to hydrate many objects through the REST API using IDs. On top of that, vendor fingerprints move: Claude Code’s attribution is configurable and can be disabled, and its changelog shows the model name was added to `Co-Authored-By`; Copilot coding agent uses `copilot/` branches and co-authored commits; Codex lets users standardize branch naming and commit/PR prompts. Any detector that ignores that drift will decay fast. ([The GitHub Blog][5])

Operationally, the main bottlenecks are API enrichment and sampling discipline, not model training. GitHub’s secondary limits cap you at 100 concurrent requests, roughly 900 REST points/minute, and 2,000 GraphQL points/minute, so the right pattern is GH Archive for coarse discovery, then REST/GraphQL only for sampled or high-value PRs/repos. From a governance perspective, GitHub’s acceptable-use policy does allow research on public, non-personal information, but publications are supposed to be open access, and source-repo licenses still govern reused patches/files. ([GitHub Docs][6])

Here’s how I’d rank the best studies by **value per unit effort**.

**1) Review tax / human oversight tax** — **difficulty 2/5, upside 5/5**
This is the first study I’d do. Almost everyone talks about code generation volume; far fewer measure the cost pushed onto reviewers. With AIDev-pop you already have PR timelines, review comments, reviews, commits, and patches, and AIDev also ships a human-PR comparison sample from the same repos for large projects. The outcome variables are strong and intuitive: time to first human review, number of review rounds, comments per 1k changed lines, fraction of agent PRs that require human pushups before merge, and close-without-merge after review. That would tell you whether AI is making coding cheaper but review more expensive. ([Hugging Face][4])

**2) Comment-invocation funnel and multi-agent chaining** — **difficulty 2/5, upside 5/5**
This is undertracked and relatively easy. Public GitHub comments are another observable surface besides commits. GitHub officially supports invoking Copilot by mentioning `@copilot` in PR comments/reviews, and OpenAI supports `@codex review` plus other `@codex` tasks in PR comments. That means you can study: how often agents are called into an already-human PR, whether they are used for review vs change requests, how often agent-invoked threads end in merge, and whether a single PR involves multiple agents across code, review, and follow-up. That starts to map the real workflow, not just authorship. ([GitHub Docs][7])

**3) Maintenance tax after merge** — **difficulty 4/5, upside 5/5**
This is probably the most important public-data study that is not really out there yet. Measure whether agent PRs are more likely to be reverted, followed by a fix PR, linked to reopened issues, or touched again in the next 7/30/90 days. You can do a strong public-only version with repo-level matching and follow-up windows; a heavier version adds commit-graph analysis and SZZ-style bug-introducing heuristics. This gets closer to “did it save time overall?” rather than “did it merge?” AIDev-pop already gives much of the linkage scaffolding. ([Hugging Face][4])

**4) Extend the traceable-agent map into 2026** — **difficulty 3/5, upside 4/5**
This is less novel than #1–#3, but still worth doing because the public AIDev cutoff is August 1, 2025. A clean update through 2026 would already be useful if it does two things well: track footprints over time and separate explicit agent PRs from “unknown” rather than pretending unknown means human. GH Archive can give the platform-scale discovery layer, but because payloads were slimmed down after October 2025, you need API hydration and a time-aware detector. ([Hugging Face][8])

**5) Hidden-agent lower-bound estimator** — **difficulty 4/5, upside 5/5**
This is the bridge from “visible” to “actually prevalent.” Use the fingerprinting package as a baseline, retrain with richer text/code/review features, and apply it only with very high precision thresholds to unlabeled PRs. The right output is not “we found the true number”; it is “here is a conservative lower bound, a looser upper bound, and a manual-audit precision estimate.” This is one of the few public-only ways to say something about attribution-disabled or weakly visible agent use without hand-waving. ([arXiv][2])

**6) Private Copilot telemetry join** — **difficulty 5/5, upside 5/5**
If you can get one enterprise or even one org, this jumps near the top. GitHub’s Copilot usage metrics now expose adoption, engagement, code generation, and PR lifecycle trends via dashboard, NDJSON export, and APIs, with org/enterprise/user report endpoints and daily historical reports. Joining that to Git histories and quality metrics would finally let you estimate the “invisible assistance” layer instead of inferring it from Git residue. This is probably the cleanest answer to the Copilot/autocomplete denominator problem. ([GitHub Docs][3])

**7) Developer volunteer panel** — **difficulty 5/5, upside 5/5**
This is the gold standard if you want line-level attribution or prompt-to-PR funnels. You recruit developers who consent to share IDE/CLI telemetry, Git history, and maybe lightweight surveys. Public GitHub cannot tell you whether a line was typed, accepted from completion, rewritten from an agent diff, or pasted from chat; volunteer instrumentation can. Harder politically and ethically, but uniquely valuable.

**8) Another task/language adoption map** — **difficulty 1/5, upside 2/5**
Easy, but I would not do this first. AIDev already supports task types, repo metadata, and language segmentation, so this is fine as context, but it is not where the real white space is. ([Hugging Face][4])

The studies I would **not** spend first cycles on are another generic acceptance-rate leaderboard, another vendor-market-share pie chart, or any attempt to estimate “global AI share of all GitHub code” from public Git alone. Public traces are good for explicit agent PRs and some comment-driven workflows, but they are structurally weak for inline completion usage; that is exactly why the private Copilot metrics layer is so valuable. ([GitHub Docs][3])

So my recommended sequence is:

1. Reproduce AIDev-pop locally and define three classes: **explicit agent**, **inferred agent**, **unknown**.
2. Build **review tax** and **comment-invocation funnel** first. Those are high-signal and relatively cheap.
3. Extend the sample into post–August 2025 GitHub using **GH Archive + API hydration**.
4. Then do **maintenance tax** and a **hidden-use lower bound**.
5. Only after that, chase private telemetry partnerships.

That path gives you genuinely new output fast, without pretending public GitHub can answer the invisible-autocomplete question by itself. The next best move is to turn the top three studies into a concrete schema, sample design, and first-query plan.

[1]: https://arxiv.org/abs/2602.09185 "https://arxiv.org/abs/2602.09185"
[2]: https://arxiv.org/abs/2601.17406 "https://arxiv.org/abs/2601.17406"
[3]: https://docs.github.com/en/copilot/concepts/copilot-usage-metrics/copilot-metrics "https://docs.github.com/en/copilot/concepts/copilot-usage-metrics/copilot-metrics"
[4]: https://huggingface.co/datasets/hao-li/AIDev/blob/main/README.md?code=true "https://huggingface.co/datasets/hao-li/AIDev/blob/main/README.md?code=true"
[5]: https://github.blog/changelog/2025-08-08-upcoming-changes-to-github-events-api-payloads/ "https://github.blog/changelog/2025-08-08-upcoming-changes-to-github-events-api-payloads/"
[6]: https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api "https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api"
[7]: https://docs.github.com/en/enterprise-cloud%40latest/copilot/how-tos/use-copilot-agents/coding-agent/make-changes-to-an-existing-pr "Asking GitHub Copilot to make changes to an existing pull request - GitHub Enterprise Cloud Docs"
[8]: https://huggingface.co/datasets/hao-li/AIDev "https://huggingface.co/datasets/hao-li/AIDev"


