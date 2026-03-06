# AI coding agents in early 2026: what the data actually shows

**Between 5% and 42% of new code is now AI-assisted, depending entirely on what you measure** — and that enormous range is the most important finding of this analysis. Git-level attribution (Co-Authored-By tags) captures roughly 5% of commits from identifiable agents, while developer self-reports claim 42% of their code is AI-generated or assisted. The true figure lies somewhere in this gap, but no methodology yet bridges it credibly. What is clear: AI coding agent adoption is accelerating at unprecedented speed, with Claude Code, Copilot, Cursor, and OpenAI Codex each crossing **$1B+ in annualized revenue** within months of launch. The harder question — whether this code is good, durable, and productive at the organizational level — has increasingly uncomfortable answers from independent research.

This report triangulates vendor claims against academic research, earnings disclosures, and independent surveys. Where numbers are unverified or originate from interested parties, they are flagged explicitly. The goal is to separate signal from hype in the fastest-moving market in software history.

---

## The numbers: what's verified and what isn't

The table below summarizes the verification status of major claims circulating in February–March 2026. Confidence ratings reflect whether claims are confirmed by independent sources, partially confirmed (single credible source), or unverified.

| Claim | Status | Source type | Notes |
|---|---|---|---|
| 4% of public GitHub commits from Claude Code | **Unverified** | SemiAnalysis estimate | Methodology not disclosed; likely Co-Authored-By tag counting. No independent replication |
| ~2.7M commits/day on GitHub (~1B/year) | **Confirmed** | GitHub Octoverse 2025 | 986M commits, +25.1% YoY. Internally consistent |
| Claude Code $2.5B ARR (Feb 2026) | **Confirmed** | Anthropic Series G announcement | Specific to Claude Code, not total Anthropic revenue ($14B) |
| Anthropic ARR surged to $19B+ (Mar 2026) | **Partially confirmed** | Bloomberg via CEO at Morgan Stanley conference | $6B added in February alone |
| Copilot 20M users | **Misleading** | Microsoft earnings (Jul 2025) | GitHub confirmed this is "all-time" signups, not active users |
| Copilot 4.7M paid subscribers | **Confirmed** | Microsoft Q2 FY2026 earnings (Jan 2026) | Commonly cited "1.3M" figure is from Jan 2025 — now outdated by 3.6× |
| Copilot 46% of code written | **Misleading** | GitHub CEO interview | Measures accepted suggestions *in files where Copilot is enabled*, not all code |
| Copilot 1.2M PRs/month from coding agent | **Unverified** | Statistics aggregator sites only | No primary GitHub/Microsoft source found |
| Cursor $2B ARR (Feb 2026) | **Confirmed** | Bloomberg (primary), TechCrunch | Annualized run rate, not trailing revenue |
| Cursor $29.3B valuation | **Confirmed** | Cursor blog, CNBC, BusinessWire | Series D, Nov 2025 |
| NVIDIA 30K devs using Cursor, 3× code output | **Partially confirmed** | Cursor blog (vendor case study) | Named NVIDIA employees quoted, but NVIDIA has not independently confirmed. Headcount concerns (NVIDIA has ~32K total employees) |
| OpenAI Codex 1M+ weekly developers | **Unverified** | OpenAI self-reported | All sources trace to OpenAI's own statements |
| Codex 5× growth since January 2026 | **Unverified** | OpenAI self-reported | Told to Pragmatic Engineer; no independent verification |
| Codex 64.9% of AIDev-pop PRs | **Confirmed** | Academic paper (MSR 2026) | Specific to curated subset (repos with 100+ stars), May–Jul 2025 window |
| Codex "writes 90%+ of its own app's code" | **Partially confirmed** | OpenAI Harness Engineering blog | Self-reported; describes an intentional internal experiment, not typical usage |
| Devin $73M ARR (Jun 2025) | **Confirmed** | Cognition blog, corroborated by Bloomberg/TechCrunch/CNBC |  |
| Windsurf $82M ARR, 350+ enterprise customers | **Confirmed** | Cognition + TechCrunch | Combined ~$155M ARR (Sacra estimate) |
| Devin PR merge rate 34% → 67% | **Partially confirmed** | Cognition self-reported | No independent audit |
| "41% of code is AI-generated" | **Citation laundering** | Likely Sonar survey (42%, n=1,149) | Dozens of sites repeat without attribution; original is developer self-report, not measurement |
| Google 25% → 30%+ AI-generated code | **Confirmed** | Sundar Pichai on Q3 2024 and Q1 2025 earnings calls | Refers to "new code," reviewed and accepted by engineers. 30% code generation → only 10% engineering velocity gain |
| "29.1% security vulnerability rate in Python" | **Unverifiable** | Unknown origin | Closest match: Pearce et al. (2022) found ~38–40%; Tippe et al. (2025) found 16–18%. The specific 29.1% cannot be traced |
| Banking customer renewed at 10× their $1.5M/yr contract | **Not found** | No source located | May be conflated with Devin's 10× migration efficiency metric |
| Gartner: 90% of enterprise engineers use AI by 2028 | **Confirmed** | Gartner press release, Jul 2025 | Updated from earlier "75% by 2028" forecast (Apr 2024) |

