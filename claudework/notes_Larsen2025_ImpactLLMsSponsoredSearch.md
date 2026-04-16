# Larsen & Proserpio (2025): Google's BERT Rollout Increases Competition Uniformly but Raises CPC for Short Queries (+1.5%) and Lowers CPC for Long Context-Rich Queries (−2.5%)

**Citation:** Larsen, P. & Proserpio, D. (2025). "The Impact of LLMs on Sponsored Search: Evidence from Google's BERT." Harvard Business School / USC Marshall Working Paper. October 21, 2025.

**File:** `papers/Larsen2025_ImpactLLMsSponsoredSearch.pdf` (106 pages incl. appendices; main text through p. 45)

---

## Identification Strategy Is a Query-Level Difference-in-Differences Exploiting Google's October 2019 BERT Rollout with Linguistic Treatment Intensity

- **Shock:** Google's October 2019 deployment of BERT (Bidirectional Encoder Representations from Transformers) as a primary query-interpretation algorithm in Search (replacing/augmenting the prior RankBrain / Doc2Vec-style interpreter).
- **Primary DD specification (Eq. 3, p. 30):**
  $Y_{i,t} = \beta_1 \text{Post}_t \times \text{LC}_i + \beta_2 \text{Post}_t \times \log(\text{Cos}_i) + \beta_3 \text{Post}_t \times \text{LC}_i \times \log(\text{Cos}_i) + \delta_i + \gamma_t + \epsilon_{i,t}$
  - $\text{Post}_t = 1$ for Nov 2019–Feb 2020; 0 for Jul 2019–Oct 2019.
  - Query fixed effects $\delta_i$ + year-month fixed effects $\gamma_t$.
  - Standard errors clustered at the query level.
- **Treatment intensity measures** (p. 26--29):
  - **Linguistic Complexity (LC):** dummy = 1 if query's syntax-tree depth or unique POS count exceeds the sample median. Captures queries that benefit from BERT's improved syntactic parsing.
  - **Cosine:** $\log(1 + \text{ratio})$ where ratio = (queries "added" to relevance set under BERT) / (queries "removed" relative to D2V), computed at 25th/50th/75th cosine-similarity thresholds. Captures BERT-induced changes in semantic relatedness.
- **Secondary identification (Appendix D):** within-query DD using same calendar months in previous year (2018–19) as a baseline; consistent results.
- **Validation tests:**
  - **Event study (Tables 5, 6, p. 32–33):** pre-treatment month coefficients near zero and insignificant; post-BERT coefficients significant and monotone → parallel trends.
  - **Placebo (Tables 11, 12, p. 37):** re-estimating on Jul 2017–Feb 2018 yields all-insignificant coefficients.
  - **Search-volume / Google Trends controls (Tables 13, 14):** estimates essentially unchanged.
  - **Advertiser budget check (Figure 3, p. 46):** no visible budget adjustment in the 4-month post window, consistent with short-run interpretation.

## Data & Sample Are 11,949 Queries × 24 Months of SEMRush CPC + Competition Score, With Primary Analysis on 10,199 Queries with Pre-BERT Auctions

- **Primary source:** SEMRush (monthly query-level CPC and Competition Score = normalized 0–1 proxy for number of bidders).
- **Sampling:** 100 Amazon MTurkers × 5 topics = 500 queries; 290 kept after filtering; SEMRush broad-match expansion → ~120,000; adult-content filter and search-volume screen → ~40,000; further filtered to queries with ≥1 year of historical data and ≥100 avg searches/month.
- **Final panel:** **11,949 unique queries × 24 monthly observations = 284,146 obs** (Jan 2018–Feb 2020).
- **Primary analytic sub-sample:** **10,199 queries** with non-zero mode Competition Score Jul–Oct 2018 and 2019 (existing auctions pre-BERT). Regression N = **63,474** query-month obs (8-month window Jul 2019–Feb 2020).
- **Query-length strata (Table 2, p. 24):**
  - Short (≤2 words): CPC mean 0.911, CS mean 0.248.
  - Medium (3–5 words): CPC mean 1.339, CS mean 0.278.
  - Long (≥6 words): CPC mean 1.533, CS mean 0.126.
