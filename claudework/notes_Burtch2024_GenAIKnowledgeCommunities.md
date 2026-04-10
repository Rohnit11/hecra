# ChatGPT's Release Caused a 12% Drop in Stack Overflow Traffic, but Reddit Developer Communities Were Unaffected

**Paper:** Burtch, G., Lee, D., & Chen, Z. (2024). "The consequences of generative AI for online knowledge communities." *Scientific Reports*, 14, 10413.
**DOI:** 10.1038/s41598-024-61221-0
**Affiliation:** Questrom School of Business, Boston University
**Published:** 06 May 2024

---

## 1. Identification Strategy

### Synthetic Control Using LASSO (SCUL) for Web Traffic

The "shock" is the public release of ChatGPT on **November 30, 2022**. For the web traffic analysis, the authors employ **Synthetic Control Using LASSO (SCUL)** (Hollingsworth & Wing, 2020), a variant of the synthetic control method (Abadie, 2021). LASSO selects a weighted linear combination of candidate control websites (from the top 1,000 websites tracked by SimilarWeb) that best predicts Stack Overflow's daily traffic in the pre-treatment period. The post-treatment divergence between actual and synthetic traffic is the causal estimate.

### Difference-in-Differences (DiD) for Question Volumes

For question posting volumes, the authors use a **Difference-in-Differences** design. They construct topic-day panels for the top 50 Stack Overflow topic tags over a window bracketing ChatGPT's release (Oct 2022 -- mid-March 2023), using the identical calendar window one year prior (Oct 2021 -- mid-March 2022) as the control period. This follows Goldberg, Johnson & Shriver (2024) and Eichenbaum et al. (2023). The parallel trends assumption is supported by the absence of significant pre-treatment differences (visible in Figure 2A, Page 3).

### Cross-Platform Comparison (Reddit as Control)

The same DiD is applied to analogous Reddit developer subreddits to test whether "social fabric" moderates the displacement effect. The logic: LLMs substitute for pure information exchange but not for social bonds, so communities with stronger social fabric (Reddit) should be less affected.

### Additional Analyses

- Topic-by-topic DiD regressions within Stack Overflow (Figure 3, Page 4)
- DiD on user account tenure and question complexity (Figures 5-6, Pages 5-6)
- Results replicated using the matrix completion estimator of Athey et al. (2021) in supplementary Figure S2

---

## 2. Data & Sample

| Source | Content | Period | Access |
|--------|---------|--------|--------|
| **SimilarWeb** (via Dewey Data) | Daily web traffic to top 1,000 websites | Sept 2022 -- March 2023 | Proprietary (purchased) |
| **Stack Exchange Data Explorer** | Questions, answers, user characteristics | Oct 2021 -- mid-March 2022 AND Oct 2022 -- mid-March 2023 | Public |
| **subredditstats.com** | Daily posting volumes per subreddit | Same windows as above | Public |
| **GitHub** | Active repo counts per language/framework | Cross-sectional | Public |

**Sample size ($N$):** The paper does **not** report explicit observation counts in the main text. The unit of analysis for the DiD is **topic-day** across the **top 50 most popular Stack Overflow tags**. Three subreddits (javascript, jQuery, Django) lacked data. Other Reddit estimates were omitted when no clearly analogous subreddit existed.

**Replication materials:** Stack Overflow data, Reddit data, and analysis scripts are available at OSF: https://osf.io/qs6b3/

---

## 3. Main Findings

### The paper reports NO traditional regression tables with exact coefficients and standard errors in the main text. All results are communicated via event-study and synthetic-control figures with 95% confidence intervals. The supplement (not included in this PDF) may contain regression tables.

### 3.1 Web Traffic Declined by ~12% (SCUL, Figure 1, Page 3)

Stack Overflow's daily web traffic declined by approximately **1 million visitors per day**, equivalent to roughly **12% of daily traffic** just prior to ChatGPT's release. The synthetic control closely mirrors actual traffic pre-treatment, supporting the counterfactual's validity.

### 3.2 Question Posting Volumes Fell Significantly on Stack Overflow (DiD, Figure 2A, Page 3)

Question posting volumes per topic declined markedly after ChatGPT's release. The effect grows over time, reaching approximately **-10 to -15 questions per topic per week** by week 15 post-release. Pre-treatment coefficients are flat at zero (parallel trends satisfied). 95% confidence intervals exclude zero in the post-period.

### 3.3 Reddit Developer Communities Show No Decline (DiD, Figure 2B, Page 3)

The same DiD applied to Reddit subreddits shows **no significant effect**. Point estimates remain centered around zero throughout, with confidence intervals consistently spanning zero. This supports the "social fabric" hypothesis.

### 3.4 Topic Heterogeneity Tracks Training Data Availability (Figure 3, Page 4)

Most affected Stack Overflow topics (approximate declines in daily questions, from Figure 3):
- **Python:** ~-175 to -200
- **JavaScript:** ~-125 to -150
- **ReactJS:** ~-100 to -125
- **Pandas:** ~-75 to -100

Least affected topics: Spring-boot, Spring, Next.js, Angular, API, PostgreSQL (near zero). These tend to involve enterprise contexts requiring private knowledge. All Reddit counterparts show null effects.

A rough correlation exists between the volume of public data sources (GitHub repos, subreddit subscribers) and the magnitude of Stack Overflow declines (Figure 4, Page 5).

### 3.5 Newer Users Disproportionately Exited (Figure 5, Page 5)

Average account tenure of posting users rose by approximately **100-200 days** by week 15 post-release, indicating newer, less socially embedded users systematically reduced participation.

### 3.6 Remaining Questions Became More Complex (Figure 6, Page 6)

Average frequency of long words (6+ characters) in questions rose by approximately **0.3-0.5 units** post-release, consistent with simpler questions being diverted to ChatGPT.

---

## 4. Limitations Noted by Authors (Pages 6-7)

- Assumes absence of confounded treatments (no other major platform emerged simultaneously)
- Complexity proxy (word length) is crude
- Short observation window (several months post-release)
- Cannot speak to whether same dynamic plays out in workplaces
- Stack Overflow and Reddit may not be representative of all developer communities
- Results may be specific to software development knowledge domains

---

## 5. Key Implications

- **Data feedback loop concern:** LLMs trained on open community data may erode the communities producing that training data, potentially undermining future model improvements (Page 6)
- **Social fabric as buffer:** Community managers can combat LLM displacement by enabling socialization, not just information exchange (Page 6)
- **Junior worker vulnerability:** Newer users who exit lose mentorship, peer learning, and career advancement opportunities -- and are also least capable of recognizing LLM hallucinations (Page 4)

---

## Appendix: Sections Skipped

- **Pages 7-8:** References (25 total) and boilerplate (author contributions, competing interests, CC-BY license). No new results.