---

## What percentage of code is actually AI-generated right now

The honest answer is that **nobody knows**, because every available methodology measures something different, and the most widely cited numbers conflate these measurements.

**Git-level attribution captures ~5% and is growing fast.** SemiAnalysis estimates 4% of public GitHub commits carry Claude Code's Co-Authored-By tag as of February 2026, up from ~2% in January — a monthly doubling. Claude Code adds this attribution by default (opt-out, not opt-in), making it uniquely trackable. A separate MSR 2026 study found **16–23% of 129,134 projects** show some agent adoption trace by October 2025, using file-level and commit-level heuristics across all agents. The AIDev dataset cataloged **932,791 agent-authored PRs** across 116,211 repositories through August 2025, with OpenAI Codex dominating the popular-repo subset at 64.9% of identified agent PRs.

**Self-reported surveys claim 42%.** The Sonar "State of Code" survey (n=1,149, October 2025) found developers report **42% of their code is AI-generated or assisted**, up from 6% in 2023. This is almost certainly the origin of the widely circulated "41%" figure, which appears on dozens of aggregator sites without attribution — a textbook case of citation laundering. The Stack Overflow 2025 survey (n=49,000+) found **84% of developers use or plan to use AI tools**, with 51% using them daily, but did not ask developers to estimate their AI code percentage.

**Big Tech self-reports land at 25–30%.** Google's Sundar Pichai disclosed that **more than 30% of new code** at Google is AI-generated (Q1 2025 earnings call, up from 25% in October 2024). Microsoft's Satya Nadella estimated **20–30%** at a conference in April 2025, with hedged language ("maybe," "probably"). Critically, Pichai clarified on the Lex Fridman podcast that while 30% of code is AI-generated, the actual **engineering velocity increase is only about 10%** — a crucial distinction that most coverage ignores.

**The best estimate for "AI-touched" code in professional settings is probably 25–35%**, considering that Copilot's 4.7 million paid subscribers and Claude Code's doubling user base generate substantial code that leaves no trace in git metadata. But "AI-touched" is not "AI-written" — much of this involves accepting autocomplete suggestions, generating boilerplate, and producing code that is subsequently edited by humans. The fraction of production code that was *wholly* AI-authored, including the review and iteration, is likely in the single digits.

---

## Growth trajectories: agent by agent

### Claude Code hit $2.5B ARR faster than any coding tool in history

