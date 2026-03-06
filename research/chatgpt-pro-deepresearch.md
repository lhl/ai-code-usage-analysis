https://chatgpt.com/c/69aa68be-7358-83a7-947e-8db0f11c8347

# AI Coding Agent Adoption on GitHub and in Professional Development as of Early March 2026

## Executive Summary

- Measurable, *attributed* “agentic” activity on GitHub (PRs opened by recognizable agent accounts/branch patterns/signatures) is still a small fraction of GitHub’s overall throughput, even though the absolute volumes are already large: GitHub reports **~43.2M PRs merged per month** and **~986M commits in 2025**, while the largest public dataset of agent-authored PRs (AIDev) contains **~933K agentic PRs** (across five agents) through **Aug 1, 2025**. citeturn21view0turn7view1turn8view0  
- The *undercount* is structurally severe: the most common, highest-volume “AI coding” mode is still **inline assistant / autocomplete**, which leaves **no reliable git-level signature**, while even signature-based agents can have attribution **disabled**. citeturn4search14turn28view0turn5view0  
- Independent academic work is now explicitly warning that “human” PR corpora are likely contaminated by undisclosed agent use, and proposes behavioral “fingerprints” that can identify which agent produced a PR with **~97% F1** using PR/commit/text features—suggesting “hidden agentic” contributions may be measurable, but only via inference, not direct provenance. citeturn27view0turn27view1turn27view3  
- In professional (private) software development, the most credible “how much code is AI-assisted?” signals remain internal disclosures from large engineering organizations: **Google** publicly stated **“more than a quarter” of new code is AI-generated** (then reviewed/accepted by engineers), and **Microsoft** leadership publicly discussed **~20–30%** for some repos/projects. These are not GitHub-public measures, but they anchor plausible ranges. citeturn23search1turn23search11  
- End‑2026 projections depend more on *which metric you choose* than on raw growth. Extrapolating “percent of commits” from short windows is especially fragile because AI tools can change *commit granularity*, not just total shipped code. GitHub’s own platform data already shows **commits up +25% YoY** while **comments on commits down −27%**, consistent with “more code, less human review per unit”—which can inflate “% of commits” without a proportional increase in business value delivered. citeturn21view0turn22view2  

## The Numbers That Are Verified

The table below separates (a) claims that are **directly supported by primary/official sources**, (b) claims that are real but **self‑reported / journalist‑sourced** (not independently auditable), and (c) claims that currently look **methodologically underspecified** or are **easy to misinterpret**.

