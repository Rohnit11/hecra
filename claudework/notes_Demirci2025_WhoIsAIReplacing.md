# Audit Notes: Demirci, Hannane, and Zhu (2025) — "Who Is AI Replacing? The Impact of Generative AI on Online Freelancing Platforms"

**Paper**: Demirci, Ozge, Jonas Hannane, and Xinrong Zhu. 2025. "Who Is AI Replacing? The Impact of Generative AI on Online Freelancing Platforms." Working Paper (dated April 22, 2024).

**Auditor**: Claude (automated lossless audit)
**Date**: 2026-04-13

---

## 1. Identification Strategy: Difference-in-Differences Exploiting Staggered GenAI Tool Releases

- **Method**: Difference-in-Differences (DiD), with multiple robustness estimators: standard TWFE DiD, Callaway and Sant'Anna (2021) CS DiD, Synthetic DiD (Arkhangelsky et al. 2021), and Negative Binomial regression.
- **Shock/Variation**: The exogenous introduction of GenAI tools serves as the treatment shock:
  - **ChatGPT**: Released November 30, 2022. Post dummy = 1 for weeks after Nov 30, 2022.
  - **Image-generating AI**: Midjourney (July 2022), Stable Diffusion (August 2022), DALL-E 2 (September 2022). Post dummy = 1 for weeks after July 20, 2022 (earliest public release).
- **Treatment group**: "Automation-prone" job clusters (writing, engineering, software/app/web development) for ChatGPT analysis; "Image-generating" job clusters (graphic design, 3D modeling) for image AI analysis.
- **Control group**: "Manual-intensive" job clusters (data and office management, video services, audio services), which have notably lower AI Occupational Exposure Index (AIOE) scores.
- **Classification basis**: Job clusters identified via Louvain unsupervised clustering algorithm applied to skill tag co-occurrence networks across job posts. 42 clusters detected, consolidated to 15, with 8 used in main analysis.
- **Key identifying assumption**: Parallel trends in demand between treated and control clusters absent GenAI introduction. Validated via event-study plots (Figure 1) and joint F-tests on pre-period coefficients (p = 0.1759 for ChatGPT; p = 0.7323 for Image-generating AI).
- **Baseline specification** (Equation 1, p. 9):
  y_ctl = beta * Post_t * T_c + gamma_cl + gamma_t + epsilon_ctl
  - Unit: week t, country l, cluster c
  - Fixed effects: country-cluster (gamma_cl) and week (gamma_t)
  - Standard errors clustered at job cluster level

---

## 2. Data and Sample

- **Source**: Undisclosed globally leading online freelancing platform, accessed via API. Supplemented with Google Trends Search Volume Index (SVI) data.
- **Time period**: July 2021 to July 2023 (approximately 2 years).
- **Unit of observation**:
  - Job post level for summary statistics and secondary outcome regressions.
  - Cluster-week-country level for main demand regressions (aggregated).
- **Raw data**: 2,712 unique skill tags; 1,388,711 job posts across 15 clusters after initial cleaning.
- **Final analysis sample**: 1,218,463 job posts from 541,828 employers across 8 clusters. Restricted to fixed-payment jobs (~80% of sample), 61 largest countries (95% of posts), excluding top 1% budget outliers.
- **Job post observables**: Title, job descriptions (skill tags, preferred software), max/min budget, payment type (fixed/hourly), local job indicator, number of bids, average bid price, date, location (country/city), final status (awarded/expired).
- **Summary statistics** (Table C4, p. 25):
  - Weekly number of job posts: Mean = 11,811.97, SD = 2,468.40, Median = 11,462
  - Maximum budget (USD): Mean = $337.17, SD = $596.23, Median = $168.31
  - Number of bids per job post: Mean = 26.43, SD = 36.29, Median = 13
  - Number of skill tags per job post: Mean = 4.52, SD = 1.61, Median = 5

---

## 3. Main Findings

### ChatGPT Reduces Demand for Automation-Prone Freelance Jobs by 21% (Table 2, p. 11)

