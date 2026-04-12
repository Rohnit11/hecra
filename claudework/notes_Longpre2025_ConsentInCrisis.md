# ~5% of AI Training Tokens Became Restricted by robots.txt in a Single Year, and 45% Are Now Restricted by Terms of Service

**Citation:** Longpre, S., Mahari, R., Lee, A., Lund, C., et al. (2025). "Consent in Crisis: The Rapid Decline of the AI Data Commons." Data Provenance Initiative / MIT.

**Paper:** 41 pages (13 main + 28 appendix). Published with open data at github.com/Data-Provenance-Initiative.

---

## 1. Identification Strategy: Large-Scale Longitudinal Descriptive Audit (Not Causal)

This is a **descriptive longitudinal audit**, not a causal study. There is no DiD, IV, or RDD.

The authors conduct the first large-scale, longitudinal audit of consent protocols (robots.txt and Terms of Service) for the web domains underlying three major AI training corpora: **C4**, **RefinedWeb**, and **Dolma**. They track changes monthly from January 2016 to April 2024 using the Wayback Machine.

The "shock" or variation they exploit is the **introduction of AI-specific crawler agents** (GPTBot launched mid-2023, Google-Extended) and the **rollout of GDPR** (2018), which they use as temporal markers to identify acceleration in restriction adoption.

They also use **SARIMA forecasting models** to project trends forward one year (to April 2025).

### Key methodological components:
- **Automatic collection:** robots.txt snapshots at monthly intervals via Wayback Machine (Jan 2016 - Apr 2024)
- **Human annotation:** Trained 14 crowdworkers ($25-30/hr, $6,972 total) to label website characteristics (content modalities, paywall, ads, purpose, user content, sensitive content)
- **Automatic ToS annotation:** GPT-4o with custom prompts to categorize Terms of Service along three taxonomies (competing services, license type, crawling/AI policy). Micro-average precision/recall: 0.85-0.92 (Table 7, p. 38)
- **SARIMA forecasting:** Non-seasonal order (2,1,2), seasonal order (1,1,1,6); parameters in Table 8 (p. 40), coefficients in Table 9 (p. 40)

---

## 2. Data & Sample

| Component | Detail |
|-----------|--------|
| **Corpora audited** | C4 (15.9M domains, crawled 4/2019), RefinedWeb (33.2M domains, 2008-2/2023), Dolma (45.2M domains, 5/2020-6/2023) |
| **Intersection** | 10,136,147 domains present in all three corpora |
| **HEAD sample (HEAD_All)** | Top 2K domains by token count from each corpus; 3,950 unique domains (union) |
| **HEAD_C4** | Top 2K domains from C4 specifically |
| **RANDOM_10k** | 10K randomly sampled domains from the intersection |
| **RANDOM_2k** | 2K subset of RANDOM_10k for human annotation |
| **Total domains audited** | ~14,000 web domains |
| **Temporal range** | Jan 2016 - Apr 2024 (monthly snapshots) |
| **WildChat comparison** | 1M ChatGPT conversations; 100 manually coded + 1K GPT-4o coded |
| **Crowdworkers** | 14 workers from 6 countries; 14,228 annotation rows |

---

## 3. Main Findings

### 3.1 Rapid Rise of robots.txt Restrictions (Figure 1, Figure 2; pp. 5-6)

- **Full corpus (C4, RefinedWeb, Dolma):** ~1% of tokens restricted in mid-2023 vs. **5-7% restricted by April 2024** (Figure 2a)
- **Head distribution (HEAD_All):** 20-33% of all tokens restricted by April 2024, vs. <3% one year prior -- a **500-1000%+ relative increase** (p. 6)
- **By organization (HEAD_C4, Figure 1 Lower, Table 3):**
  - OpenAI: **25.9%** of tokens restricted
  - Anthropic: **13.3%**
  - Common Crawl: **13.3%**
  - Google Extended: **9.8%**
  - Cohere: **4.9%**
  - Meta: **4.1%**
  - Internet Archive: **3.2%**
  - Google Search: **1.0%**

### 3.2 Terms of Service Restrictions (Figure 1 Middle, Figure 2c; p. 6)

- **45-55% of all tokens** in C4, RefinedWeb, and Dolma now carry some form of ToS data use restriction
- **26-53% relative increase** in ToS crawling restrictions across the three corpora in the last year
- Only in 2024 do ToS pages begin to specifically mention and restrict **generative AI** use