| Claim | Best primary source(s) found | Verdict | What it actually means (and key caveats) |
|---|---|---|---|
| GitHub had **~986M commits** in 2025 (+25.1% YoY) | GitHub’s Octoverse 2025 post | Confirmed | This is a *platform activity* metric (code pushes / commits), not “lines shipped,” and it reflects behavior changes as well as output. citeturn21view0 |
| GitHub merged **~43.2M PRs/month** in 2025 (+23% YoY) | GitHub’s Octoverse 2025 post | Confirmed | A PR-based denominator for agent PRs; but PR counts can increase if teams shift to smaller PRs. citeturn21view0turn22view3 |
| GitHub public/open-source activity in 2025: **~1.12B contributions**; **~518.7M merged PRs** | GitHub’s Octoverse 2025 post | Confirmed | This is the headline public/open-source activity baseline, but “contributions” includes many event types. citeturn22view1turn22view3 |
| **AIDev** aggregates **~932,791 agentic PRs** across **116,211 repos** and **72,189 developers**, cutoff **Aug 1, 2025** | AIDev MSR’26 dataset paper; AIDev dataset card | Confirmed | “Agentic PRs” here are those attributable via recognizable signatures/queries, not all AI-assisted work. citeturn7view0turn7view1turn8view0 |
| AIDev “popular repos” subset has **33,596 PRs**; and in that subset **OpenAI Codex ~64.9%** of PRs | AIDev dataset card; fingerprinting paper uses similar distribution | Confirmed | The 64.9% figure is *for the curated/popular subset*, not the full dataset. citeturn8view0turn27view0 |
| In the **full** AIDev dataset, **OpenAI Codex** accounts for **814,522 / 932,791** agentic PRs (~87%) | AIDev dataset card | Confirmed | This dominance is largely a function of *how AIDev identifies Codex PRs* and the period when Codex PR-automation ramped. citeturn8view0 |
| AIDev’s PR identification relies on **agent-specific GitHub search queries** (e.g., branch prefixes; explicit “Co‑Authored‑By” strings) | “Rise of AI Teammates” paper (AIDev methodology table) | Confirmed | This is a core reason AIDev undercounts “invisible” AI and can bias agent shares. citeturn10view5 |
| “Claude Code is 4% of public GitHub commits; could be 20%+ by end‑2026” | SemiAnalysis (paid article excerpt) | Unverified | The claim exists, but the excerpt available does not fully specify a reproducible method. Treat as an estimate, not a measured fact. citeturn2view0 |
| Anthropic states Claude Code run‑rate revenue is **>$2.5B**, **>2× since Jan 1, 2026**; weekly active users **doubled** since Jan 1 | Anthropic Series G announcement | Confirmed (self‑reported) | These are official claims, but not independently audited in the announcement. Useful for *directional* adoption signals. citeturn25view0 |
| Anthropic reports overall run‑rate revenue **$14B**, “growing over 10× annually” for three years | Anthropic Series G announcement | Confirmed (self‑reported) | Strong indicator of demand; not a direct measure of “code written.” citeturn25view0 |
| OpenAI internal “harness engineering” experiment: **0 manual lines**, **~1M LOC**, **~1,500 PRs merged** over ~5 months | OpenAI engineering blog | Confirmed (self‑reported) | Demonstrates what “agent-written code” means in a controlled internal workflow; not representative of all teams. citeturn26view0 |
| “Codex is used by **>1M developers weekly**; usage **5× since Jan**; Altman quote about internal product” | Pragmatic Engineer deep dive (paid) | Partially confirmed | Reported as sourced from OpenAI interviews and links; still not audited platform telemetry released publicly. citeturn25view1 |
| Cursor has **~$2B annualized revenue** (reported) | TechCrunch; Bloomberg | Partially confirmed | Strong journalism, but attributed to “a person/source familiar” rather than audited filings. citeturn24search1turn24search12 |
| Google: **“more than a quarter”** of new code is AI-generated (reviewed/accepted by engineers) | Google/Alphabet published CEO remarks | Confirmed | A rare, high-signal disclosure about *AI-assisted code share* in a large engineering organization. citeturn23search1turn23search5 |
| Microsoft: **~20–30%** of code in some repos/projects said to be written by AI | TechCrunch report on Nadella remarks | Confirmed (reported quote) | A public leadership statement; still ambiguous whether “% of lines,” “% of files,” or “% of changes.” citeturn23search11 |
| Stack Overflow 2025: **84%** of respondents use AI tools (daily/weekly/etc); **~31%** currently use AI agents at work (daily/weekly/monthly) | Stack Overflow Developer Survey 2025 | Confirmed | Survey data = self-report, but valuable for distinguishing “agents” vs “copilot mode.” citeturn28view0 |
| Claude Code commit/PR attribution can be customized or hidden (empty string hides) | Claude Code docs | Confirmed | Direct evidence that signature-based measurement can be defeated by normal configuration. citeturn4search14 |
| Fingerprinting paper: multi-class XGBoost identifies agent with **~97.2% F1**, reduced to **41 features** | Fingerprinting AI Coding Agents paper | Confirmed | Enables *inference-based* estimation of hidden agent use; also highlights dataset contamination risk. citeturn27view0turn27view1turn27view2 |
| Acceptance rates (11‑week aligned window): Codex **79.9%**, Cursor **74.4%**, Claude **72.6%**, Devin **68.0%**, Copilot **68.0%** | Task-stratified acceptance paper | Confirmed | Acceptance/merge rates are outcome metrics for *agentic PRs*, not for autocomplete or human-edited patches. citeturn1search3turn1search16 |