| Estimation Method | All Treated Groups | Writing | Software/App/Web Dev | Engineering |
|---|---|---|---|---|
| DiD | -0.234** (0.0837) | -0.362*** (0.0543) | -0.231** (0.0543) | -0.110 (0.0577) |
| Negative Binomial | -0.241*** (0.0916) | -0.379*** (0.0666) | -0.170*** (0.0701) | -0.235*** (0.0665) |
| CS DiD | -0.174*** (0.0364) | -0.233*** (0.0183) | -0.187*** (0.0183) | -0.1016*** (0.0183) |
| Synthetic DiD | -0.176*** (0.0271) | -0.280*** (0.0338) | -0.165*** (0.0338) | -0.0798** (0.0338) |

- N = 39,528 for all treated groups; N = 26,352 for individual clusters.
- R-squared of DiD models > 0.85.
- **Interpretation**: 20.86% decrease in weekly job posts for automation-prone vs. manual-intensive jobs within 8 months of ChatGPT. Writing most affected (30.37%), followed by software/app/web dev (20.62%), then engineering (10.42%).

### Image-Generating AI Reduces Demand for Graphic Design and 3D Modeling by 17% (Table 3, p. 13)

| Method | All Treated (Entire) | All Treated (Pre-ChatGPT) | Graphic Design (Entire) | Graphic Design (Pre-ChatGPT) | 3D Modeling (Entire) | 3D Modeling (Pre-ChatGPT) |
|---|---|---|---|---|---|---|
| DiD | -0.1864** (0.0488) | -0.1381** (0.042) | -0.2042** (0.0484) | -0.1677*** (0.036) | -0.1687** (0.0484) | -0.1083** (0.0361) |
| Neg. Binomial | -0.1244*** (0.0411) | -0.0869*** (0.0186) | -0.1232*** (0.0427) | -0.1025*** (0.0111) | -0.1319*** (0.0392) | -0.0627*** (0.0125) |
| CS DiD | -0.1077* (0.0615) | -0.0577 (0.077) | -0.187*** (0.0251) | -0.150*** (0.04088) | -0.028 (0.0251) | 0.034 (0.0408) |
| Synthetic DiD | -0.178*** (0.0297) | -0.121*** (0.0335) | -0.176*** (0.0303) | -0.139*** (0.0312) | -0.180*** (0.0303) | -0.103*** (0.031) |

- N = 32,940 (entire period); N = 22,265 (pre-ChatGPT period).
- **Interpretation**: 17.01% decrease in image-generating job posts vs. manual-intensive. Graphic design: 18.49% decline; 3D modeling: 15.57% decline.

### Google SVI Predicts Demand Decline: Higher ChatGPT Awareness Correlates with Greater Job Loss (Figure E1, p. 26)

- Coefficient on SVI * Post: -0.00405** (SE = 0.00107), N = 39,528, R-squared = 0.885.
- One SD increase in SVI corresponds to 8.01% decrease in job posts.
- Equivalently, a 1% increase in SVI is associated with a 0.404% decrease in job posts.

### Remaining Employers Post Higher-Budget, More Complex Jobs with More Competition (Table D1, p. 24)

- For employers posting in both pre- and post-periods (35.45% of sample):
  - Maximum budget: +$12.67*** (SE = 2.987), a 5.71% increase vs. pre-mean of $221.66.
  - Number of bids (logged): +0.0822** (SE = 0.0229), an 8.57% increase vs. pre-mean of 3.37.
  - Complexity (skill tags): +0.103*** (SE = 0.0157), a 2.18% increase vs. pre-mean of 4.74.

---

## 4. Robustness and Placebo Tests

### ChatGPT Robustness (Table D2, p. 25)
- 3-month post-period only: -0.1448* (SE = 0.0566)
- Alternative comparison group (manual + excluded clusters): -0.250*** (SE = 0.066)
- Local jobs as comparison: -0.371** (SE = 0.069)
- Hourly-paid jobs: -0.150*
- Aggregated cluster-week level: -0.2909**
- Excluded clusters (legal, finance, marketing, etc.) vs. manual-intensive: beta = 0.0272, insignificant

### Image-Generating AI Robustness (Table D3, p. 25)
- 3-month post-period: -0.0957* (SE = 0.0437)
- Alternative comparison group: -0.195*** (SE = 0.0276)
- Local jobs comparison: -0.313*** (SE = 0.0259)

### Placebo Tests
- ChatGPT placebo (November 2021, one year early): coefficient = -0.068, insignificant.
- Image-generating AI placebo (January 2022): coefficient = -0.005, insignificant.
- Additional image AI placebo (Jan-Apr 2022): coefficient = 0.0325, insignificant.

