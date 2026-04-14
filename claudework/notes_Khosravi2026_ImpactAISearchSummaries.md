# Khosravi & Yoganarasimhan (2026) — The Impact of AI Search Summaries on Publisher Traffic

> Khosravi, M. & Yoganarasimhan, H. (2026). "The Impact of AI Search Summaries on Publisher Traffic." University of Washington.

---

## AI Overviews Reduce English Wikipedia Daily Pageviews by ~15%

**Identification Strategy:** Difference-in-Differences exploiting the staggered geographic rollout of Google's AI Overviews (AIO). AIO launched for U.S. users in mid-May 2024 but was not available in most other countries during the study period. The design compares English Wikipedia articles (treated, since U.S. users disproportionately consume English Wikipedia) against matched articles in control language editions (French, German, Japanese, Russian) that share the same content but were not exposed to AIO. Article-language and date fixed effects; two-way clustered standard errors by article and date.

**Shock/Variation:** AIO rollout to U.S. Google Search users (May 14, 2024). Wikipedia's multilingual structure provides the cross-sectional variation — same article exists in multiple languages, but only English-language pageviews are treated.

---

## 46.5 Million Article-Language-Day Observations from Wikimedia Analytics

**Data Source:** Wikimedia Analytics API (publicly available pageview data).

**Sample:**
- 52,262 English Wikipedia articles matched to 4 control languages (French, German, Japanese, Russian)
- 161,382 matched article-language pairs
- 46.5 million article-language-day observations
- **Time period:** October 28, 2023 -- August 14, 2024 (146-day symmetric pre/post windows around AIO launch)

**Unit of observation:** Article-language-day.

---

## AIO Causes a 220-Pageview Daily Decline per Article, Totaling ~4.2 Billion Fewer Visits Annually

**Preferred specification (Table 4, TWFE with article-language and date FE):**
- DiD coefficient: **-220.545** (SE = 15.15, p < 0.001) — daily pageviews per article

**Percentage effects:**
- PPML specification: **-3.5%**
- Weighted log specification: **-8.1%**

**Heterogeneity by topic (Table 5):**
- Culture: **-19.6%**
- Geography: **-16.6%**
- History & Society: **-9.9%**
- STEM: **-7.4%**

**Aggregate magnitude:**
- ~11.5 million fewer daily Wikipedia visits attributable to AIO
- ~4.21 billion fewer visits annually
- Revenue-equivalent loss: **$35.7M--$102.1M per year** (based on Wikipedia's donation-per-pageview benchmarks)

**Robustness:**
- Stable across test-period exclusion (-243.7), weekly aggregation (-14.8%), high-traffic subsample
- Parallel trends tests pass; HonestDiD sensitivity analysis confirms findings

---

## Limitations

- **Single publisher:** Results are for Wikipedia only — generalizability to other publishers uncertain.
- **Language as proxy for geography:** Not all English Wikipedia users are in the U.S.; not all non-English users are outside the U.S. This likely attenuates the estimates (bias toward zero).
- **No mechanism decomposition:** Cannot distinguish whether users who leave Wikipedia go to AIO snippets, other sources, or stop searching entirely.
- **Evolving technology:** AIO features, coverage, and quality changed during the study period; results reflect average effects over this window.

---

## AIO Substitutes for Publisher Content, Raising Revenue-Sharing and Algorithmic Accountability Questions

- AI search summaries directly substitute for visits to content publishers, even for a high-authority source like Wikipedia.
- The revenue shift flows from publishers to search platforms without compensation.
- Risk of a content supply feedback loop: reduced traffic lowers publisher revenue, which may reduce content investment, degrading the very sources AI summaries depend on.
- Policy implications for revenue-sharing mechanisms and algorithmic accountability in AI-powered search.