## Current State of AI Code Generation

“AI-written code” currently spans at least three distinct realities, with different measurability:

1) **Agentic PRs/commits**: an AI tool (or bot account) proposes a PR/commit as a first-class artifact. This is most measurable. AIDev targets this category. citeturn7view1turn10view5  
2) **AI-assisted editing (copilot/autocomplete/chat)**: the AI proposes snippets and developers accept/modify them directly in the IDE. This is high-volume but mostly invisible in git metadata. citeturn28view0  
3) **Human-submitted PRs with heavy agent involvement**: developers run agent loops locally, then submit under their own identity; these can be partially detectable via behavioral fingerprints, but provenance is not explicit. citeturn27view3turn5view0  

### What we can bound from GitHub-wide denominators

GitHub’s Octoverse data gives a hard sense of scale: **~43.2M PRs merged/month** and **~986M commits/year** (2025). citeturn21view0turn22view2  

AIDev, the largest public dataset focused specifically on *agent-authored PRs* for five major agents, contains **~932,791 agentic PRs** through **Aug 1, 2025**. citeturn7view1turn8view0  

A simple ratio (with major caveats) illustrates why “agentic PR share” and “AI-assisted code share” are different universes:

- If GitHub merges ~43.2M PRs/month (≈518.7M/year), then ~933K agentic PRs over ~7 months is on the order of **<1% of yearly PR merges**, and likely **well below 1%** of total PR activity once you account for (a) PRs created vs merged and (b) the fact AIDev counts only *recognizable* agent PRs. citeturn21view0turn22view3turn8view0  

This strongly suggests: **today’s explicitly attributable “agents submitting PRs” are not yet the majority of how AI is changing software development**, even if the absolute count of agent PRs is already in the hundreds of thousands. citeturn28view0turn10view5  

### A best estimate for “AI-assisted” code share in professional development

For professional (mostly private) development, the most credible anchor points are internal disclosures:

- **Google**: “more than a quarter of all new code at Google is generated by AI,” *then reviewed and accepted by engineers*. citeturn23search1turn23search5  
- **Microsoft**: leadership publicly discussed **~20–30%** of code in some repos/projects being “written by software (AI).” citeturn23search11  

These statements are not GitHub‑public measurements, but they imply that in AI-forward large orgs, **AI assistance plausibly sits in the ~25–30% range of newly produced code** (as they define it). citeturn23search1turn23search11  

Outside top-tier adopters, survey data suggests fast uptake of “AI tools” but slower uptake of “agents” specifically:

- Stack Overflow’s 2025 survey reports **84%** of respondents use AI tools (daily/weekly/monthly), while for “AI agents at work,” only **~31%** report current use (daily/weekly/monthly), with additional groups either planning to use agents or staying in copilot/autocomplete mode. citeturn28view0  

Putting these together, the most defensible March‑2026 statement is:

- **AI-assisted editing** is already mainstream among surveyed developers, but **agentic workflows that reliably submit PRs are not yet mainstream**, and the share of shipped code attributable to autonomous PR-submission remains hard to bound from public data. citeturn28view0turn7view1  

## Growth Trajectories and Agent-by-Agent Signals

### What AIDev shows about early agent PR ramp

AIDev’s public “cumulative PR” plot (through Aug 2025) shows a sharp inflection where **OpenAI Codex** PR volume expands rapidly compared with the other four agents in the dataset. citeturn18view0turn8view0  

Even without perfect monthly bucketing, the direction is clear: from May→Aug 2025 the dataset’s Codex-attributed PRs grow to **~800K+ cumulative**, while the other agents remain in the tens of thousands or fewer by Aug 2025. citeturn18view0turn8view0  