### 3.3 Consent Asymmetries and Inconsistencies (Table 3, Figure 3; pp. 7-8)

- **Conditional restriction rates** (Table 3, p. 7): If *any* AI org is restricted, OpenAI is restricted **91.5%** of the time, vs. Cohere **52.3%**, Meta **52.2%**, Internet Archive **32.3%**, Google Search **17.1%**
- **4.5% of websites** disallowed unrecognized user agents "anthropic-ai" or "Claude-Web" (dubbed "False Anthropic") but *not* Anthropic's actual agent "ClaudeBot"
- **robots.txt vs. ToS contradictions (Figure 3, p. 7):** 35.1% of websites have anti-crawling ToS but *no* robots.txt; 20.3% have restrictive robots.txt but *no* ToS

### 3.4 Head vs. Tail Distribution Divergence (Table 4; p. 8)

- Head domains: **50%+ news/periodicals**, much higher paywall (+23%), ads (+47.9%), video (+39.8%), audio (+38.4%)
- Tail domains: **71.2% org/personal websites**, 15.1% blogs
- Head is **significantly more restricted**: +23.1% restrictive robots.txt, +35.5% restrictive ToS vs. random sample

### 3.5 AI Usage vs. Training Data Mismatch (Figure 4; pp. 9-10)

- **News** = ~40% of HEAD_C4 tokens but **<1%** of ChatGPT queries
- **Creative composition** (fiction, roleplay, poetry) = **~28%** of ChatGPT use but poorly represented in training data
- **Sexual roleplay** = **12%** of WildChat interactions vs. **<1%** of HEAD_C4 sensitive content

### 3.6 SARIMA Forecasts (pp. 6-7; Appendix C)

- By April 2025: additional **2-4% absolute** of full corpus tokens and **7-11%** of head tokens fully restricted by robots.txt
- ToS forecasts: restricted tokens in full corpus expected to rise **6-10% absolute** by April 2025

---

## 4. Limitations

- **Wayback Machine gaps:** Temporal gaps in archival coverage create intermittent lack of smoothness in some time series (acknowledged for Figures 2c, 2d)
- **robots.txt ≠ consent:** The authors "make no assertion regarding whether the prior omission of a robots.txt or restrictions implies consent to use data" (p. 4)
- **robots.txt owners ≠ copyright holders:** Social media sites and forums host content created by third parties; robots.txt/ToS are imperfect proxies for actual copyright holders (p. 12-13)
- **WildChat representativeness:** Only ChatGPT conversations via HuggingFace Spaces wrapper; potentially skewed toward technical users; limited to GPT-3.5-Turbo and GPT-4 APIs between April 2023 - May 2024 (p. 10)
- **GPT-4o annotation accuracy:** 85-92% micro-average precision/recall for ToS classification -- not perfect (Table 7)
- **Random sample bias:** RANDOM_10k sampled from the intersection of all three corpora, which may skew toward more widely-used or high-quality domains (p. 3)
- **Legal ambiguity:** Whether robots.txt or ToS should be enforceable, and how, remain open questions legally and ethically (p. 13)

---

## 5. Key Implications

1. **Data scaling is under threat:** If restrictions are respected/enforced, the availability of high-quality pretraining data will rapidly diminish, challenging the data scaling laws that have driven AI capability improvements
2. **Composition shift:** Restrictions disproportionately affect news, forums, and social media -- if respected, training data will shift toward organization websites and e-commerce, losing freshness, diversity, and representativeness
3. **Non-profits as collateral damage:** Blanket crawling bans (using wildcard "*") also block Common Crawl and Internet Archive, harming academic research and non-commercial AI
4. **Protocol inadequacy:** The REP (robots.txt) was designed in 1995 and is fundamentally unequipped for AI-era consent signaling; a new protocol controlling *how* data is used (not just *who* crawls) is needed
5. **Fair use implications:** The mismatch between training data composition (news-heavy) and actual AI usage (creative composition, brainstorming) may be relevant to US copyright fair use analysis under 17 U.S.C. §107
6. **Inference-time crawling loophole:** Some AI developers may distinguish between crawling for training vs. crawling for inference-time retrieval, potentially circumventing opt-outs