---

## 5. Limitations (as Noted by Authors)

1. **Short-term effects only**: The paper documents short-term (8-month) impacts; long-term labor market effects of GenAI remain unclear and may differ (p. 15).
2. **Online labor markets may not generalize**: OLMs have unique features (flexible, short-term, task-oriented, remote) that differ from traditional labor markets, though authors argue insights may extend beyond contract employment (p. 1-2).
3. **Demand-side measurement only**: The paper measures employer demand (job posts), not freelancer outcomes like earnings or employment. Does not capture supply-side responses.
4. **Potential selection in employer sample**: Secondary outcome analysis (budget, complexity, bids) restricted to employers present in both pre- and post-periods (35.45% of sample) to mitigate selection bias from employer exit (p. 12, 24).
5. **Exclusion of certain clusters**: Legal, accounting/finance, social media marketing, internet marketing, and statistical analysis excluded due to non-parallel pre-trends or credentialing requirements (9.34% of sample; p. 7).
6. **AIOE index limitations**: AIOE measures exposure to LLMs only, not image-generating AI. Classification relies on manual mapping of job clusters to occupational titles (Table C3).
7. **Undisclosed platform**: Data come from an unnamed platform, limiting replicability.
8. **Engineering cluster zeros**: 48% of pre-period observations are zero in engineering cluster, rising to 55% post-period. This explains discrepancy between DiD and Negative Binomial estimates for engineering (footnote 14, p. 11).

---

## 6. Key Implications for the Broader Research Agenda

1. **GenAI disproportionately affects automation-prone freelance tasks**: Writing, coding, and engineering jobs see the largest demand declines, consistent with AIOE rankings and public awareness measures. This provides early evidence that GenAI substitution effects are heterogeneous across task types.
2. **Image-generating AI has independent displacement effects**: Separate from LLM impacts, tools like Midjourney and Stable Diffusion reduce demand for graphic design and 3D modeling, suggesting multiple GenAI modalities create distinct labor market shocks.
3. **OLMs as early warning systems**: Online freelancing platforms, with their flexible and task-oriented structure, may be leading indicators for broader labor market disruption from GenAI.
4. **Demand-side evidence complements supply-side studies**: Unlike Hui et al. (2023) who measure freelancer employment changes, this paper measures employer posting behavior, providing a cleaner demand-side measure less subject to supply-side confounds or survivorship bias.
5. **Remaining jobs become more complex and higher-budget**: The composition of surviving job posts shifts toward greater complexity and higher budgets, suggesting GenAI may substitute for routine tasks while complementing more complex ones.
6. **Public awareness correlates with substitution**: Google SVI as a proxy for awareness of ChatGPT's substitutability predicts demand decline, suggesting information diffusion plays a role in adoption timing.
7. **Open questions for future work**: Long-term effects on earnings, welfare, and productivity remain unclear; whether early displacement leads to permanent job loss or reallocation is unresolved.

---

## Appendix: Chunk-by-Chunk Reading Log

| Chunk | Pages | Content |
|---|---|---|
| 1 (pp1-4) | 1-4 | Title, abstract, introduction, literature review, paper structure |
| 2 (pp5-8) | 5-8 | Institutional details (GenAI, OLMs), data description, cluster classification, AIOE mapping, Google SVI data |
| 3 (pp9-12) | 9-12 | Empirical strategy (TWFE DiD, event study, CS DiD, Synthetic DiD), Table 1 summary stats, results for ChatGPT (Table 2), event study Figure 1 |
| 4 (pp13-16) | 13-16 | Image-generating AI results (Table 3), event study Figure 3, Google SVI analysis, robustness discussion, conclusion |
| 5 (pp17-20) | 17-20 | References, Appendix A (GenAI timeline), Appendix B (Louvain method details, sample construction) |
| 6 (pp21-24) | 21-24 | Appendix C (Tables C1-C4, Figure C1), Appendix D (Table D1 other outcomes, Table D2 ChatGPT robustness) |
| 7 (pp25-26) | 25-26 | Table D2 continued, Table D3 (image AI robustness), placebo tests, Appendix E (Figure E1, Google SVI regression) |