Crucially, the “Rise of AI Teammates” paper documents that AIDev’s collection relies on platform-visible cues (branch prefixes, bot authors, explicit strings like “Co‑Authored‑By”), so *ramp speed is entangled with product defaults and identification heuristics*, not just true usage. citeturn10view5turn4search14  

### Quality/acceptance as a growth constraint

One MSR’26 paper analyzing PR acceptance in an aligned time window reports acceptance rates for agentic PRs where **Codex is highest (79.9%)** and others trail; it also reports variation across agents and task types, suggesting that “more PRs” does not mean “more accepted PRs,” and acceptance is likely a key saturation force. citeturn1search3turn1search16  

### Revenue and usage as indirect adoption signals

Because output is hard to measure directly, revenue and active-user growth are often used as proxies—with the caveat that these are *willingness-to-pay* metrics, not code volume.

- entity["company","Anthropic","ai lab, us"] reports **Claude Code run-rate revenue >$2.5B**, more than doubling since Jan 1, 2026, and **weekly active users doubled** since Jan 1 (company statement). citeturn25view0  
- A reported growth datapoint for entity["company","Cursor","ai code editor company, us"]: Cursor has reportedly surpassed **$2B in annualized revenue**, according to a Bloomberg-sourced report and TechCrunch coverage. citeturn24search12turn24search1  
- entity["company","OpenAI","ai lab, us"] provides a concrete internal “agent-first” case study: a team reports building an internal product with **0 manually-written lines**, ~**1M LOC**, and **~1,500 PRs opened/merged** over ~5 months, with large claimed speedups. citeturn26view0  
- A reported usage datapoint via entity["organization","The Pragmatic Engineer","newsletter, gergely orosz"]: “more than a million developers use Codex every week” and usage increased **5× since early Jan 2026,” presented as sourced from interviews. citeturn25view1  

image_group{"layout":"carousel","aspect_ratio":"1:1","query":["Anthropic logo","OpenAI logo","GitHub Copilot logo","Cursor AI coding assistant logo","TechCrunch Cursor AI coding assistant"],"num_per_query":1}

## The Measurement Gap

The central analytical takeaway from triangulating GitHub platform stats, public datasets, and methodology papers is:

> **There is no single “% of code written by AI” number that is simultaneously meaningful, measurable, and comparable across tools.**

### Why common metrics disagree

**Git-trailer attribution (e.g., `Co-Authored-By`)**  
Claude Code (and similar tools) can add attribution to commits/PRs, which creates a measurable public trace. But the same Claude Code documentation explicitly allows this attribution to be **customized or hidden**, and AgentPack notes that some invocation paths or settings can suppress visible signatures. citeturn4search14turn5view0  
Implication: **signature-based measures are lower bounds** and can be biased by defaults and user preferences.

**Dataset-defined “agent PRs” (AIDev, AgentPack)**  
AIDev’s own methodology uses targeted GitHub search queries (branch prefixes, bot accounts, explicit strings). That means it captures “agentic PRs that look like agentic PRs,” rather than “all PRs heavily influenced by agents.” citeturn10view5turn7view1  
AgentPack similarly mines GitHub public timeline signals (e.g., looking for Claude Code’s co-author string; Codex PR description patterns) and explicitly warns that the dataset “likely omits a significant amount” of agent-authored code, including paths that don’t sign their activity. citeturn5view0

**Surveys**  
Stack Overflow’s survey cleanly distinguishes “AI tools” vs “AI agents,” showing that “agents” are not yet mainstream even if AI tools broadly are. But surveys do not produce reliable “% of code” denominators; they measure *developer perception and usage frequency*. citeturn28view0  

**Platform-level activity baselines**  
GitHub shows strong growth in commits and PRs, but also states these are “observational signals rather than causal claims.” It also reports a sharp decline in comments on commits. If AI causes developers to commit more frequently in smaller chunks, “% of commits” can rise even if “% of shipped functionality” rises more slowly. citeturn22view2turn21view0  

### A plausible “undercount multiplier,” grounded in evidence