- **External validation (p. 25):** SEMRush Competition Score vs Google Keyword Planner (N = 10,000 queries, 2021–22) — Pearson correlation 0.65 (low/mid/high score) and **0.87** (competition index); Spearman 0.57 between SEMRush CPC and GKP max bid.
- **Theoretical model:** stylized two-sided matching model with 4 bidders indexed by topic θ ∈ {0,1} and context z ∈ {0,1}; CTR = $B_t \mathbb{1}\{\theta=t\} + (1-B_t)\mathbb{1}\{z=q\}$; SPA/GSPA; platform cost $C$ of showing irrelevant ad; 6 regions defined by $(C, B_t)$; main analysis focuses on Region 1 ($C \ge 8/5$).

## Main Findings Are (1) Competition Score Rises Uniformly 0.1–0.4%, (2) CPC Rises +1.5–1.7% for Short Queries but Falls −2.3–2.7% for Long Queries

### Theoretical Propositions (pp. 19–21)

- **Proposition 1 (Platform Selection):** under sufficiently high externality cost $C \ge 8/5$, $\partial \text{NOB}/\partial a = 2 \partial \gamma_t/\partial a > 0$ → better interpretation → more bidders.
- **Proposition 2 (Average CPC):** CPC declines iff $\tfrac{1+B_t}{6}(B_t-1)^2 < \tfrac{\gamma_t}{\gamma'_t \gamma'_q + \gamma_q}$; equivalently CPC falls more readily for context-rich (low $B_t$, i.e., long) queries because improved context signals increase relevancy-score dispersion and reduce the expected second-highest ad rank.

### Empirical: Competition Score (Number of Bidders) — Table 7, p. 34

Dependent variable: $\log(\text{CS})$. N = 63,474.

| Term | 75th threshold | 50th | 25th |
|---|---|---|---|
| Post × LC | **0.0040** (0.002)** | 0.0033 (0.002)* | 0.0033 (0.002)* |
| Post × log(Cos) | **0.0012** (0.001)** | 0.0009 (0.001)* | 0.0007 (0.001) |
| Post × LC × log(Cos) | **−0.0015** (0.001)** | −0.0020 (0.001)** | −0.0030 (0.001)** |

Bootstrapped predicted effects by length (Table 8, p. 35, all $p < 0.01$, 1000 iterations):

| Length | 75th | 50th | 25th |
|---|---|---|---|
| All | +0.3% | +0.2% | +0.1% |
| Short | +0.4% | +0.2% | +0.1% |
| Medium | +0.3% | +0.2% | +0.1% |
| Long | +0.4% | +0.3% | +0.2% |

→ **Uniform ~0.1–0.4% increase in number of bidders across all query lengths**, consistent with Proposition 1.

### Empirical: Cost-Per-Click — Table 9, p. 36

Dependent variable: $\log(\text{CPC})$. N = 63,474.

| Term | 75th | 50th | 25th |
|---|---|---|---|
| Post × LC | **−0.0270** (0.015)* | −0.0289 (0.014)** | −0.0307 (0.015)** |
| Post × log(Cos) | **0.0056** (0.003)* | 0.0065 (0.004)* | 0.0075 (0.005) |
| Post × LC × log(Cos) | −0.00003 (0.005) | 0.0009 (0.006) | 0.0006 (0.009) |

Bootstrapped predicted effects by length (Table 10, p. 37, all $p < 0.01$):

| Length | 75th | 50th | 25th |
|---|---|---|---|
| All | −0.7% | −0.8% | −1.1% |
| **Short** | **+1.7%** | **+1.5%** | **+1.2%** |
| **Medium** | **−1.4%** | **−1.6%** | **−1.8%** |
| **Long** | **−2.3%** | **−2.5%** | **−2.7%** |