Anthropic's Series G announcement (February 12, 2026) confirmed Claude Code's run-rate revenue exceeded **$2.5 billion**, more than doubling since January 1. Weekly active users also doubled in that six-week period. By early March, Bloomberg reported Anthropic's total ARR had surged to **$19B+**, with $6B added in February alone — much of it driven by Claude Code. Enterprise usage now exceeds 50% of Claude Code revenue, with Accenture deploying 30,000 professionals (confirmed via joint press release, December 2025) and **8 of Fortune 10** as Claude customers.

Boris Cherny, Claude Code's creator at Anthropic, confirmed on X (December 27, 2025) that **100% of his code** has been written by Claude Code for months, shipping 22–27 PRs per day using 5 terminal instances simultaneously. Independent analysts correctly note this is "not a realistic measure for most developers" — he has direct access to model development. The SemiAnalysis trajectory (2% → 4% in one month) has not been independently replicated, though the methodology — counting Co-Authored-By tags in GitHub's public event stream — is plausible. The tag is default-on, but multiple GitHub issues show developers actively removing it, introducing both overcounting (trivial commits) and undercounting (stripped attribution) biases.

### OpenAI Codex dominates academic datasets but growth claims are unverified

OpenAI reports **1M+ weekly developers** and **5× growth** since January 2026, but both figures originate solely from OpenAI's statements to press. The Pragmatic Engineer's interview with Codex head Thibault Sottiaux provides the most detailed technical picture: Codex CLI is written in Rust, uses a state machine agent loop, and employs over 100 internal "Agent Skills." GPT-5.3-Codex launched February 5, 2026, scoring **77.3% on Terminal-Bench 2.0** (vs. Claude Opus 4.6 at 65.4%) while trailing on SWE-bench Pro (56.8% vs. 59%).

The most compelling independent data comes from the AIDev dataset: in popular open-source repos (May–July 2025), Codex authored **64.9% of agent-identified PRs** with an **82.59% merge rate** — the highest among all agents. Internally, OpenAI product lead Alexander Embiricos told Lenny's Newsletter that Codex users at OpenAI produce **70% more PRs** than non-users, though critics correctly note this is "a productivity claim, not a quality claim." The Harness Engineering experiment — three engineers building a million-line product with zero hand-written code — is fascinating but explicitly described as an intentional constraint, not standard practice.

### Copilot's real numbers are both bigger and smaller than commonly cited

**The most outdated figure in circulation is Copilot's "1.3M paid subscribers"** — this dates to January 2025. Microsoft's Q2 FY2026 earnings (January 28, 2026) disclosed **4.7 million paid GitHub Copilot subscribers**, up approximately 75% year-over-year. The "20M users" figure, often cited as active users, was confirmed by a GitHub spokesperson as **all-time signups**, not monthly or daily active users. Both corrections significantly change the competitive picture.

The widely quoted "46% of code is written by Copilot" requires heavy qualification. GitHub CEO Thomas Dohmke's exact words: code written by Copilot "in those files where it's enabled." Academic studies find actual acceptance rates of **21–24%** of suggestions, and Communications of the ACM research shows less experienced developers accept more suggestions (31.9%) than experienced ones (26.2%). This creates a paradox: Copilot is simultaneously the largest AI coding tool and the most invisible in git metadata, since autocomplete suggestions leave zero attribution traces.

As of March 2026, Copilot supports models from **OpenAI (GPT-5.3-Codex), Anthropic (Claude Opus 4.6), Google (Gemini 3.1 Pro), and xAI (Grok Code Fast 1)**, effectively transforming from a single-model product into a multi-model platform. This co-opetition dynamic — where Anthropic both powers Copilot and competes with it via Claude Code — is reshaping the competitive landscape.

### Cursor's revenue growth may genuinely be the fastest in SaaS history

Cursor's ARR trajectory is independently confirmed across multiple sources: **$100M (January 2025) → $500M (June 2025) → $1B (November 2025) → $2B (February 2026)**. Bloomberg reported the $2B milestone on March 2, 2026. Sacra's analysis confirms Cursor reached $1M→$100M ARR in approximately 12 months — faster than Wiz (18 months), Deel (20 months), or Ramp (24 months). The **$1B→$2B jump took only three months**, with enterprise customers now accounting for 60% of revenue.