A frequently repeated narrative is: “attributed AI commits are small, but real AI involvement is much larger.” Two concrete mechanisms support that:

- The simplest mechanism is configurability: attribution can be removed by normal configuration. citeturn4search14  
- The stronger mechanism is *behavioral contamination*: the fingerprinting study argues that even PRs submitted under a human account can carry agent fingerprints, and explicitly warns that datasets separating “human” from “agent” PRs based on submitter identity risk mislabeling and invalid conclusions. citeturn27view3turn27view0  

Separately, an empirical study of agentic coding workflows reports that in their analyzed context, **41.6% of revision commits were co-authored by Claude Code**, and review threads referenced multiple tools—evidence that “AI involvement” can be substantial even when not cleanly attributable to a single “agent PR.” citeturn9search2  

## Fingerprinting and Classification Research

The most direct answer to “can we estimate hidden agent usage?” in the current literature is: **yes, partially—by modeling behavior rather than provenance**, with important limitations.

The fingerprinting paper reports:

- A supervised classifier (XGBoost) trained on agentic PRs achieves **~97.2% F1** in identifying which of five agents produced a PR, using a reduced set of **41 features** spanning: commit message patterns, PR structure, code-change properties, patch-level code characteristics, and temporal patterns. citeturn27view0turn27view1turn27view2  
- The paper’s “signatures” are concrete and match common anecdotes: e.g., Codex associated with extensive multi-line commits; Copilot with longer PR descriptions and higher change concentration; Cursor with bullet points/hyperlinks in PR bodies; Claude Code with code-level traits like higher conditional density and elevated comment density. citeturn27view2turn27view3  

Practical implications:

- This approach could be applied retroactively to PRs not explicitly labeled as agent-authored, but only as an **inference** (not proof), and only within the scope/representativeness of the training data (public GitHub; these five agents; this period). citeturn27view3turn27view0  
- The same paper emphasizes the governance challenge: if policy enforcement depends on identifying AI contributions, then purely metadata-based approaches are brittle, while behavioral classifiers require maintenance as tools evolve. citeturn27view3  

## Market and Competitive Dynamics

A market view is useful mainly to understand *which tools have distribution and incentives to change developer workflow quickly*—but it is not a direct proxy for “code volume.”

Platform distribution and usage environment:

- entity["company","GitHub","code hosting company, us"] reports ~180M+ developers on the platform and indicates that AI adoption starts quickly for new developers (nearly 80% using Copilot in their first week), alongside record activity growth. citeturn21view0turn22view1  
- This matters because the easiest path to massive “AI share” is not autonomous PR submission—it is ubiquitous inline assistance integrated into default workflows. citeturn28view0turn21view0  

Revenue signals (directional, not audited output):

- entity["company","Anthropic","ai lab, us"] positions agentic coding as a primary growth driver, explicitly stating Claude Code run-rate revenue **>$2.5B** and rapidly growing enterprise usage. citeturn25view0  
- entity["company","Cursor","ai code editor company, us"] is reported (via Bloomberg/TechCrunch) to have surpassed **$2B annualized revenue**, with a large enterprise component—implying meaningful corporate adoption even if it’s not directly measurable on public git traces. citeturn24search12turn24search1  
- entity["company","OpenAI","ai lab, us"] showcases an “agent-first” internal development model that is explicitly throughput-driven (hundreds/thousands of PRs) and attempts to mechanize review and knowledge management for agents. citeturn26view0  

## Quality and Security Implications

The most relevant 2025–2026 empirical evidence in the provided source set focuses on *agentic PR properties*, review dynamics, and security-related PRs.

- A large-scale study of how coding agents modify code (merged agentic PRs vs merged human PRs) reports substantial differences in commit counts and some differences in files touched and deleted lines, emphasizing that agentic PRs are behaviorally distinct artifacts—not just “human PRs but faster.” citeturn1search2turn1search9  
- A security-focused empirical study finds that security-relevant agentic PRs are a non-trivial portion of activity (~3.85% in their curated set), and that security-related agentic PRs show **lower merge rates and longer review latency** than non-security PRs—consistent with heightened scrutiny. citeturn1search1turn1search5  