→ **Short queries: CPC rises ~1.2–1.7%. Long queries: CPC falls ~2.3–2.7%.** This is the key heterogeneity confirming Proposition 2.

### Combined Interpretation

- BERT improves topic signals → more bidders per query regardless of length (market expansion).
- BERT improves context signals → for long context-rich queries, greater dispersion of relevancy scores, highly relevant advertisers prioritized, expected second-highest ad rank falls → **CPC down despite more bidders**.
- Short context-poor queries lack differentiable context; the bidder-count channel dominates → **CPC up**.

## Limitations as Noted by the Authors

- **Short-run only:** analysis window ends Feb 2020 because COVID-19 (Mar 2020) confounds consumer/advertiser behavior. Long-run equilibrium (advertiser learning, bid adjustment) not testable in this sample (p. 3 fn 3).
- **SEMRush is a third-party proxy:** Competition Score is a relative 0–1 measure, not the true count of bidders; correlations with GKP are reasonable (0.87 on index) but not perfect.
- **Fixed query panel:** estimates are conditional on queries that had pre-BERT auctions; newly emerging queries or non-competitive baseline queries are handled in an appendix (Appendix D.1) but not the main specification.
- **Treatment intensity is inferred, not randomized:** LC and Cosine are constructed linguistic proxies; identification depends on the assumption that these properties interact with sponsored-search outcomes only through BERT.
- **Advertiser valuations static:** theoretical model assumes $v_i \sim U[0,1]$ fixed; a two-period extension (allowing advertisers to learn and re-price) is noted as a direction but not modeled.
- **Platform-side data unavailable:** authors do not observe Google's actual relevancy scores or ad-rank computations.

## Key Implications for the Research Agenda

- **LLMs can lower prices in two-sided matching markets** even while increasing participation — a counterintuitive result relative to Bergemann & Bonatti (2011) and Cowgill & Dorobantu (2020), which predict thinner markets or different price dynamics under information disclosure.
- **Context in language is economically significant:** the paper provides a rigorous channel (relevancy-score dispersion) linking a specific NLP capability (contextual understanding via self-attention) to sponsored-search outcomes.
- **Advertiser strategy implication:** long, context-rich keywords become relatively cheaper and more attractive for highly relevant advertisers; short generic keywords become more expensive; less-relevant advertisers face lower ad ranks and must bid more to maintain reach.
- **Platform-revenue channel:** average CPC declines (~0.7–1.1%) suggest BERT may have modestly reduced per-click revenue for Google even as auction participation rose; total revenue depends on CTR gains not directly estimated here.
- **Methodological contribution:** demonstrates using algorithm-rollout events combined with linguistic treatment-intensity proxies as a feasible DD design for studying LLM effects on digital platforms.

---

## Audit Checklist

- [x] **Identification Strategy:** Query-level DD exploiting Oct 2019 BERT rollout × linguistic treatment intensity (LC + Cosine), plus within-query calendar DD; event study + placebo + search-volume robustness.
- [x] **Data & Sample:** SEMRush panel, 11,949 queries × 24 months (284,146 obs); primary regressions on 10,199 queries (N = 63,474 query-months). Validated against Google Keyword Planner (Pearson 0.87).
- [x] **Main Findings:** CS +0.1–0.4% uniformly across lengths (Table 7–8); CPC +1.5% short, −1.6% medium, −2.5% long (Table 9–10). Supported by theoretical Propositions 1 and 2.
- [x] **Limitations:** short-run only (pre-COVID); SEMRush proxy; fixed query panel; constructed LC/Cos proxies; no observed platform-side scores.
- [x] **Key Implications:** LLMs can lower CPC despite more bidders (context channel); context in language is economically meaningful; long queries become relatively cheaper and short queries more expensive.