The NVIDIA case study (Cursor blog, February 6, 2026) claims 30,000 developers using Cursor with a **3× increase in committed code and flat bug rates**. WebProNews raised valid skepticism: NVIDIA employs roughly 32,000 people total, and a 3× code output increase across 30,000 engineers "would represent a paradigm shift" with no precedent. Named NVIDIA executives (VP of Engineering Wei Luo, Senior Software Architect Fabian Theuring) were quoted, lending some credibility, but NVIDIA has issued no independent confirmation. The "flat bug rates" claim, if true, would mean absolute bug count tripled alongside code output — a framing choice that obscures reality.

### Devin grew from $1M to $155M ARR in nine months, then acquired its competitor

Cognition's Devin grew from **$1M ARR (September 2024) to $73M (June 2025)**, then acquired Windsurf ($82M ARR, 350+ enterprise customers) in July 2025 for an estimated ~$250M in what SaaStr characterized as a "distressed sale" — Windsurf's leadership had been poached by Google in a $2.4B reverse-acquihire days earlier. Combined ARR reached approximately **$155M** (confirmed by Sacra and Summit Ventures). The September 2025 funding round ($400M at $10.2B valuation) was confirmed by CNBC and VentureBeat. Goldman Sachs CIO Marco Argenti independently confirmed Goldman's adoption, telling CNBC: "We're going to start augmenting our workforce with Devin, which is going to be like our new employee."

Cognition's self-reported metrics show PR merge rates improving from **34% to 67%** and claim **4× faster problem solving** and **2× resource efficiency**, but none of these have been independently audited. The specific claim about a banking customer renewing at 10× their $1.5M contract could not be found in any public source and may be conflated with a 10× migration efficiency metric from Devin's performance review blog.

---

## The measurement gap explains why numbers diverge so wildly

This is the most analytically important section. The AI coding adoption debate is plagued by five distinct measurement approaches that produce incompatible numbers, yet are routinely conflated:

**Git attribution (measuring ~5%)** captures only agents that leave explicit traces. Claude Code's Co-Authored-By tag is default-on; Copilot leaves zero trace. The MSR 2026 agent fingerprinting paper achieved **97.2% F1-score** classifying which agent authored a PR using 41 features (commit message patterns, PR structure, code change characteristics, patch-level features, temporal patterns). Agent-specific signatures include Codex's distinctive multiline commits (67.5% feature importance), Cursor's bullet-heavy descriptions, and Claude Code's dense comments. This classifier *can* be applied retroactively to detect undisclosed AI usage, but the authors note "human" PR baselines may already be contaminated.

**Identifiable agent PRs (AIDev dataset)** cataloged 932,791 PRs but only from known bot accounts and branch patterns. The "Agentic Much?" study (arXiv:2601.18341) used broader heuristics — file-based traces like `.cursorrules`, commit co-authoring patterns, PR metadata, documentation markers — and found **16–23% adoption** across 129,134 projects. Both approaches miss code generated by AI but committed under human accounts without attribution.