A critical nuance for forecasting:

- If agents increase raw throughput, then **human review bandwidth becomes the bottleneck**, and systems will either (a) become more reliant on agent-to-agent review (as OpenAI’s internal writeup describes), or (b) accept greater risk, or (c) constrain agent autonomy. citeturn26view0turn22view2  

## Projections for End of 2026 and Open Questions

### Scenarios for “how much code is written by AI” by end of 2026

Because the measured quantities are not commensurate, projections must be phrased as **ranges by metric**.

**Conservative scenario (end‑2026)**  
AI-assisted tools are near-universal among active developers, but autonomous PR-submitting agents remain bounded by workflow friction, review bottlenecks, and policy constraints.

- “Agentic PRs” as a share of GitHub PR merges: **low single digits** (e.g., ~1–3%). Rationale: today’s attributable agent PRs are tiny vs. GitHub’s PR volume baseline, and “agents” are not yet mainstream in survey adoption. citeturn21view0turn28view0turn7view1  
- “AI-assisted code” share inside professional orgs: **~25–40%** median, reflecting continued spread from AI-forward leaders like Google/Microsoft to the broader industry. citeturn23search1turn23search11turn28view0  

**Base scenario (end‑2026)**  
Agentic workflows become mainstream *for specific task classes* (maintenance, refactors, docs, tests), while copilot/autocomplete remains the dominant AI modality.

- Publicly attributable “agentic PR” share: **~3–7%** in public repos where such tooling is permissible and integrated, with much higher shares in high-adoption projects/teams. Rationale: revenue/user growth claims from major vendors imply rapid adoption, but review infrastructure becomes the binding constraint. citeturn25view0turn24search12turn26view0  
- AI-assisted share of newly written code in professional settings: **~35–55%** for many teams, driven by default AI-on IDEs and organizational mandates. Rationale: already >25% at Google (Oct 2024), plus strong survey evidence of daily use. citeturn23search1turn28view0  

**Aggressive scenario (end‑2026)**  
Agentic systems materially change the unit of work, pushing toward “specify intent → agent executes → agents review agents,” with substantial automation of test writing, docs, and integration work.

- “Agentic PR” share: **~7–15%** in public repos (and potentially higher in private repos), but interpretation becomes difficult because PR sizing/commit granularity shifts. citeturn26view0turn22view2turn27view3  
- AI-assisted share of new code in professional settings: **~50–70%** in leading orgs, with humans increasingly functioning as spec writers/reviewers. This scenario is consistent with internal “all-agent codebase” experiments, but would require major improvements in autonomous verification and governance. citeturn26view0turn27view3turn1search1  

### What remains genuinely unknown

- **A defensible “% of public GitHub commits from AI”** (in the sense of *true causation*) is not currently derivable from public traces: signature-based measures can be disabled, most AI assistance is invisible, and commit behavior is itself a moving target. citeturn4search14turn22view2turn10view5  
- Whether the widely-circulated “4% of public commits” estimate is reproducible depends on a transparent methodology (e.g., exact event stream, exact heuristics, bot filtering, handling of squash merges, and treatment of rebases). The accessible excerpt does not fully specify this. citeturn2view0turn25view0  
- The **true undercount multiplier** between “attributed agent output” and “actual AI-assisted code” likely varies by environment (open source vs enterprise; regulated vs unregulated), and may require inference methods like PR fingerprinting plus careful validation. citeturn27view3turn9search2turn28view0  
- The most important forward-looking question is not “how much code” but **how much verified, maintainable, secure change** agents can produce before human attention becomes the hard ceiling. Early evidence suggests security-related PRs already receive heavier scrutiny, and agentic output changes PR structure/commit patterns in ways that can stress existing workflows. citeturn1search1turn1search2turn26view0