**Autocomplete acceptance rates (Copilot's "46%")** measure something fundamentally different: how much of the code typed in a file was suggested by AI and accepted via Tab key. This metric applies only to active users with the tool enabled, says nothing about whether code survives to production, and is measured solely by GitHub's internal telemetry with no independent verification. Academic studies consistently find lower acceptance rates (**21–24%**) than vendor-reported figures.

**Self-reported surveys (42%)** capture developer perception, which diverges significantly from measured reality. The METR study found developers believed AI made them **20% faster** when they were actually **19% slower** — a **39-point perception gap**. The Sonar survey's 42% is developer self-report, not instrumented measurement. BNY Mellon's study of 2,989 developers found most save less than 1 hour per week despite high satisfaction scores.

**Revenue and ARR ($4B+ market)** measure willingness to pay, which is real but tells you nothing about code output. Cursor generates $2B ARR from usage-based pricing; Claude Code generates $2.5B. Neither metric reveals what fraction of production code these tools actually produce.

### The denominator is also shifting

GitHub commits grew **25.1% year-over-year** to ~1 billion in 2025, while the developer base also grew ~25% (to 180M+). Per-developer commit rates appear roughly flat at the platform level. However, controlled enterprise studies show Copilot users create **8.7–21.8% more PRs** per week, and Faros AI telemetry shows AI users interact with **47% more PRs daily**. If AI tools cause more, smaller commits, the "percentage of commits" metric is increasingly misleading as a measure of code volume. A 4% share of an inflating denominator represents something different than 4% of a stable one.

---

## Market dynamics: a three-way race with a platform play

CB Insights' December 2025 analysis of the **~$4 billion AI coding market** found it "crystallizing around 3 leading players who hold just over 70% of the market": GitHub Copilot, Claude Code, and Cursor, all above $1B ARR. The often-cited "Copilot 42% market share" appears to refer to either North American regional share or developer usage rates (Stack Overflow), not revenue share — resolving the apparent discrepancy with the "near three-way tie" framing.

The competitive picture is complicated by Copilot's multi-model strategy. By offering Claude, Codex, and Gemini as selectable models, GitHub transforms Copilot into a **distribution platform** rather than a single product. Anthropic both powers Copilot (revenue) and competes with it (Claude Code). This co-opetition is the defining strategic tension of the market.

Market size projections vary wildly across research firms — from $220M to $29.5B for 2025 alone — because definitions differ radically (narrow IDE assistants vs. broad AI developer platforms). The most credible mid-range estimate for narrowly defined AI coding tools is approximately **$4–7B in 2025**, projected to reach **$24–37B by 2030–2032** at 25–27% CAGR. These figures come from Mordor Intelligence and SNS Insider, though all commercial market research firms' methodologies are opaque.

---

## Quality and security concerns are growing, not shrinking

Independent research increasingly challenges the "more code, more productivity" narrative. **GitClear's analysis of 211 million lines of code** (2020–2024) found an **8-fold increase in duplicate code blocks** during 2024, with refactored/"moved" code declining from 25% to less than 10% of changed lines. Copy/paste code rose from 8.3% to 12.3%. Code churn for new code increased from 5.5% (2020) to 7.9% (2024). The original 2024 report predicted 4× duplication; reality was 8×.

The DORA State of DevOps reports show a nuanced trajectory. The **2024 report** found AI adoption accompanied by an estimated **1.5% decrease in delivery throughput** and **7.2% reduction in delivery stability**. The **2025 report** (nearly 5,000 respondents) showed improvement — throughput turned positive — but **stability still declined**. DORA's central finding: "AI doesn't fix a team; it amplifies what's already there." Teams with loosely coupled architectures and fast feedback loops benefit; tightly coupled systems see little gain.

Academic findings from the MSR 2026 conference reinforce these concerns. Agent-introduced code symbols (functions, classes) are **removed in a median of 3 days** versus 34 days for human-authored symbols, with code churn rates of **7.33% versus 4.10%**. Static-analysis warnings rise approximately 18% and cognitive complexity increases approximately 39% after agent adoption. Security research on the AIDev dataset found security-related agentic PRs receive **3.92 hours median review time** versus 0.11 hours for non-security PRs, indicating humans apply heightened scrutiny — though Codex security PRs still achieve an 86.59% merge rate.

The seminal Pearce et al. study (IEEE S&P 2022) found **~40% of Copilot-generated programs contained vulnerabilities**. More recent work by Tippe and Schreiber (2025) analyzing 7,703 files from public GitHub repos found lower rates: **16–18% for Python**, suggesting improvement over time. The specific "29.1% vulnerability rate" widely cited in 2026 coverage **cannot be traced to any published study** and appears to be a misquotation or conflation of different metrics.

---

## Projections for end of 2026: three scenarios

### Conservative scenario: 8–12% of commits are agent-attributed

This assumes current growth rates decelerate as early adopters are absorbed, enterprise security and compliance reviews slow rollout, and the novelty effect fades. Cursor and Claude Code ARR growth slows from monthly doubling to quarterly doubling. Copilot's installed base grows steadily but code contribution per user plateaus. Total identifiable agent commits reach 8–12% of GitHub's public stream. Total AI-assisted code (including invisible autocomplete) reaches approximately 35–40% for active tool users but remains at 25–30% across all professional developers.

### Base scenario: 15–20% of commits are agent-attributed

This assumes Claude Code's trajectory continues but with diminishing monthly growth rates (30–50% monthly rather than 100%), Codex and Copilot's coding agents mature and gain market share, and enterprise adoption accelerates through H2 2026 as contracts signed in early 2026 deploy. The 16–23% project-level adoption found in October 2025 grows to 30–40%. Total AI-assisted code reaches 40–50% for professional developers using tools.

### Aggressive scenario: 20%+ of commits from Claude Code alone

This is SemiAnalysis's projection, extrapolating the January–February 2026 doubling rate. It requires sustained exponential growth for 10+ months, which faces significant headwinds. Ceiling effects emerge as the remaining non-adopters are disproportionately in regulated industries, legacy codebases, and security-sensitive environments. Model costs, rate limits, and API reliability constrain heavy usage. The growing evidence of quality and security concerns may trigger enterprise pullbacks. Even Anthropic's own data shows enterprise adoption is primarily in financial services, life sciences, and tech — not evenly distributed. **No software tool has ever maintained monthly doubling of usage for a full year.** Gartner's updated forecast (90% of enterprise engineers using AI assistants by 2028) implies the adoption curve extends years, not months.

**The base scenario is most credible.** Agent-attributed commits will likely reach 15–20% of GitHub's public stream by end of 2026, with total AI-assisted code (including invisible Copilot autocomplete) representing 40–50% of new professional code by tool-using developers. The critical caveat: "more code" continues not to equal "better outcomes" at the organizational level, based on every independent study to date.

---

## What we still don't know

Several critical questions remain unanswered as of March 2026. **No one has measured what fraction of AI-assisted code survives to production.** The gap between "code generated" and "code shipped and maintained" could be enormous, and no study has attempted to bridge it. Copilot's autocomplete contribution remains a black box — GitHub's internal telemetry is the only source, and the 46% figure is routinely misrepresented as applying to all code rather than active-user files.

**The long-term maintenance cost of AI-generated code is unknown.** GitClear's churn data and the MSR 2026 finding that agent-introduced symbols are removed in 3 days versus 34 suggest significant durability concerns, but no study has tracked AI-generated code over years. Similarly, **no independent financial audit of any AI coding company's ARR figures exists** — all revenue numbers originate from the companies themselves or from analyst firms citing those same disclosures.

The "Agentic Much?" paper's finding that "human" PRs in academic datasets may be contaminated with undisclosed AI usage raises fundamental **ground truth concerns** for all comparative studies. If the "human" baseline is already partially AI-generated, measured differences between human and agent code are understated. The fingerprinting classifier (97.2% F1-score) offers a path to retroactive detection, but it has not been applied at scale.

Perhaps most importantly, **the relationship between AI coding output and actual business value remains unquantified.** Google's disclosure that 30% AI-generated code produces only 10% engineering velocity gain is the most honest data point available, yet it comes from a single company. The METR finding that developers were actually 19% slower with AI tools, combined with the DORA finding of declining delivery stability, suggests that at the organizational level, the productivity revolution may be significantly overstated — even as individual developers genuinely benefit from reduced boilerplate and faster prototyping. The 2026 story is not "AI is writing all the code" but rather "AI is writing a lot of code, and we don't yet know whether that's good."